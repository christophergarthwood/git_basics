# GIT GENERAL PROCESS

`git add/commit/push/stash`   #whatever local changes you have in your branch

`git checkout master/main`

`git pull`

`git checkout <your branch>`

`git merge master/main`       #now you're 100% up to date

TEST TEST TEST TEST TEST!!!!!

`git push`                    #these changes from master inside your branch up

`git checkout master`

`git pull`                    #one more time on master to ensure you're up to date.

`git merge <your branch>`     #now you have a local copy of master on your system

TEST TEST TEST TEST TEST!!!!!

git push`                    #now the central repo's master is up to date and has been tested

# GIT alias

`alias git_report="git log --graph --decorate --pretty=format:'%C(yellow)%h %Cred%cr %Cblue(%an)%C(cyan)%d%Creset %s' --abbrev-commit |head -40"`

`alias git_tags="git log --no-walk --tags --pretty='%h %d %s' --decorate=full"`

`alias show_versions="git log --no-walk --tags --pretty='%h %d %s' --decorate=full"`

# GIT CLEAN EVERYTHING (Dangerous)

`git clean -fd`

# GIT RESET

`git reset --hard`

# GIT NUKE

`git clean -fd`

`git reset --hard`

# GIT SQUASHING

If you've ever made a lot of commits locally and wish there was a way to smash them all down into a single commit, you're in luck. Git calls this concept "squashing commits."

`git rebase -i HEAD~2`

You'll be prompted with a message showing each commit. 

`pick 718710d Commit1.`

`pick d66e267 Commit2.`

Put the word squash in front of the commit you want to be absorped into the other.

`pick 718710d Commit1.`

`squash d66e267 Commit2.`

# GIT REMOVE COMMIT

See squash but put `drop` in front of the choice you want removed.

# GIT REPO CRASHING

`chown -R me:me *`

`chmod -R ugo+rx *`

`git fsck`               #performs a file integrity check

`git prune`              #an internal housekeeping utility that cleans up unreachable or "orphaned" Git objects

`git repack`             #combine all objects that do not currently reside in a "pack", into a pack. 

                       #It can also be used to re-organize existing packs into a single, more efficient pack.

`git fsck`

# GIT LOG

Log Reference [https://www.atlassian.com/git/tutorials/git-log]

`git log --graph --oneline --decorate`

#limit output

`git log --graph --oneline --decorate -10`

# GIT PERMISSIONS

Set execute bit on a file `git add install.sh --chmod=+x`

# GIT SSL ISSUES

http.slCAPath or http.sslCAInfo. Adam Spiers's answer gives some great examples. This is the most secure solution to the question.

To disable TLS/SSL verification for a single git command try passing -c to git with the proper config variable, or use:

`git -c http.sslVerify=false clone https://example.com/path/to/git`

To disable SSL verification for a specific repository, if the repository is completely under your control, you can try:

`git config http.sslVerify false`

There are quite a few SSL configuration options in git. From the man page of git config:

http.sslVerify

Whether to verify the SSL certificate when fetching or pushing over HTTPS.  Can be overridden by the GIT_SSL_NO_VERIFY environment variable.

http.sslCAInfo

File containing the certificates to verify the peer with when fetching or pushing over HTTPS. Can be overridden by the GIT_SSL_CAINFO environment variable.

http.sslCAPath

Path containing files with the CA certificates to verify the peer with when fetching or pushing over HTTPS.  Can be overridden by the GIT_SSL_CAPATH environment variable.

A few other useful SSL configuration options:

http.sslCert

File containing the SSL certificate when fetching or pushing over HTTPS.  Can be overridden by the GIT_SSL_CERT environment variable.

http.sslKey

File containing the SSL private key when fetching or pushing over HTTPS.  Can be overridden by the GIT_SSL_KEY environment variable.

http.sslCertPasswordProtected

Enable git's password prompt for the SSL certificate. Otherwise OpenSSL will prompt the user, possibly many times, if the certificate or private key is encrypted.  Can be overridden by the GIT_SSL_CERT_PASSWORD_PROTECTED environment variable.

# SUBVERSION LOG
Show descending values, last 10 only `svn log -r HEAD:1 -l 10`

# SUBVERSION on DSRC

`module load costinit`

`module load subversion`
