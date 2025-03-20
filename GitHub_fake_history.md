```
git filter-branch --env-filter '
 
OLD_EMAIL="giri.shashank19@gmail.com"
CORRECT_NAME="codegenius2"
CORRECT_EMAIL="lucifer231220@gmail.com"

if [ "$GIT_COMMITTER_EMAIL" = "$OLD_EMAIL" ]
then
    export GIT_COMMITTER_NAME="$CORRECT_NAME"
    export GIT_COMMITTER_EMAIL="$CORRECT_EMAIL"
fi
if [ "$GIT_AUTHOR_EMAIL" = "$OLD_EMAIL" ]
then
    export GIT_AUTHOR_NAME="$CORRECT_NAME"
    export GIT_AUTHOR_EMAIL="$CORRECT_EMAIL"
fi
' --tag-name-filter cat -- --branches --tags
```

```
git commit --amend --date="YYYY-MM-DD HH:MM:SS"
```

```
npx fake-git-history --startDate "2020/09/01" --endDate "2020/09/30" --workdaysOnly --commitsPerDay "0,5"
```