> Continuous attention to technical excellence and good design enhances agility.

> Simplicity--the art of maximizing the amount of work not done--is essential.

> The best architectures, requirements, and designs emerge from self-organizing teams.

### Craftsmanship in development teams
An agile team employs multiple methods to build in quality and robustness to the product, creating technical agility. The team strives for a product that has been continuously reviewed, continuously tested, and which has been refined and simplified as much as possible. The practices and process that a team uses are owned by the team itself. How a team incorporates craftsmanship to their solutions should be a common discussion among the team, and an area that the team strives to regularly improve.

### Adopt a Coding Standard
Forming a **coding standard** is an essential task for any Agile Team. Creating agreed-upon documentation that defines the style in which code will be written and any practices to be followed or deemed unacceptable, prevent the occurrence of potential problems. The team’s coding standards also likely will include topics such as how errors are handled and how code is structured (directory convention, etc.). The intent is to assure the Delivery Team develops code uniformly, which aids future code updates and developer comprehension, and eases code review. Coding best practices fall into two groups, independent best practices (e.g., variable naming conventions) and dependent best practices (e.g., how to use aspect-oriented programming principles).

During Sprint 0, the Agile Team and its senior developers should define the coding best practices the team will use during software development activities. These practices should be presented to the team and discussed in detail to assure complete understanding of how to execute acceptable coding practices, and the implications of not doing so. During Retrospectives, these practices should be considered and modified as needed, to reflect possible improvements for the team.

### Strive for Secure Coding
**Secure coding** is using best practices to prevent known vulnerabilities and keeping the code secure by refactoring as new vulnerabilities are identified, or as the environment (i.e., operating systems, browsers, web specifications, etc.) changes. Implementing this practice includes:
* Defining secure coding best practices at the start of the project.
* Reviewing practices during the code review for the checked-in file.
* Using free open-source software that checks against defined best practices to review the code against general coding practices and against custom practices that the team would define within the tool. See the Tools section of this document for more information on code review and scanning tools.
* Integrating automated code reviews into code check-in and continuous integration to gain the best results with minimal manual effort.
* Scanning applications for vulnerabilities on the server. Three types of scans would benefit the team:
*  Scan the server for container-based vulnerabilities. The Retina network security scanner is one of the best tools to use for this purpose. Another tool for the same purpose is the Nessus Vulnerability scanner.
*  Perform static analysis on the code with tools such as IBM Appscan or HP Fortify.
*  Perform automated penetration testing using tools such as Hailstorm.
*  Documenting the actions to be taken for each type of scan.

Secure-coding best practices incorporate the Open Web Application Security Project (OWASP) Enterprise Security Application Programming Interface (ESAPI) to simplify and standardize the implementation of security functions in the environment, unless environmental factors prohibit deployment. OWASP ESAPI Toolkits help software developers guard against security-related design and implementation flaws by ensuring simple, strong security controls are available to every developer. An integrity check of software products is included to facilitate organizational verification of software integrity after delivery.

### Refactor your solutions
Code refactoring is a technique for restructuring an existing body of code, altering its internal structure without changing its external behavior. We refactor to improve the nonfunctional attributes of the software. Advantages include improved code readability and reduced complexity to support maintenance. There are two general benefits:
* **Maintainability** > It is easier to fix bugs/defects when the source code has been written so that it is easy to understand and grasp. This might be achieved by reducing large routines into a set of individually concise, well-named, single-purpose methods. It might also be achieved by moving a method to a more appropriate class or by removing misleading comments.
* **Extensibility** > It is easier to extend the capabilities of an application if it uses recognizable design patterns and provides some flexibility where this may not have existed previously.

### Invest in Unit Testing
Unit tests are a foundational software engineering practice for development teams. It refers to developers writing small tests that test individual components in the system, typically with code that's automatically run during builds. Designing unit testing is a challenging task for the development team. The unit test infrastructure and architecture need to be designed during Sprint 0 of the project. The unit tests could cover all layers of the application or target only certain layers.

