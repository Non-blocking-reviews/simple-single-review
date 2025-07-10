# simple-single-review
Github actions to support trunk based development with non-blocking reviews

CURRENTLY MIGRATING A RUNNING SOLUTION TO THIS REPOSITORY.

# Introduction
This repository contains actions that are intended to use a combination of Github actions that allows for non-blocking async code reviews in trunk based development.

Thoughts and reasoning can be found here: [optimizing-software-development-process-continuous-flow](https://www.linkedin.com/pulse/optimizing-software-development-process-continuous-flow-mortensen-ljkhf/)

## Process
- Commit and push to main
- For each commit is created:
  - Author Issue
    - Assigned to author of commit
    - Checked list containing state and link to peer review and list of comments.
  - Peer review 
    - Assigned to all reviewers in list (except author)
    - Link to commit
    - Link to Author Issue
    - Inlined changes if a small change.
- If Peer reviewer adds a comment to a commit, a check list item is added to Author Issue.
- Author issue closes when peer review is closed and all comments have been checked in author issue.

## Setup

### Security 
Current version is in use with organization repository.
It uses an "App" for authorization.
Permissions required for app: (PENDING)

### Issues
The following labels must be created - or the App used should be able to create labels.
- Peer-review
- Commit-issue
- Commented

### Project
- Create a project for code review issues. 
- Get the ID of the project by running "List Project V2 IDs" manually and inspecting output.


## Future features
In addition to a lot ease-of-use improvements the following features are in pipeline: 

- "Reviewed until"-tag that moves ahead with reviews.
- Introduce use of GitNotes to link to reviews or reviewers

