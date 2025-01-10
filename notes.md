#####  My car is VrimVriming!

# - how to delete:
```bash
Being in <Esc> mode: move cursor in the character to delete and press <x>.
```
# - how to insert:
```bash
- normal insert: press <i> and insert at the cursor level and use <h, j, k, l> to move cursor <left, down, up, right>
- append insert: press <a> and you will see down there '--INSERT--' and you do the same as when using <i>
```
# - Quit 
```bash
use <Esc> then <:q!> , it tried without the '!' and it worked... soooo...
```
# - to Write to file
```bash
use <Esc> then <:wq!> .. i tried without the '!' and it worked...
```
# - to come back to beginning of line
```bash
use <0> to come back at the beginning of the line
```
# - to replace a character
```bash
use <r> on the character to replace and then type your character .
From the <Esc> mode and then will return <Esc> mode.
```
# - delete a full line
```bashuse <dd> to delete a full line
```
# - past a line under where your cursor is from a deleted line
```bash
use <dd> to delete a line and paste it somewhere else using <p> (called 'PUT' not 'paste') which will paste it in the line under the cursor.
```
# - The format of command are
```bash
operator     [number]     motion
  d, c...      2,3...       $, w ...
```
# - Operator to delete word
```bash
use <ce> to delete the from the cursor to the end of the word
```
# - Search
```bash
use '/' with the word that you are searching like: '/my_searched_word'
use '?' to search upwards while '/' is downword
use then 'ctrl o' to go back where you where initially
use also 'n' to jump to next similar word going downward
use also 'N' to jump to next similar word going upward
```
# - Access to shell from 'vim'
```bash
use ':!<your shell command>' to have access to the shell terminal and write some commands
use ':w filename' to write the full content of the file we are working on to a specific file name
```
# - Copy part of the file and save to file
```bash
use 'v' and move the cursor to highlight the part that you want to select
use ':' and delete what is writen to then use ':w filename' to write the selected part to a separate file 
```
# - Copy other file content to the one you working on
```bash
use ':r <filename>' and the file content will be copied and paste where the cursor is in your file
```
# - Open newline
```bash
use 'o' to open a newline under your cursor line
use 'O' to open a newline above your cursor line
```
# - Append
```bash
move cursor to the place where you want to append in '<Esc>' mode then use 'a' to add some extra characters
append 'a' is like 'i' insert
use 'A' to append at the end of the line instead of cursor position.
```
# - Replace
```bash
use 'R' after having moved cursor to where you want to replace, then your will see down that you are in '--REPLACE--' mode
```
# - Autocompletion
```bash
use 'Ctrl d' to see possible completions while in ':' mode
use 'Tab' to use one completion as in any terminal (This is best one! even how it displays the completion possibilities)
```
# - split screen
```bash
use 'ctrl w' 'v' for vertical split
use 'ctrl w' 's' for horizontal split
use 'ctrl w' 'hjkl' to move from one screen to another choosing direction left, down, up, right
use 'ctrl w' 'ctrl w' to mo from one screen to another just next one, no directions here and will go around to come back to first screen split
use 'ctrl q' to close terminal splits
```

# - zoom in and out
```bash
use 'ctrl shift' '+' to zoom in
use 'ctrl' '-' to zoom out
```
# - open file in new buffer
# can add '!' if don't want to save previous buffer changes
```bash
:BDE ~/.vimrc
:bde ~/.vimrc 
```
# - set working directory to the file opened path
- for setting working directory and having net split using same working directory as orgin path
```bash
:cd %:p:h
```
- for each split to have their working directory being the working space orign path to search from
```bash
:lcd %:p:h

:cd # change working directory
:lcd # local change director
%:p:h # get path without the file name
```
# - open new file while working on a file
```bash
:cd %:p:h # making the file opened already as working directory
```
- if in same directory
```bash
:vs %:p:h/otherfile
:vs # for vertical split
%:p # % converts :p to full path of current file
:h  # to get rid of the file name in the path and get the head of the path
/otherfile # noe you can put otherfile to open
```
# - open new file
```bash
:e filename
```
# - Neotree : the sidebar with the filesystem tree
```bash
:Neotree <path of file to open>
:Neotree <TAB> # to see options
```
- Then press `a` to create a directory ending with `/` or a file (popup will open)

# - open new tab and navigate tabs
```bash
:tabnew <name_of_tab>   will open one in a new tab.
(cab use nouse to click on tab to switch as well)
:-tabnext       " go to the previous tab page
:+tabnext       " go to the next tab page
:tabp           go also to previous tab
:tabn           go also to next tab
:tabN           got to next tab but the last one
"space space" to find buffer number > then ":dbe <number>" to delete buffer tab
```
# - file navigation
```basg
:Ex  to get view on folders and navigate after need to to use :cd /path/to/folder of :lcd /path.. for that tab only or window to not af>
```
# - difference between tabs, splits and buffer
- Tabs: Ideal for separating different workflows.
- Splits: Useful for viewing multiple files side by side.
- Buffers: Lightweight and allow switching between multiple open files without duplicating views.
```bash
:edit <filename>        open file in current buffer
:tabedit <filename>     open file on new tab
:<v/h>split <filename>  open file on new split (naviagte with Ctrl-w w/h/j/k/l)
:bedit <filename>       open file in new buffer (:ls to list all opened buffers)
```