Unit tests should be included in the definition of “Done” for any work item, and developers should discuss plausible test strategies when the work is planned. When a developer makes the code ready for the Sprint’s releasable software, this indicates that the unit tests scoped for the code are also ready and included in continuous integration. Continuous integration means that unit tests are executed every time automated test builds are generated from the code repository. If one of the unit tests should fail during execution, the continuous integration mechanism notifies the project team every time it tries to execute the test, until the problem is resolved.

### Use Continuous Integration
Continuous integration is a foundational agile technical practice. It requires each team member to integrate their latest work with the trunk frequently -- at least daily -- and to have each integration verified by an automated build (with automated testing included). Continuous integration increases the quality of the software by reducing the defect escape rate, and decreases maintenance and sustainment costs. Developers working from a local copy for days at a time is a bad practice and contributes to risky, complicated merges; continuous integration mitigates this risk.

Continuous integration tools can be set up to notify the development team of any failed build. This enables the team to resolve immediately small integration issues early, before they become large or multiple issues just prior to a release/deployment.

When complemented with **automated unit testing**, code quality inspection tools, and vulnerability scanning tools, continuous integration becomes an even more powerful tool for the Agile Team. Automated unit tests identify problems early and prevent integration defects from piling up, reducing risk to release candidates and product deliveries. Automated code quality inspection tools and vulnerability scanning tools can identify poor coding practices, code violations, and security violations, without the need for additional developer code review. Continuous integration increases code quality and reduces bugs in the deployed software.

Teams that practice continuous integration tend to be able to complete a build easily and have a lower cost-of-change than teams who have to manually exercise their build process. 

Guidelines for successful continuous integration include:

* Providing the ability for a “one-click-build”
* Executing automated builds at every commit or at least once daily
* Achieving 60-percent unit test code coverage as a target, with anything above 70 percent considered exceptional
* Provide automated notification to the entire development team when a build or unit test fails.

### Continuous Delivery and Continuous Deployment
When a team has continuous integration working well, they can consider the more mature practices of Continuous Delivery and Continuous Deployment. 

Continuous integration gets us as far as having a server somewhere that builds the software and runs the automated tests, but it doesn't get it off that build server. Continuous Delivery is that next step -- ensuring each change to the software is packaged up and releasable, and we can push it to production with click. This means we must have automated and smoothed all the mechanical steps of the release and deployment process, which often slows down teams. In a Continuous Delivery environment, releases become boring. 

Continuous Deployment goes one more level -- each change is pushed to Production automatically. You must be practicing Continuous Delivery before you can consider Continuous Deployment. To make this leap, we must now automate all those qualitative and judgement aspects of releases that might have been perfomed by humans before: Do we really trust the autoamted QA? Have we covered the edge cases? Does this release degrade performance anywhere? Is the timing right for the business? When the software can automatically stop releases that should not go out, but let the others pass, we've reached Continuous Deployment.   

### DevOps
//TODO (should come from the DevOps playbook and reference it)

### Continuous Monitoring
//TODO (should come from the DevOps playbook and reference it)

### Do Code Reviews
There are two primary benefits of **code reviews**. First, any bug found during inspection is cheaper to fix then (by orders of magnitude) than if it is found later in the process. Second, a team that is practiced in inspecting the code tends to be able to embrace the Agile principle of collective code ownership. All of the code (and any bugs identified) are the responsibility of the team, rather than a specific individual. This mindset results in a tighter, higher-quality product.

Collaborative code reviewing tools, such as Atlassian’s Crucible, which is a part of our SmartSuite environment, provide the ability for inline comments for code with informative feedback. Agile teams use code reviews to identify and fi bugs and weaknesses that may have been overlooked. Code reviews also enable senior developers to mentor junior developers on how to write better quality code.

Code reviews are performed for all code changes and should be included in the team’s software development workflow. When developers complete coding for a task, the status of the task becomes “code review,” and the Technical Lead is notified by automated email. Code is not included in the next build or made available to the test team unless the Lead Developer reviews the code with the developer present. If rejected, the task returns to the developer. If approved, the task status changes in the scope tracker to include the code in the next test build. The team should decide which of the following elements will be included in the team’s code review practice:

