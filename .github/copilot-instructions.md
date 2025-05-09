When doing a .NET Upgrade, use the following rules:
* When running tests, ONLY run the exact tests listed in the plan.
* DO NOT add any test projects other than those in the plan.
* when you discover the list of test projects to run, triple-check to make sure that you are only using the ones I explicitly requested.

When migrating tests, do not change the test framework. If a project uses xunit, keep using xunit. If a project uses MSTest, keep using MSTest.