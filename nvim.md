# NeoVim
<hr>


<!-- Keybindings -->

## Keybindings:

Tutorial: **:Tutor**



### Copy Paste:
for some reason only "nvim" opened files will copy to clipboard????

ctr shift v (paste from arch clipboard) <br>

v (visual) <br>
y (copy) <br>
yy (copy line) <br>
:%y+ (copy whole file into clipboard) <br>

p (paste) <br>
P (paste line before) <br>
	
*Copying to clipboard (Arch):* <br>
installed wl-clipboard <br>
set clipboard+=unnamedplus (init.vim, always copies to clipboard) <br>



### Split Screen:
ctr w h 
(h j k l: move to left down up right window)



### Moving cursor:
h j k l (left, down, up, right) <br>
w (beginning next word) <br>
e (end next word) <br>
0 (beginning line) <br>
$ (end line) <br>

gg (beginning document) <br>
G (end document) <br>
	
H (top of page) <br>
M (mid of page) <br>
L (bottom/low of page) <br>
	
zz (curr. line center) <br>
zt (curr. line top) <br>
zb (curr. line bottom) <br>

ctl f (forward page) <br>
ctl b (backward page) <br>



<!-- Editing -->

## Editing
#### Substitute
:[range]s/{string}/{string}/[flags] [count] <br>
you can use other single-byte characters instead '/' (but not alphanumeric character '\', '|', '"')
range: <br>
% (whole file) <br>
. (current line) <br>
$ (end of file) <br>
otherwise just enter two numbers seperated by comma <br>
flags: <br>
g (replace all) <br>
c (confirm each replace) <br>
- y (replace) <br>
- l (replace and quit) <br>
- n (skip) <br>
- q (quit) <br>



<!-- Buffers -->

## Buffers
<https://linuxhandbook.com/vim-buffers/>

:edit 
:e
(opening buffers, in active buffer)

:badd
(opening buffers, in background)

:split 
:sp 
:vsplit 
:vs 
:hsplit
:hs
(splitting buffer, and opening if not open)

:ball
:vertical ball
(open all buffers in spearate windows)

:bdelete
:bd
(delete buffer)

:buffer
:b
(switch to buffer)

:bnext
:bn
(switch to next buffer)

:bprevious
:bp
(switch to previous buffer)

:bfirst
:blast
(switch to first, last buffer)

:set hidden
(save changes in buffer, without writing, good for switching between buffers)

#### List buffers
:ls
:files
:buffers
(list buffers)

- % : buffer in current window
- # : Alternate buffer (last file edited in current window)
- a : Acitve buffer
- h : hidden buffer (unsaved changes, not displayed in any window)
- u : unlisted buffer (not open in vim, but exists in cwd)
- - : buffer with modifiable set off
- = : readonly buffer
- + : unwritten changes
- X : read errors buffer



<!-- Windows -->

## Windows
<https://www.baeldung.com/linux/vim-windows>

vim -o filename filname ...
(opens files in separate windows in vim, horizontally)

vim -o[N] filename filename ..
(opens files in vim, but separate windows only for N first files)

vim -O filename filename ...
(opens files in separate windows in vim, vertically)

:new
(create new buffer, in new window)

:vnew
(create new buffer, in new window, vertically)

:q
(quits vim)

:close
(closes window)

:only
:on
(closes all other windows)



<!-- Tabs -->

## Tabs
<https://www.linux.com/training-tutorials/vim-tips-using-tabs/>

Opened and closed files are stored in buffers.
Multiple windows allow you to simultaneously view multiple buffers.

A tab can contain multiple windows, i.e. its like a layout.

:help tab-page-intro
(displays tutorial for tabs)

vim -p file1 file2 ...
(opens files in multiple tabs)

:tabnew
(opens new tab)

:tabf filename
(searches file in current directory, opens it in new tab)

:tabfir
(jump to first tab)

:tablast
(jump to last tab)

:set showtabline=X
(X=0 or 1 or 2, 0 -> never show tabline, 1 -> if mult. tabs open, 2 -> always)

:tabs
(shows tabs)

:tabm X
(movew tab to position X in tabline, indexing from 0)

:tabdo command
(does same command in all tabs)



<!-- Sessions -->

## Sessions && Views
<https://learnvim.irian.to/basics/views_sessions_viminfo>

### Views
Views are smaller then sessions.

Stored in: 
~/.local/state/nvim/view/


### Sessions
Stored in directory

:mksession PATH 
(saves current state of vim session)

:source PATH 
(opens state of a session)

vim -S nameSession.vim 
(opens state of a session)

:qa 
(closes everything, all buffers etc)



<!-- Folding -->

## Folding

:help folding

:mkview 
(save folds to close vim)

:loadview
(load folds)

### create & delete
zF 
(create fold)

:{range}fo 
(create fold)

zd 
(delete fold at cursor)

zD 
(delete folds recursively)

zE 
(eliminate all folds in window)

### open and close
zo 
(open fold under cursor)

zO
(open all folds under cursor)

zc
(close one fold under cursor)

zC 
(close all folds under cursor)



<!-- Marks -->

## Marks
<https://vim.fandom.com/wiki/Using_marks>

marks in a file can be: a-z

global marks can be : A-Z

ma 
(sets mark "a")

'a 
(jumps to first character of line of a)

`a 
(jumps to line and column of a)

:marks 
(outputs marks)

:delmarks a 
(delete mark a)

:delmarks a-d
(delete marks a, b, c, d)

:delmarks! 
(delete all lowercase marks from current buffer)

### special marks

`. 
(jump to last change in current buffer)

'' 
(jump back from where jumped)

`` 
(jump back to position where jumped from)


<!-- Packages -->

## Packages
~/.config/nvim

confPath/pack/\*/start/\* 
will be loaded automatically

confPath/pack/\*/opt/\* 
can be loaded with :packadd