___________________________________________________________________________________________________________

# **LUA**

# - learn `lua`
https://learnxinyminutes.com/docs/lua

## - Comment:
```lua
`--` : single line comment
`--[[ ]]`: multiline comment
```

## - variables
```lua
- local keyword for local variables
local variable = <put number>
- '' or "" for string: 
local word = "sentence not word"
- `[[ ]]` for multiline string:
[[ a mutiline string
 for my docstring for example or prompt
 ]]
```

- boolean:
```lua
local variable, othervar = true, false
- null values
local nulvar = `nil`
```

## - Functions
```lua
- funcion + name + body + end
local function <name of function>(parametervar)
  print("this is a parameter: ", parametervar)
end
- OR variable equal to funciton
local varfunc = function(paramvar)
  -- i am comment ting inside the function just one line
  print("parameter passed in func: ", parmvar)
end

# `calling` function with only one argument which is a string
- function with only one argument which is a string can be called without parenthesis (works for literal strings only), like:
local func_one_string_arg_only = function(string_argument)
  return string_argument .. " - Yoooooowwww!"
end
local sakura_house = func_one_string_arg_only "finger in orange juice" -> finger in orange juice - Yoooooowwww!
- can call function with map the same (literal table):
local checking_1_or_2 = function(any_map)
  if any_map.one == nil then
    any_map.one = "n'importe quoi"
  end
  print(any_map.one, any_map.two)
end
checking_1_or_2 { one = 1, two = 2} -> 1, 2
checking_1_or_2 { two = 2222} -> n'importe quoi, 2222 -- we didn't pass in key `one` so the key have been set in the function

# functions syntaxe sugar
- using `:` to replace `self` and dot `.` notation
local my_list = {}
funciton my_list.method_func(self, ... ) end
function my_list:method_fuc( ... ) end
```

## - dictionary and list to store stuff (those are tables in lua)
```lua
# List between: `{` and `}`
local mylist = { "junko", true, function() print("manga kissa shibuya"), 109 }
mylist[1] -> junko (so notice first value is not 0 index but 1)

# map (dictionary) betweem: `{` and `}` but `=` sign between key/value pairs
local dictionary = {
  boolean_var = false,
  ["a sentence as key"] = "really!?",
  [function() end] = "even function as key?! WOW!",
}
dictionary.boolean -> false
dictionary["a sentence as key"] -> "really!?"
dictionary[fucntion end] -> returns nothing because those are 2 different lua functions so not pointing to the same function so it won't work!
```

# - for loop
```lua
local my_list = { "creditizens", "toyko", 2024 }
[[ here `#` is the length operator (so like Python for index in len(my_list))
 and doesn't work for maps but for tables only (list)
]]
 -- index is start, # is stop
for index = 1, #my_list do
  print(index, my_list[index])
end

# OR use `ipairs` (index pairs or integer pairs) for tables (list)
for index, value in ipairs(my_list) do
  print(index, value)
end

# for maps use `in pairs`
local my_map  = { "pen" = "JR station", "paper" = "phone number" }
for key, value in paris(my_map) do
  print(key, value)
end
```

# - `if` conditionals
```lua
# if -> then -> else (or else if)
local function starbucks(coffee_type)
  -- this is like saying `if true`
  if coffee_type then
    print("You will get a discount")
  else
    print("we don't have this coffee here")
  end
end
# when we callit only `nil` and `false` are considered false
starbucks("junko shibuya")  or starbucks(1) or starbucks(true) -> You will get a discount
starbucks() or starbucks(false) -> we don't have this coffee here
```

# - modules
```lua
-- module_junko.lua
local my_module = {}
my_module.my_function_named_109 = function() print("Junko is shopping in 109 the whole afternoon.") end
return my_module
# import module (so here we import the mudle made just before which is in another file)
-- ginza_store.lua
local module_junko = require('module_junko')
module_junko.my_function_names_109()
```

# - unpacking objects vars
```lua
local var_func_param_packed = funciton( ... ) -- has some parameters with commas (param1, param2...)
  local argument_vars = { ... }
  for index, value in ipairs({ ... }) do print(index, value) end
  return unpack(argument_vars)
end
```

# - meta tables like dunder method (__repr__)in Python (change behavior of table) or like rust trait implementation
```lua
local super_table = {}
super_table.__add = function(left_table, right_table)
  return setmetatable({
    -- here we define the rule in how tables should be added up.
    --  here we are using the same index from both tables to be added and summed up in the `super_table` 
    left[1] + right[1],
    left[2] + right[2],
    left[3] + right[3],
  }, super_table)
end

local table1 = setmetatble({ 0, 1, 2}, super_table)
local table2 = setmetatble({ 10, 9, 8}, super_table)
local table3 = table1 + table2
tbale3 -> { 10, 10, 10, 
  <metatable> = { 
    __add = <function 1>
  }
}
```

# - keymaps to set vim keys
```lua
vim.keymap.set("n", "what you want to use as key", "the command that will be actioned when doing that key")
eg.:
vim.keymap.set("n", "<space><space>x", "<cmd>source %<CR>")
# need to chekc what is lhs, rhs..wakaranai!
use `:lua vim` to search and have access to doc or `:lua vim.<function name>` or `:help <name of function>`
```
