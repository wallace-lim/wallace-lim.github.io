---
layout: post
title: "Candidate Tracker Slackbot"
permalink: /project/slackbot
---

## Background
UPE is the CS honors society club at UC Berkeley which focuses on providing academic and professional services such as phone interview, career advice for the CS community. To become a member, an invitation is extended to the top 1/3 CS majors for candidacy. Upon candidacy, specific requirements must be completed in order to initiate and offically become a member.

Prior to slackbot, the officers would keep track of all the requirements for the candidates in a Google Spreadsheet. This proved to be difficult to maintain and a major inconvenience for both the candidates and officers to access as Google Drive tends to be not too organized. This project removes the necessity to maintain the spreadsheet through using slack commands. Slack is the preferred communication tool used to relay messages to both members and candidate so centralizing all information into 1 location can greatly decrease confusion.

## Slackbot
Slack bot originally was designed using Flask running as an AWS Lambda function through the [Zappa](https://github.com/Miserlou/Zappa) package. But to mitigate cost, [OCF](https://www.ocf.berkeley.edu/), a computing facility for clubs, is used instead to host out Flask App.

The commands through the gspread API would access Google spreadsheets and request the necessary information in our spreadsheet, essentially acting as a makeshift database. To communicate with Slack, the [slash command](https://api.slack.com/interactivity/slash-commands) API is used to create custom commands for us to use.

## Commands
Below is a list of all the possible implemented commands
- `/check <candidate>` - looks up a candidate and returns the requirements
- `/checkoff <type> | <candidate>` - checkoff candidate for a candidacy requirement based on type
- `/newevent <type> | <name> | <mm/dd> | <password>` - creates a new event in a spreadsheet with a password for checkoff purposes
- `/challenge <officer first name> | <challenge desc> | <candidate name>` - assigns a challenge given by officer to candidate

## Challenges
Given that this was my first project used by others, I wanted to ensure that the end product sets a high standard displaying my work.

The main challenge in mind is clarity and migration cross semesters. Because UPE is a club, there will be a time where I graduate and would not maintain this app. With that in mind, I wanted a product and proper documentation for future developers to easily pick up this project. I spend hours commenting code and neatly organizing all the python files such that it was clear when forked and added clear documentation into the README for improving this project (See Github link below for documentation). 

In the end this was a project, I'm very proud of and consider it also as my first born into the computing world. Through the advice from my peers and other officers, I really happy that I helped the Berkeley CS community and developed a product that hopefully would create a lasting impact for many semesters to come.

## Links
[UPE Website](https://upe.berkeley.edu/)

[Github](https://github.com/upenu/slackbot)