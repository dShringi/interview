A set of principles that describes a way of making software that, when followed, enables companies to create code that can be released reliably, scaled quickly, and maintained in a consistent and predictable manner.

1. Codebase: One codebase tracked in revision control, many deploys
   - all assets related to an application, source code, provisioning script, and configuration settings, are stored in a source code repository that is accessible to development, testing, and system administration staff, CI/CD pipelines
2. Dependencies: Explicitly declare and isolate dependencies
   - only code that is unique and relevant to the purpose of the application is stored in source control
   - external artifacts such as Node.js packages, Java .jar files should be referenced in a dependencies manifest loaded into memory at runtime
3. Config: Store config in the environment
   - configuration information should be injected into the runtime environment as environment variables or as settings defined in an independent configuration file
4. Backing Services: Treat backing services as attached resources
   - treat external components such as databases, email servers, message brokers, and independent services that can be provisioned and maintained by systems personnel as attached resources
5. Build, Release, Run: Strictly separate build and run stages
   - Build stage is where code is retrieved from the source code management system and built/compiled into artifacts stored in an artifact repository
   - after the code is built, configuration settings are applied in the Release stage
   - in the Run stage, a runtime environment is provisioned via scripts and the application and its dependencies are deployed into the newly provisioned runtime environment
6. Processes: Execute the app as one or more stateless processes
   - Store any data that is required to persist in a stateful backing service, such as databases. The idea is that the process is stateless and shares absolutely nothing
   - an application developed under The 12 Factor App structure will run as a collection of stateless processes
   - no single process keeps track of the state of another process and that no process keeps track of information such as session or workflow status
7. Port Binding: Export services via port binding
   - a service or application is identifiable to the network by port number, not a domain name
   - potential issues due to a collision between port number assignment private to the network and public use of that same port number by another process publicly can be avoided using port forwarding
8. Concurrency: Scale-out via the process mode
   - organizing processes according to their purpose and then separating those processes so that they can be scaled up and down according to need
   - supporting concurrency means that different parts of an application can be scaled up to meet the need at hand
9.  Disposability: Maximize robustness with fast startup and graceful shutdown
    - applications should start and stop gracefully. This means doing all the required "housekeeping" before an application is made accessible to consumers
10. Dev/Prod Parity: Keep development, staging, and production as similar as possible
    - all deployment paths are similar yet independent and that no deployment "leapfrogs" into another deployment target
    - ensures the same deployment process for Production as it does Development
11. Logs: Treat logs as event streams
    - should stream logs to a chosen location—not simply dump them into a log file
    - sending log data in a stream that a variety of interested consumers can access. The process for routing log data needs to be separate from processing log data
12. Admin Processes: Run admin/management tasks as one-off processes
    - admin processes are first-class citizens in the software development lifecycle and need to be treated as such
    - though the admin processes are separate, you must continue to run them in the same environment and against the base code and config of the app itself. Shipping the admin tasks code alongside the application prevents drift.
