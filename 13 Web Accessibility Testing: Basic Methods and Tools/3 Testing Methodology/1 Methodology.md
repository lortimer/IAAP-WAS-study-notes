# Methodology

The methodology recommended by the course is

1. Determine the Scope for Testing 
   1. Determine how many pages will be evaluated, selecting representative pages, choosing which conformance level to evaluate against, etc.
2. Conduct Tests
    1. Automated Tests: Use a specific tool or tools to find issues that can be found automatically and report those as a foundation for the work to come in the manual testing phase.
    2. Manual Tests: Following the suggested methodologies in this section, go through a series of tests using different tools to find issues in the page or application that is being tested. The recommended routine for manual testing is:
        1. Input: Keyboard
        2. Input: Touch
        3. Visual Presentation
        4. Alternative Text
        5. Audio and Video
        6. Semantics and Document Structure
        7. Forms
        8. Dynamic Content
        9. Custom Widgets
3. Document All Findings in an Accessibility Report Format 
   1. Bring all the findings together into a comprehensive and usable format that allows stakeholders to remediate the issues found based on recommendations provided.
4. Plan for Remediation 
   1. Use testing results to prioritize issues to remediate based on things like business value, risk, severity, etc.
5. Conduct Regression Testing 
   1. Re-run previously run tests to check whether program behavior has changed and whether previously fixed faults have re-emerged.
   
## Where to Begin

You can begin by using an automated tool like aXe DevTools to scan your scoped test units for problems. Automated scans can help identify problems that can be solved easily so you can focus your attention on issues an automated test cannot detect. About 1/3 of problems can be found this way.