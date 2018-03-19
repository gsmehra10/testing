#ProvarTestResults

 ProvarTestResults contains example Test Cases for integrating Provar test results into a Salesforce Org.
 For the purposes of these tests we've integrated with the Provar Test Integration package which contains
 the following custom objects:

    1. TestSuiteExecution - for logging a test execution run and measuring the performance of the complete
                            execution cycle. This can be linked to any of your own custom objects or 3rd
                            party packages such as AgileAccelerator or Flosum if you wish.
    2. TestCaseExecution -  for logging results of individual tests including a summary of their execution
                            time and status should you wish.

 This repository contains the following test cases you can re-use:
    Initialise Test Suite: This Setup Test will execute each time you run an execution and populate the
                           TestSuiteExecution object automatically, and maintain test references for the    
                           complete Test Run.

    Finalise Test Suite:   This Teardown Test will execute each time you run an execution and complete the
                           TestSuiteExecution duration information.


    Write Test Results:	Is a Callable Test with a parameter of the Test Case Name being run, which you 
    to Salesforce          can pass using the {TestCaseName()} expression. You may want to extend this
                           test to pass the start and end times for the test case too. This test inserts
                           a new record into TestCaseExecution and links it to the TestSuiteExecution. 

    Example Test-Do Stuff: Is a basic test case that you can run with a finally block that demonstrates
                           how to use the Write Test Results to Salesforce callable test in a Finally 
                           step.


