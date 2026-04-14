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

In the `config_defaults.json` file there is a section like this:
```py
{
"textmatch_backend":      "tfidf",
"likely___Punishment":    "warn",
"dangerousPunishment":    "mute",
"deleteLikelyMessage":     false,
"deleteDangerousMessage":  true,
"tooManyChannelsSpammed":  3,
"stopPayingAttentionToUserAfterThisAmountOfSeconds": 30,
"debugUsers": [270149861398151169]
}
```

- *textmatch_backend* possible values are `tfidf` (which is more accurate) and `fuzz` (which is more performant).
- *likely___Punishment* and *dangerousPunishment* possible values are `nothing`, `warn`, `mute`, `kick`, or `ban`, which applies that punishment to the offending user depending on if the message is likely to be a scam, or very likely (dangerous).
- *deleteLikelyMessage* and *deleteDangerousMessage* determine if the offending post gets automatically deleted or not. Their possible values are `true` and `false`.
- *tooManyChannelsSpammed* is the number of channels needed to be spammed in by a user within a certain timeframe for a likely match to be elevated to dangerous. This value needs an integer.
- *stopPayingAttentionToUserAfterThisAmountOfSeconds* is the timeframe where the bot will pay attention to if a user will send messages in other channels, which can lead to *tooManyChannelsSpammed* and thus a likely match being elevated to a dangerous one. This value needs an integer.
- *debugUsers* is a list of user ids which will not be punished when detected, for use of testing the scam spam matcher.

Changing `config_defaults.json` will change the default for all Discords with the bot. To change it for a specific user, use the `/change_settings` command.
