# repo tool

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
$ repo init -u git@github.com:Rubusch/repo.git --repo-url=git@github.com:Rubusch/repo.git --no-repo-verify
$ repo sync
```

FIXME: seems to scramble and concat the url somehow...


