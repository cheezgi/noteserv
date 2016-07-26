#noteserv

This is a simple shell script that sets up a note server using
[Vimwiki](https://github.com/vimwiki/vimwiki). I have tried using solutions
like Evernote and others, but I wanted to be able to use my own text editor to
edit my notes, and organize it how I wanted.

When I fould Vimwiki, I really liked how you could organize your notes however
you wanted. However, typical file sharing solutions like Dropbox were overkill
for something this simple.

##usage

Before editing, sync your notes (to avoid merge conflicts):

```
$ download_linux_osx # you can rename this to whatever
```

Then, go ahead and edit your notes. When you are finished writing, push your
edits to the server:

```
$ upload_linux_osx
```

##setup

###server

The server setup must come first for `noteserv`. Install ssh and git if you
haven't already. The package names may vary depending on your package manager
or operating system.

```
# apt install ssh git-core
```

Then, start the ssh service if you have not already:

```
# /etc/init.d/ssh start
# update-rc.d ssh defaults
```

Take note of the server's IP address:

```
$ ip addr
```

Then, run the relevant setup file for your server:

```
$ setup_linux_osx_server
```

This creates a new user `git` that will handle your repository, and the emtpy
repo itself. This is basically what GitHub does when you create a new repo.

###client

Now that the server is set up, edit the relevant setup script for your client
to contain the details of your server. Before you run it, make sure that the
~/vimwiki directory exists, an index.wiki file exists, and there is not a git
repository already in the directory.

Now you are able to run the client setup script:

```
$ setup_linux_osx_client
```

You're all done! Read the usage section above to learn more.
