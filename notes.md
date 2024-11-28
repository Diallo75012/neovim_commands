#####  My car is VrimVriming!

 how to delete:
Being in <Esc> mode: move cursor in the character to delete and press <x>.

# how to insert:
- normal insert: press <i> and insert at the cursor level and use <h, j, k, l> to move cursor <left, down, up, right>
- append insert: press <a> and you will see down there '--INSERT--' and you do the same as when using <i>

# Quit 
use <Esc> then <:q!> , it tried without the '!' and it worked... soooo...

# to Write to file
use <Esc> then <:wq!> .. i tried without the '!' and it worked...

# to come back to beginning of line
use <0> to come back at the beginning of the line

# to replace a character
use <r> on the character to replace and then type your character .
From the <Esc> mode and then will return <Esc> mode.

# delete a full line
use <dd> to delete a full line

# past a line under where your cursor is from a deleted line
use <dd> to delete a line and paste it somewhere else using <p> (called 'PUT' not 'paste') which will paste it in the line under the cursor.

# The format of command are
operator     [number]     motion
  d, c...      2,3...       $, w ...

# Operator to delete word
use <ce> to delete the from the cursor to the end of the word

# Search
use '/' with the word that you are searching like: '/my_searched_word'
use '?' to search upwards while '/' is downword
use then 'ctrl o' to go back where you where initially
use also 'n' to jump to next similar word going downward
use also 'N' to jump to next similar word going upward

# Access to shell from 'vim'
use ':!<your shell command>' to have access to the shell terminal and write some commands
use ':w filename' to write the full content of the file we are working on to a specific file name

# Copy part of the file and save to file
use 'v' and move the cursor to highlight the part that you want to select
use ':' and delete what is writen to then use ':w filename' to write the selected part to a separate file 

# Copy other file content to the one you working on
use ':r <filename>' and the file content will be copied and paste where the cursor is in your file

# Open newline
use 'o' to open a newline under your cursor line
use 'O' to open a newline above your cursor line

# Append
move cursor to the place where you want to append in '<Esc>' mode then use 'a' to add some extra characters
append 'a' is like 'i' insert
use 'A' to append at the end of the line instead of cursor position.

# Replace
use 'R' after having moved cursor to where you want to replace, then your will see down that you are in '--REPLACE--' mode

# Autocompletion
use 'Ctrl d' to see possible completions while in ':' mode
use 'Tab' to use one completion as in any terminal (This is best one! even how it displays the completion possibilities)

# split screen
use 'ctrl w' 'v' for vertical split
use 'ctrl w' 's' for horizontal split
use 'ctrl w' 'hjkl' to move from one screen to another choosing direction left, down, up, right
use 'ctrl w' 'ctrl w' to mo from one screen to another just next one, no directions here and will go around to come back to first screen split
use 'ctrl q' to close terminal splits


# zoom in and out
use 'ctrl shift' '+' to zoom in
use 'ctrl' '-' to zoom out

# open file in new buffer
# can add '!' if don't want to save previous buffer changes
:BDE ~/.vimrc
:bde ~/.vimrc 

# set working directory to the file opened path
- for setting working directory and having net split using same working directory as orgin path
:cd %:p:h
- for each split to have their working directory being the working space orign path to search from
:lcd %:p:h

:cd # change working directory
:lcd # local change director
%:p:h # get path without the file name

# open new file while working on a file
:cd %:p:h # making the file opened already as working directory
- if in same directory
:vs %:p:h/otherfile
:vs # for vertical split
%:p # % converts :p to full path of current file
:h  # to get rid of the file name in the path and get the head of the path
/otherfile # noe you can put otherfile to open
