GitReleaseNotes
==============

Utility which makes it really easy to generate release notes for your Git project. Works with GitHub, Jira and YouTrack. TFS Support coming soon

## Install

    cinst GitReleaseNotes

This will use [Chocolatey](http://chocolatey.org) to install GitReleaseNotes into your %path%, ready to be used for any project

## Usage
GitReleaseNotes must be run inside a git repository.

    GitReleaseNotes.exe /OutputFile ReleaseNotes.md

This will write `ReleaseNotes.md` into the root of your repo, the release notes are generated by:

 - Use the git remote to connect to your issue tracker (if possible, i.e issue tracker is GitHub)
   - Otherwise specify the issue tracker on the command line (`/IssueTracker Jira /Server MyJiraServer` as well as project name, check `/?` for more info)
 - Find closed issues since the last release and generate your release notes
 - Use /allTags to generate complete release notes for all releases
 - If the release notes are already generated, GitReleaseNotes will *append* **new** closed issues to your release notes, meaning all custom edits will be retained
 - Writes out the release notes following [SemanticReleaseNotes.org](http://www.semanticreleasenotes.org/)

You can also use GitReleaseNotes to create a GitHub release, and generate the release notes automatically allowing fully automated releases including release notes generation.

If you use GitHub milestones to manage your releases [GitHubReleaseNotes](https://github.com/Particular/GitHubReleaseNotes) is a similar project.

## Versioning a release
[GitVersion](https://github.com/Particular/GitVersion) is another project which can help you generate version numbers and make following Semantic Versions easily
