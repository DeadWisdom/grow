# grow

A platform for creating highly operational, continuously deployed services by defining a network of data-processing actors.

We shift focus from coding in editors to iteratively developing usable services. At the beginning, simple running processes can be defined, deployed, and interacted with. These can then be composed into larger workflows, and then deployed as fully-featured services. All along the way, everything is tested, monitored, and integrated, so there is no point where we can get ourselves in a situation that our service is un-deployable, un-integratable, or un-maintainable.

Code is no longer the hard part. LLMs give us an opportunity to let go of the code as the central focus. It never should have been anyway, because that makes us focus on solutions and implementations rather than needs and problems. This has always created a cart-before-the-horse mentality in the industry that drags it down. Philiosophies like Agile and Test Driven Development have tried to alieviate this, but developers are fundementally pushed towards thinking about the code first.

With Grow, developers define the fundemental structure like tests and reqiurements first. LLMs can then help us generate the code, and we can use our structure to validate and complete that work. We can also use the AI to modify or optimize the code. For instance, quickly updating code because an third-party API changed or automatically converting code from Python to Rust for optimization purposes.

Still we don't want to let go of everything all at once; we an still use grow with github and hand-generated code, but that takes a back-seat to the more difficult problems.

## Fundemental Entities

### Actors

- Represent scalable, running processes or thread
- Communicate with messages
- Are defined by:
  - Documentation, goals, requirements, and examples
  - Configuration parameters
  - Types of incoming messages they respond to
  - Types of outgoung messages they send
  - Integrations with other services like databases and third-party APIs
  - Performance and scaling parameters
- Are tested by defining example configuration, incoming messages, resulting outgoing messages
- Can be interacted with and debugged live, for instance by going into their running environment

### Workflows

- Represent graphs of coordinated Actors
- Are defined by:
  - Documentation, goals, requirements, and examples
  - Configuration parameters
  - Set of Actors and their configurations
  - Routes to dispatch messages between them
  - Rules for selecting routes
  - Performance and scaling parameters
- Are tested by defining example configuration, incoming messages, resulting outgoing messages

### Services

- Represent interfaces to running actors and workflows
- Are defined by:
  - Documentation, goals, requirements, and examples
  - Configuration parameters
  - Interfaces like HTTP Endpoints
  - Performance and scaling parameters
- Basic dashboards, monitoring, logging, and general visibility; athird-party services can be used as well with via Open Telemetry
- Alerting of errors and performance issues
- Consumers/Customers can be managed, handling api-keys, rate-limiting, billing and payments
- Versioning, and backwards compatibility is tracked, consumers can be notified
- Continuous deployment is achieved easily since actors and workflows are thoroughly tested

## Implementation Plan

### Beginning Requirements
- Deployment can be on some specific platform for now until someone needs something else
- Let's make configuration YAML files for now, with a nice CLI, and a UI later; but we need a UI in the cloud to be really useful
- Feature: Create/Manage a Service
- Feature: Create/Manage an Actor in a Service
- Feature: Manage multiple documents on the Actor that represent the code
- Feature: Start the service / Spawn the Actor
- Feature: Route messages
- Feature: Live debug actor
- Feature: Automatic Testing
- Feature: LLM generation/modification
- Feature: Create/Manage a Workflow
- Feature: Rule-based message routing

