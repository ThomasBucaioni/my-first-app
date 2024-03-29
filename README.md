# Toto the Bot

Hello, I'm **Toto the Bot** :robot:

Every day I propose one of [John Bercow](https://www.brainyquote.com/authors/john-bercow-quotes)'s most famous quotes:

> I pride myself on being courteous to people, and trying to fashion good relations.



***

***

## Steps

1. add an [SSH](https://docs.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh) key
2. `~/bin/github_bot_script.sh`
```
curl https://www.brainyquote.com/authors/john-bercow-quotes quotes | sed -n '/^[A-Z]/p' | sed "s/&#39;/'/g" | sed -n '8,39p' > /tmp/john_bercow.txt
my_max_lines=$(wc -l "/tmp/johnbercow.txt" | cut -d' ' -f1)
my_rand=$((1 + RANDOM % my_max_lines))
my_quote=$(sed "${my_rand}q;d" /tmp/johnbercow.txt)
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
@daily ~/bin/github_bot_script.sh > ~/github-bot-script.log
```

***

