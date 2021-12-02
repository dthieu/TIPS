# Some useful tips :smile:
## VIM
* :star: List all finding:
  + Step 1: Search by "/" . Ex: "/ahihi"
  + Step 2: List all result by: **:g//l**
* :star: Issue: Sometimes you press <kbd>Ctrl</kbd> + <kbd>S</kbd> as a habit and... cannot edit => vim editor hung up? :scream:
  That's a screen-lock. Use <kbd>Ctrl</kbd>+<kbd>q</kbd> to unlock :smile:
  
* :star: Find and replace place by place
   Using: **:%s/\<old>/\<new>/gc** and **press 'y' or 'n' to replace or not**
   _Ex:_   :%s/foo/bar/gc => Change each 'foo' to 'bar', but ask for confirmation first. 
- :star: Edit on multi-line:
  + <kbd>Ctrl</kbd>+<kbd>V</kbd> and press (↑ ↓ → ←) to select 
  + <kbd>Shift</kbd>+<kbd>I</kbd> to edit 
  + Press <kbd>ESC</kbd> to finished.
* :star: Open 2 windows (left and right):
  + :vsp <tab_to_select_file>
  + <kbd>Ctrl</kbd> + <kbd>w</kbd> + <kbd>h</kbd> : select left window
  + <kbd>Ctrl</kbd> + <kbd>w</kbd> + <kbd>l</kbd> : select right window
  + Tip: we can click <kbd>Ctrl</kbd> + <kbd>w</kbd> to navigate between 2 windows
* :star: Select all in a file: type: `ggVG`
* :star: Export diff into html file
 ` vimdiff`  `file1.txt` `file2.txt` -c `TOhtml` -c `'w! diff.html'` -c `'qa!'`
 
* :star: Command when using vimdiff
  +   ` ]c`          - next difference
  +    `do`          - diff obtain
  +   ` [c`          - previous difference
  +    `dp`          - diff put
  +   ` zo`          - open folded text
  +    `zc`          - close folded text
  +    `:diffupdate` - re-scan the files for differences
  +    To avoid whitespace comparison type `:set diffopt+=iwhite`
* :star: Navigate the position of pointer:
  + <kbd>''</kbd> or <kbd>``</kbd> (click <kbd>~`</kbd> below of <kbd>ESC</kbd> 2 times) to switch between the last position and the current position.
* :star: Like Unikey, abbreviation in Vim :sunglasses:
`:ab <type> <display>`
_Ex:_ 
  + `:ab apple Apple Computer, Inc.`
  + Press <kbd>i</kbd> to change insert mode, type: `apple<space>` 
  + The apple will become: `Apple Computer, Inc.<space>` :yum:
* :star: Open and jump: `$ vi fileName +<LineNumber>`
* :star: Quick search    : Select variable and <kbd>Shift</kbd> + <kbd>8</kbd> or <kbd>Shift</kbd> + <kbd>3</kbd>
* :star: Move to end of line: Shift + 4 // $
* :star: Change tougle characters: as -> AS: <kbd>Shift</kbd> + <kbd>F3</kbd>
* :star: Delete all line in a file: `gg dG`
* :star: Using mouse to move pointer: add "set mouse=a" in ~/.vimrc
