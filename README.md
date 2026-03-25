# OpenAntiScamSpam aka oASS
A simple open-source Discord bot for detecting and handling scams being spammed.

# How to Use?

Create a [bot for Discord](https://discord.com/developers/applications), and go get it's token. Then invite the bot to whatever Discord you have control over.

Create a `.env` file in the directory with:
```
DISCORD_BOT_TOKEN=your_token_here
```

Make sure you have [Python installed](https://asnake.org/docs/installing%20python.html), and [install ASnake.](https://asnake.org/docs/installing%20asnake.html)

When in the directory, install all the requirements needed:
```
pip install -r requirements.txt
```

And then to run the bot:

```
ASnake -r main.asnake
```

## How to configure?

In `main.asnake` there is a section like this:
```py
# config
str likely___Punishment = 'warn' # nothing, warn, mute, kick, ban
str dangerousPunishment = 'warn'
bool deleteLikelyMessage    False
bool deleteDangerousMessage True
```
You can set punishment as nothing, warn, mute, kick, or ban depending on if the message is labeled likely-dangerous, or dangerous.
`deleteLikelyMessage` and `deleteDangerousMessage` control if the offending message is deleted after punishment.
