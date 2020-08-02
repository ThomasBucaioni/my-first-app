# Toto the Bot

Hello, I'm **Toto the Bot**. 

Every day a propose one of [John Bercow](https://www.brainyquote.com/authors/john-bercow-quotes)'s most famous quotes:

> If you asked me if I'd rather be Speaker or a very senior minister, I'd say Speaker.



***

1. [SSH](https://docs.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh)
2. `script.sh`
```
curl https://www.brainyquote.com/authors/john-bercow-quotes | awk  -F '[<>]' '/<a href.*john_bercow_.*quote/ {print $1 $3}' | sed s/\&#39\;/\'/g | sed s/\\.\'/\./g > /tmp/john_bercow.txt
my_max_lines=$(wc -l "/tmp/john_bercow.txt" | cut -d' ' -f1)
my_rand=$((1 + RANDOM % my_max_lines))
my_quote=$(sed "${my_rand}q;d" /tmp/john_bercow.txt)
sed -i "7s/.*/> $my_quote/" /home/user/github/my-first-app/README.md

cd /home/user/github/my-first-app/
pwd

ssh-agent
ssh-add ~/.ssh/id_rsa_github

git add -A
git commit -m "reload quote"
git push
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

