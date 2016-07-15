# Git with Multiple Remotes

You can add multiple push remotes to git so you can push your repositories to multiple places for backup or other purposes.

    git remote set-url --add --push origin git://original/repo.git
    git remote set-url --add --push origin git://another/repo.git

Some consider it best practice to keep origin as just where you pull from though and instead add an additional push location called all.

    git remote add all git://original/repo.git
    git remote set-url --add --push all git://another/repo.git
