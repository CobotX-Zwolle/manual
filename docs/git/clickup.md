### Bug reports 
Reporting bugs should happen via Clickup, not directly via github (Clickup can create issues). 
Keeping the data in Clickup allows for a better overview of that status of bugs. 

Use the ```Bugs``` list to create a new ```Task``` in the ```Waiting for Triage``` section.
Steps: <br>

* Give the bug a proper name.
* Set the ```Priority```:
    * Low: No need to look at it for now.
    * Normal: Should be looked at within 2 weeks of reporting.
    * High: Should be looked at within 2 days of reporting.
    * Urgent: Requires being looked at within 2 hours of reporting.
* Set the ```Bug Severity```:
    * Trivial: Bug is not really causing any issues, more a 'nice to have'.
    * Minor: Bug is sometimes causing an issue.
    * Major: Bug is causing or could cause quite some issues. 
    * Critical: Bug is causing or could cause big issues or have impact on performance.
* Fill in ```Reported By```, for now keep this to the person writing the bug Task.
* Environment: Fill in which OS (Ubunt 20/24), Repository name and which branch 
* Steps to reproduce: If available describe how to recreate the bug, e.g. "If the X button was pressed while Y was happening, Z would crash".
* Expected outcome: If possible describe what should happen if the bug would be fixed, e.g. "Z would no longer crash, but an error message should popup on the screen"
* Tags: Add possible tags that belong to this bug (no need to add the tag 'bug' because it's a list of only bugs), e.g. 'ui', 'yaml' 
* Description: Write who reported the bug/issue, e.g. The operator from company ABC reported issue that when he pressed the X button, Z crashed.  
Write in details the information that describes the problem, possible suggestions and/or other information that you think is important to document. 
Does this happen often? Do you think this is related to something else? Was there a recent software update or other changes to the machine?
* Attachments: Add photos or log files that could help with understanding the issue. 
* Github: Create a new Github issue (via Clickup). Set the issue title, select the correct Repository, and label as Bug. The description can be left empty because the information is in Clickup.
* Assignees: If possible assign it to the person(s) who have to work on the Bug, else leave empty 
* Report the bug in the Bugs channel such that every one is aware its created, if a specific person needs to work on it right away than contact that person directly. 

### Task tracking
Currently there are 5 Steps for a Bug: Waiting for Triage, Investigating, In Progress, Testing / QA, Resolved. 

* Waiting for Triage: Task just created, waiting for somebody to start working on it.
* Investigating: The bug requires more information, more information, logs, etc.. 
* In Progress: The bug is being worked on.
* Testing / QA: There is a fix but still requires both testing and QA (Code Review) before it can be resolved. 
* Resolved: The bug has been fixed, tested and approved. 

In the future we can start adding Time Tracking and deadlines 

## Feature request

Use the ```Features``` list to create a new ```Task``` in the ```Not Started``` section.
Steps: <br>

* Give the feature a proper name. 
* Set the ```Priority```:
    * Low: No need to look at it for now.
    * Normal: Should be looked at within 2 weeks of reporting.
    * High: Should be looked at within 2 days of reporting.
    * Urgent: Requires being looked at within 2 hours of reporting.
* Set the ```Feature Impact```: 
    * Low Impact: More a 'nice to have' feature.
    * Medium Impact:  Feature will add some value.
    * High Impact: Feature will have a significant value.
* Feature Complexity: A numerical value representing the complexity of implementing the feature. Values 1 - 10; 1 low complexity, 10 high complexity
* Description: Write a detailed description of the feature request, add documentation if available. 
* Github: If possible create a new Github issue (via Clickup). Set the issue title, select the correct Repository, and label as enhancement. The description can be left empty because the information is in Clickup.
* Assignees: If possible assign it to the person(s) who have to work on the Feature, else leave empty.
* Tags: add possible tags that belong to this feaure (no need to add feature tag, because it's a list of features only), e.g. 'ui', 'yaml' 

### Task tracking
Currently there are 4 steps for a feature: Not started, In Development, Testing, Released. 

* Not Started: Task just created, waiting for somebody to start working on it. 
* In Development: The feature is being worked on. 
* Testing: The feature is in testing phase. 
* Released: The feature has been tested and approved.

In the future we can start adding Time Tracking and deadlines 
