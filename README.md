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

In the `config.json` file there is a section like this:
```py
{
"textmatch_backend":      "tfidf",
"likely___Punishment":    "warn",
"dangerousPunishment":    "warn",
"deleteLikelyMessage":     false,
"deleteDangerousMessage":  true
}
```

*textmatch_backend* possible values are `tfidf` (which is more accurate) and `fuzz` (which is more performant).
*likely___Punishment* and *dangerousPunishment* possible values are `nothing`, `warn`, `mute`, `kick`, or `ban`, which applies that punishment to the offending user depending on if the message is likely to be a scam, or very likely (dangerous).
*deleteLikelyMessage* and *deleteDangerousMessage* determine if the offending post gets automatically deleted or not. Their possible values are `true` and `false`.
