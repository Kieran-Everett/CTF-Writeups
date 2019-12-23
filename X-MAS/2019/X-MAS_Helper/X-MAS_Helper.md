# X-MAS Helper

![chall]

This challenge focuses on a Discord bot called X-MAS Helper in the CTF's Discord server. 

Along with some basic information about the challenge, some code Python code is provided which is the code for the `!flag` command, the command that needs to be exploited. This code is absolutely useless to know.

To complete this challenge all you need to do is enable Developer Mode in Discord which is in User Settings > Appearance > Advancded. This will allow you to right-click the bot in the user list of the server and copy its' ID. Next, open a browser and enter `https://discordapp.com/oauth2/authorize?client_id=<Bot_Client_ID>&scope=bot&permissions=0` (replace <Bot_Client_ID> with the bot's ID) and invite it to one of your own servers. Then create and give yourself the `Organizer` role and then just say !flag in your server and it will reply with the flag: `X-MAS{FREE_FLAGS_FOR_EVERYONE}`

## Closing thoughts on the challenge

This was a fairly easy challenge to complete but without prior knowelege on how to add bots from another server to your own makes the challenge significantly harder. I managed to complete this challenge in 30th, 3 hours and 6 minutes after release.



[chall]: challenge.png "Challenge screenshot"