* Changed code
* Results of security and code quality scans
* Test case for the capability
* Functionality

### Seek an agile architecture
//TODO

### Use Test-Driven Development
TDD is a software development practice that aggressively increases code quality and testability, and integrates well with the iterative nature of Agile and the process of refactoring code. Both small and large Agile teams can use TDD. It asks developers to write a test first, then produce only enough code to pass that test, then refactor the code to integrate into the existing codebase in an elegant way. Round after round, this practice continues building a robust, tested body of code.

TDD is performed in a series of Sprints for a release cycle. It is **not a testing methodology**; it is a software development technique. The objective is 100-percent coverage for the software that is built and maintained. The TDD test suite is generally executed with each built, but at least once a day as part of the continuous integration, and checks the state of the software. A previously working broken module is identified when TDD tests are automatically executed during a continuous integration build on the development servers.

Having such an extensive suite of tests built into the product greatly aids in onboarding new team members, or when developers need to work in unfamiliar parts of the system. The system's correct behavior is so well codified in the body of tests that developers exhibit exceptional boldness in making changes, and they have much greater confidence deploying their changes.

## Testing
Testing incremental functionalities of the product developed by the Agile Team involves reviewing the User Stories to ensure they meet the definition of “Done,” are considered complete, and have passed the acceptance testing criteria. Preparing for testing activities includes any artifacts required to successfully execute testing, such as the scripts, code, data, etc. The objective of any testing activity is to determine whether the incremental product developed satisfies the intended requirements and also proves to be a testable component. Along with Functional and Regression Testing activities, Automated Testing, and Acceptance Testing are also performed.

###Functional Testing
The team performs **functional testing** to ensure that the functional behavior of the product (or system) corresponds to its specifications, which involves testing one component at a time. Unit Testing focuses on testing the smallest individual units or components of the build, application modification, or system, to verify that each component is built to design specifications. Functional testing is performed after the component has been unit tested to verify functionality against the requirements and specifications, before system and integration testing.

###Regression Testing
The team performs **regression testing** to isolate and resolve any errors or defects introduced during modifications based on change requests. This testing verifies that the component still meets its specified requirements and no adverse effects have been identified as a result of implemented changes. Regression testing focuses on executing test scripts and/or scenarios in functional and non-functional areas of a system after changes have been made; ensuring the product/system still meets its specified requirements, and will not fail when deployed to the operational environment or adversely affect code that is currently in production. The Agile Team should conduct a degree of regression testing at the end of each level of testing to ensure that any defects corrected during each testing segment have not caused additional defects.

###Automated Testing
**Automated testing** must be considered part of the software development cycle. The tests themselves are an integral part of software development because they help minimize time spent debugging and help the team identify and resolve issues before users do. Prior to committing code, the code should be thoroughly subjected to automated test, and those tests should be committed with the code. This helps team members ensure their work is compatible with the code being committed. The entire automated test suite should be run against all code changes before that code is committed to ensure that there are no conflicts with other areas of the project.
When a bug is found in the system, the developer committed to fixing the bug should follow the following steps:

1. Write a unit test that expects the specific failing behavior not to occur
2. Run the test, which should fail because the bug will still be in the code
3. Fix the bug
4. Run the unit test to ensure the test now passes.

This practice ensures the bug can never be reintroduced into the system without being caught by the automated test suite.

###User Feedback or Acceptance Test
Successful Agile projects regularly put new software in front of the users for immediate feedback. This does not require a deployment to a production server but does require a demonstration or test server to which users have access and can use to try out new features still in development. Making this environment available increases communication between the users and the Agile Team. If features are found to be off track, the developers can start over, with only the loss of a Sprint’s worth of work versus 6 months or more if discovered later. This has the added benefit of showing users that while you may not have had a deployment recently, you are making progress on the highest priority request.