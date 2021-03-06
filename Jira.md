# Using Jira for Coordinating Development #

KBase uses Jira for trouble tickets, as well as tracking work during sprints. For the implementation team, a sprint based approach is used with 3 weeks sprints, daily standups, and use of Jira Sprint boards for tracking work. The KBase Jira instance is currently accessed at https://kbase-jira.atlassian.com

## Sprint Board ##

The sprint board can be found at https://kbase-jira.atlassian.net/secure/RapidBoard.jspa?projectKey=TASK&rapidView=5

This board is used for queueing and tracking work that is being done within a sprint.

## Jira Tickets ##

A Jira ticket should be created for tasks that are being worked on. Generally the tasks will be part of a backlog that is negotiated by the Implementation and Product teams,
however team members that start work on non-trivial tasks that do not have a Jira ticket
should create a Jira ticket in the current sprint for the new work.

### Jira and Github ###

Jira has integration with Github, and repos which are known to Jira will have their commit
messages parsed and the state of the code will be tracked in the Jira ticket.

This integration is described here:
https://confluence.atlassian.com/adminjiracloud/connect-jira-cloud-to-github-814188429.html

To initiate Jira tracking, as part of your git commit message include the Jira refer
in your commit message. For example, if a commit id related to Jira ticket TASK-674
( https://kbase-jira.atlassian.net/browse/TASK-674 ), you would include the "TASK-674"
in the commit message.

Here is an example of entering a commit message that ties a commit to Jira ticket TASK-704:
![Git commit referencing TASK-704](images/GitCommitJiraLink.png "Commit message linking to jira ticket TASK-704" )

It is possible to transition your Jira ticket to/from different states in the workflow by
include #state after the ticket reference. For example, to close Task 674 you would include
the following in the commit message that closes the ticket:
"TASK-674 #close"

Here is a longer document that explains the feature:
https://confluence.atlassian.com/jirasoftwarecloud/processing-issues-with-smart-commits-788729666.html

As commits are made, they are tracked in the Jira ticket. If a pull request comment
references a Jira ticket, it is also tracked in the Jira ticket, as well as the flow
of that particular commit through various merges.

For example, if you check the "Development" section of this Jira ticket, you will find the
commits and the status of the pull request as it gets merged into different branches. This
makes it much easier to track the flow of fixes and feature requests as they propagate
through the different branches.
https://kbase-jira.atlassian.net/browse/TASK-674
![Development Panel in Issue](images/JiraGithubIntegration.png "Development Panel in Jira Ticket" )
![Branches Popup in Issue](images/JiraGithubPRTracking.png "Branches popup in Jira Ticket" )