---
title: Get source
---

BioJava now using SVN
=====================

BioJava has moved the version control system from CVS to Subversion
(svn). All Biojava modules, branches and tags and the history of the
files has been imported into the new repository.

### how future checkouts will work

For a developer the CVS checkout will look like this:

`svn co svn+ssh://dev.open-bio.org:/home/svn-repositories/biojava/biojava-svn/biojava-live/trunk/  ./biojava-live`

after initial checkout, you can change into the local ./biojava-live
directory and execute SVN commands without the URL. For example:

`svn update`  
`svn commit -m "comments for this commit"`  
`svn add myfile.java`

If your local user name is different from the one one the open-bio
server you can edit

`~/.ssh/config`

and add

`host dev.open-bio.org`  
`user blablabla`

see also the [SVN developers page in the OBF
wiki](http://www.open-bio.org/wiki/SVN-Developers)

We will also continue to provide anonymous checkouts and a browsable
interface to the repository. Information how to obtain an anomymous
checkout will become available soon.

History of the update procedure
-------------------------------

for more detailed documentation about the procedure used for the CVS to
SVN migration see [SVNmigrationHistory](SVNmigrationHistory "wikilink")