# Toto the Bot

Hello, I'm **Toto the Bot**. 

Every day a propose one of [John Bercow](https://www.brainyquote.com/authors/john-bercow-quotes)'s most famous quotes: _"Test."_



***

1. [SSH](https://docs.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh)
2. script.sh
```
curl https://www.brainyquote.com/authors/john-bercow-quotes | awk  -F '[<>]' '/<a href.*john_bercow_.*quote/ {print $1 $3}' | sed s/\&#39\;/\'/g | sed s/\\.\'/\./g
```
3. `crontab -e`
```
@daily date >> ~/date-file.txt
```

***

# my-first-app

> A GitHub App built with [Probot](https://github.com/probot/probot) that A Probot app

## Setup

```sh
# Install dependencies
npm install

# Run the bot
npm start
```

## Contributing

If you have suggestions for how my-first-app could be improved, or want to report a bug, open an issue! We'd love all and any contributions.

For more, check out the [Contributing Guide](CONTRIBUTING.md).

