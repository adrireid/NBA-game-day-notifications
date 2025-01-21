# NBA-game-day-notifications

NBA Game Day Notifications 

Overview

This project is a game day notification system that sends NBA game day scores via notifications to subscribed users via Email or Text message. The system utilizes Amazon SNS, AWS Lambda  Amazon EvenBridge, NBA APIs, and Python to successfully execute.

Features

Fetches live NBA game scores using an external API every 2 hours to send updates to users.
Sends formatted score updates to subscribers via SMS/Email using Amazon SNS.
Scheduled automation for regular updates using Amazon EventBridge.


Technology Architecture

![gdn](https://github.com/user-attachments/assets/a31fde4e-f914-4885-ab81-840e722a813b)

Steps Taken 

Created account on Sportsdata.io to receive API key to later utilize to set up Lambda. 
Created SNS topic that would pull data from the NBA API to the subscribed users. 
Set up Lambda and utilized python code to add in which information I wanted to pull from the NBA API such as the teams playing, the score by quarter, and the channel the game was being shown on. 
The Final step was to schedule the notifications using event bridge. 

I created a new recurring schedule pattern and defined a cron expression that would pull game data from 9 am - 2 am the following day every 2 hours. (I recommend using chatgpt to help you build your schedule for this) 

Success I waited for the event trigger on the schedule I set up for which was every 2 hours and received the notification via email. 

Future goals: I plan to update the code to clearly display which team won in the final score. 

Challenges

While building this API I ran into a few minor challenges. 

Received error messages when attempting to run test 

1st error:  error fetching data, I viewed the API Key inputted to realize I put in the incorrect code and updated, passed 

2nd error: Error publishing to SNS, upon reading the error, error stated are should start with “arn” not “  arn” in the log it appears that was a space before “arn”. Updated, 

3rd attempt success!!! Best message I’ve ever seen “data processed and sent to SNS’

Checked the email used to sign up for notifications and…..BOOM it works and notifications were sent to the email subscribed to my game day API 



