# SprintBootApplicationSample
Sample drafted project for Employee using Cucumber,Rest Assured Wiremocks and Spring boot
# demo application drafted project

SpringBoot based integration testing using Cucumber and Rest Assured

## Objective

* Create a reference implementation which provides the best practices of running integration & component tests in a SpringBoot application for creating employee
* While Rest Assured provides an excellent DSL to quickly create component and integration tests , using Cucumber will provide us a not only creating readable and maintainable code , but also being able communicate the requirements across various stakeholdes in a human readable language.
* Gherkin (used by Cucumber to define the automated tests) along with Rest Assured provides a very effective solution for the same.

### Technologies

* Spring Boot Test - Provides the spring boot ecosystem required for the tests
* Rest Assured - Provides the service client APIs using the powerful DSL for creating maintainable tests
* Cucumber (with Spring Boot) - BDD based Integration Test and Component Tests
* Spring Cloud Contract WireMock
    * The WireMock server is setup using the `@AutoConfigureWireMock(port = 8090)` annotation
    * The programmaticaly created wiremock stubs are demonstrated in the files [EmployeeSteps]
* Automatic Pact file generation for each of the test scenarios , based on the registered Pact listeners using `wiremock-pact-generator`



#### Tests

* The BDD tests are setup using `CucumberIntegrationTest` class that provides the cucumber configuration and depends on
    * The `SpringIntegrationTest` class : this wires up the spring boot tests and starts the server and the wiremock server at port `8090`
    * The `steps` folder provides the glue code or test steps (bound to the features)
    * The `java\features` folder provides the BDD test scenarios
