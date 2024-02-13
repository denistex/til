# Registers

Vim features registers for yank/put operations and recording commands.

To copy text to a register, type `"{register}{yank}` where `{register}`
is a register name (lowercase a-z) and `{yank}` is one of many possible
yank commands: `yas` to yank a sentence, `3yy` to yank three lines, etc.

It is possible to specify a register for the delete operation as well:
`"wdaw"` will delete a word and write it to the `w` register.

To put text from a register, type `"{register}p`.

There is a special register `*` that represents the system clipboard:
`"*dd` will delete a line and write it to the clipboard and `"*p` will
put it back. However, not all versions of Vim support that.

It is also possible to append text to a register by using uppercase
register names, for example, `"Ayy"` will append a line to the `a`
register.

To write a sequence of keystrokes to a register, type
`q{register}{commands}q`. The `{commands}` will be saved to the register
and it is possible to replay them with `@{register}`. The latest
replayed keystroke can be repeated with `@@`.

Now the interesting part: it is possible to edit the recorded commands
by putting them to the current file from a register, editing as regular
text and yanking back to the register. For example, to edit commands
saved in the `n` register, paste them to the file: `"np`, then edit the
text and yank it back: `"ny$`. Now the updated keystrokes will be
applied by typing `@n`.
