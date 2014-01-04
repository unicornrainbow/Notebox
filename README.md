# Notebox

Capture your ideas in an open, free and private format. Notebox is a command
line tool that lets you create, store and retrieve notes--no strings attached.

## Installation

Install to `/usr/local/bin/nbx`. Or copy and paste:

    curl -Sso /usr/local/bin/nbx \
        https://raw.github.com/blakefrost/notebox/master/bin/nbx; \
    chmod +x /usr/local/bin/nbx

## Getting started

### Initialization

The first thing you should do is initialize Notebox.

    $ nbx init

This simply makes sure the Notebox notes directory exists. This directory is
where Notebox stores all of your notes. The default is `~/Notebox/notes`, but you
can configure it to any directory by setting the `NBX_NOTES_ROOT` environment
variable.

Feel free to take a peek in this directory. Files will be stored within it
according to the Notebox Format described below.

### Creating a note

Use the `new` command to create a note. This will open a new unsaved note inside
your editor.

    $ nbx new

Save the file to save the note. Exit the editor when finished.

### Listing notes

Use the `ls` command to list notes. This will show notes in reverse
chronological order.

    $ nbx ls

### Topics

You can create and list notes within a certain topic by passing a topic as the
first argument.

    $ nbx new topic
    $ nbx ls topic

Topics can be nested.

    $ nbx new topic/subtopic
    $ nbx ls topic/subtopic

### Grep

Grep notes with the `grep` command.

    $ nbx grep keyword

### Editing notes

Edit the most recently created note with the `last` command.

    $ nbx last

This can also be scoped to a topic.

    $ nbx last topic

Edit any note by opening it in your text editor.

### Git support

Notebox has built in git support. Enable it by passing `init` to the Notebox
`git` command to initialize the git repository.

    $ nbx git init

You can pass any command you would otherwise pass to git to `nbx git` and it
will affect the Notebox git repository specifically.

Once enabled, `nbx new` and `nbx last` will automatically generate create and
edit commits respectively.

You can see all commits with the `log` command.

    $ nbx log

You can pass the path to a specific note to get the git log for just that note.

    $ nbx log <filepath>

Since Notebox is being tracked in a git repository, it's easy to add a git
remote and push to it for replication and backup.

See `nbx help` for more information.

## Notebox Format

The **Notebox Format** is a core part of the magic that makes Notebox work. This
is, by virtue, an open format, and it's meant to be understood and of benefit to
the user.

The Notebox Format specifies that all new files (individual notes), be stored in
a directory reflecting the current date.

For example: Notes from December 4th 2013 would be stored in `entries/2013/12/04`.

Within that directory, the file is stores according to a timestamp of when the
file was generated, and can carry any file extension.

Example: `entries/2013/12/04/12:23:25.txt`.

By storing notes, or anything in this manner, you're always left with a spot for
a new note. It also makes it easy to merge notes gathered from different
sources.

This format easily checks into git, and doing so provides yet another
dimension with means to track changes to temporal files over time.

Considering the format is well known, local and plain text, you can always
switch tools and take your notes wherever you go. Notes are private, and never
leave you system unless you tell them too.

## Contributions

Notebox is a tool that has evolved over time to help me collect my own thoughts.
It's finally reaching a point where I think it can be useful to others. I think
of data emitted from Notebox as a film negative of sorts, and the Notebox tool
of today as a primitive version of what it could ultimately be. New, and
alternative ways to capture, convert, copy, share, explore or digest information
are only some of the ways in which this system could become more useful in the
future.

Please take what's here, and figure out what might be useful to you. If you have
something to contribute back, please do.

Pull requests will be reviewed and merged accordingly.

## License

### This code is free to use under the terms of the MIT license.

Copyright (c) Blake Taylor 2014

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
"Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be included
in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
