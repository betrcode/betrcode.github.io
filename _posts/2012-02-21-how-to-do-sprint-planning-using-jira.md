---
layout: post
title: "How-to do Sprint Planning using Jira"
tags: [agile, scrum, jira]
---
I have been using Jira for many years and have worked as a Scrum Product Owner for a few years. I have managed multiple teams, based in different parts of the world. This is my guide to using Jira as a Sprint Planning tool.
<!--more-->

### When to use a web-based tool instead of a wall board (whiteboard)

* When you have distributed teams
* When you want to work on your tasks from multiple locations
* When you need to share information with outside stakeholders (like customers)

If you have a simpler scenario, try using the simplest tool possible for your task tracking, like a whiteboard.

![Jira screenshot](/images/jira-screenshot-300x258.png)

### Before Sprint Planning
It's the job of the Product Owner to keep the Product Backlog groomed & ordered. The items on top of the backlog should be well enough specified so that they can be moved into a Sprint Backlog. This work is ongoing and often means talking to stakeholders a lot.

Before Sprint Planning I prepare one Jira "bucket" per team. Usually I use one Jira "Version" for each Sprint and add a custom field ("Sprint Team") to track which team a specific issue belongs to.

I fill the buckets with issues I find suitable for each team until there's more than enough issues for each team. How do I know how much is enough? Past performance. Do I have estimates on all issues? No, usually not. Perhaps on some.

This results in a **preliminary** Sprint Backlog. This is not the final Sprint Backlog, but only a suggestion.

I usually juggle a bit with the ordering (prioritization) to make sure the most important issues are on top. Also, if there are any bigger or riskier issues, I move them up the list so they are handled early in the Sprint.

A few days before the Sprint Planning meeting I send out links to the preliminary backlog to the teams. At this time, the suggestion for next iteration should be pretty stable, but changes can still occur.

This enables the team to:
* Review the issues in advance (makes for a quicker and less painful Sprint Planning meeting)
* Give me feedback on poor priotization, poor team choice etc

#### Managing left-overs
Hours before the Sprint Planning meeting I kick any unfinished issues from the current Sprint into the preliminary Sprint Backlog for the upcoming Sprint. If there are issues that are not valid any more, I close them with "Won't fix" or similar resolution. Issues that have been started are usually given a higher priority. ("Stop starting, start finishing") The full remainder from current Sprint does not necessarily make it to the top of the list for the upcoming Sprint. Priorities change and new things pop up.

### During Sprint Planning meeting
It is the job of the Scrum Master to send invites to the Sprint Planning meeting. The Product Owner is just there to clarify the backlog and answer questions. I try to take a backseat position here if possible and let the team drive the planning as much as possible.

Since the teams are often distributed in different parts of the world we usually use Skype for voice and some screen sharing software to display Jira.

Quick overview of Sprint Planning process using Jira:

* Display list of issues (preliminary Sprint Backlog) in Jira and talk about the overall goal of the Sprint
* For each issue in the list:
1. Team reads the issue
2. Team discusses the issue and asks the PO when in need of clarification
3. Team estimates the issue using Planning Poker or similar technique. Estimation is entered as "Time Remaining" in Jira. (or if estimation is done in "Story Points", in some other suitable Jira field)
4. When the team feels that they have enough issues to fill a Sprint, the process ends. This is usually done by summing up the "time remaining" on the issues in the Jira "bucket" and when that sum reaches what the team usually manages (their velocity), then they know they have enough. Please note that summing up "Original Estimate" is not a good idea if you have work-in-progress left-overs from last Sprint.

### After Sprint Planning
Directly after Sprint Planning I kick all issues that didn't make the cut to the next version so that the teams bucket only contain what they have committed to for the new Sprint. Then I send a Jira link to the stakeholders so they can see exactly what the new Sprint Backlog contains. I may only send them a list of the issues that didn't make the cut if I know they were expecting some specific issues.

I usually have some Jira filters for each Sprint to make it simple for the teams to know what issues to work on. I update these for the new Sprint.

Here are some example filter names:

* Current Sprint - TODO - Team A
* Current Sprint - TODO - Team B
* Current Sprint - TODO - Team C
* Current Sprint - TO TEST - Team A
* Current Sprint - TO TEST - Team B
* Current Sprint - TO TEST - Team C

You can probably figure out what these filters show...

### Closing thoughts and further reading
![Jira Admin Ninja Black, courtesy of Atlassian](/images/jira_admin_ninja_black.png)

I hope this guide gives you some idea how you can make it work. If you wish to read more about Jira in general, visit [Atlassians Jira section](https://www.atlassian.com/software/jira). If you are unsure of the Scrum terminology used here, or just want to know more about Scrum, check out [What is Scrum at Scrum Alliance](https://www.scrumalliance.org/why-scrum).
