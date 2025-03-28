[[Testing]]

## What is smoke testing?

Smoke testing, also called _build verification testing_ or _confidence testing_, is a software testing method that is used to determine if a new software [build](https://www.techtarget.com/searchsoftwarequality/definition/build) is ready for the next testing phase. This testing method determines if the most crucial functions of a program work but does not delve into finer details.

## What are the different types of smoke testing?

Types of smoke testing include the following:

- **Manual smoke testing.** Human software testers conduct smoke tests manually. This includes manually developing and updating test cases. Test scripts are also written manually for new or existing features.
- **Automated smoke testing.** Software tools are used to automate the smoke testing process. Smoke testing tools make the testing process more efficient by automatically providing relevant tests.
- **Hybrid smoke testing.** Hybrid testing is a combination of manual and automated smoke testing, where testers write test cases and then automate the tests using a tool.


A general process for performing a smoke test may look like this:

1. **Decide** **between manual, automated or hybrid testing.** Manual testing is most commonly chosen first, while automated tests may be done once more elements are added to the smoke test.
2. **Create testing scenarios.** QA testers need to know how many test cases they need for each core software feature. Pass or fail metrics should be decided on based on software and organizational needs and standards.
3. **Create the smoke tests.** Either using manual or automated processes, write and create the test suites.
4. **Run and record tests.** While smoke tests are run, testers should have a process set to record the results for each test. This can either be manual or automated.
5. **Analyze smoke test results.** If the software fails, it's returned to the development team for more testing. If it passes, it is ready for more rigorous functional testing.

## Advantages of smoke testing

Smoke testing is a valuable part of the testing process for the following reasons:

- Automation enables tests to be run faster and more often.
- Future builds are constructed on bug-free software.
- It identifies defects in early stages of development.
- It lessens risks associated with adding code to existing build integrations.
- Smoke tests can be run often due to their low resource requirements and simple process.
- There is flexibility in implementation with manual, automated and hybrid types.
- It verifies software quality early on in development, ensuring that a build is stable.

## Disadvantages of smoke testing

There are some disadvantages that come with smoke testing, however, for example:

- Smoke testing doesn't cover all functionalities in a piece of software -- only specified core functionalities are tested.
- Not every [bug](https://www.techtarget.com/searchsoftwarequality/definition/bug) or problem may be found with smoke tests, and some may still be found later in development.
- Manual smoke testing takes longer to complete when used in larger projects.