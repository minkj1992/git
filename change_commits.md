# Change commit
> when yout want to change commit which you already pushed


## email & author
```bash
git filter-branch --env-filter '
OLD_EMAIL="leoo.j@kakaocorp.com"
CORRECT_NAME="minkj1992"
CORRECT_EMAIL="minkj1992@gmail.com"
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

$ git push -f
```

