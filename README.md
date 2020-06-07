# repo tool

## bundling the original git repo

```
$ git clone --mirror https://gerrit.googlesource.com/git-repo
$ cd git-repo
$ git bundle create /tmp/git-repo.git --all --tags --remotes
$ cd -

$ git clone git@github.com:Rubusch/repo.git my-repo
$ cd ./my-repo
$ git remote -v
    origin [...] (fetch)
    origin [...] (push)
$ git remote add community /tmp/git-repo.git
$ git fetch --all
$ git checkout stable
$ git pull community stable --ff-only
$ git push origin --tags

```



## example:

```
$ cat ./default.xml 
<manifest>
        <remote name="oe" fetch="https://github.com/openembedded/meta-openembedded.git" />
        <default revision="master" remote="oe" />
        <project name="meta-openembedded" remote="oe" path="meta-openembedded" />
</manifest>
```

```
$ repo init --manifest-url=git@github.com:Rubusch/repo.git --repo-url=git@github.com:Rubusch/repo.git --no-repo-verify

$ repo sync
```

FIXME: seems to scramble and concat the url somehow...


