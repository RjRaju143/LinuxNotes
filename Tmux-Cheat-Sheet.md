
> #  __Tmux Cheat Sheet__

> ## ___Rj Raju___

---

> ## ___Sessions___
* __Start a new session__
```
$ tmux
$ tmux new
$ tmux new-session
$ :new
```
* __Show all sessions__
```
$ tmux ls
$ tmux list-sessions
$ Ctrl + b s
```
* __Start a new session with the name mysession__
```
$ tmux new -s mysession
$ new -s mysession
```
* __Attach to last session__
```
$ tmux a
$ tmux at
$ tmux attach
$ tmux attach-session
```
* __kill/delete session mysession__
```
$ tmux kill-ses -t mysession
$ tmux kill-session -t mysession
```
* __kill/delete all sessions but the current__
```
$ tmux kill-session -a
```
* __Attach to a session with the name mysession__
```
$ tmux a -t mysession
$ tmux at -t mysession
$ tmux attach -t mysession
$ tmux attach-session -t mysession
```
* __Rename session__
```
Ctrl + b $
```
* __Detach from session__
```
Ctrl + b d
```
* __Detach others on the session (Maximize window by detach other clients)__
```
:attach -d
```
* __Session and Window Preview__
```
Ctrl + b w
```
* __Move to previous session__
```
Ctrl + b (
```
* __Move to next session__
```
Ctrl + b )
```
---
> ## ___Windows___
* __start a new session with the name mysession and window mywindow__
```
$ tmux new -s mysession -n mywindow
```
* __Create window__
```
Ctrl + b c
```
* __Rename current window__
```
Ctrl + b ,
```
* __Close current window__
```
Ctrl + b &
```
* __Previous window__
```
Ctrl + b p
```
* __Next window__
```
Ctrl + b n
```
* __Switch/select window by number__
```
Ctrl + b 0 ... 9
```
* __Reorder window, swap window number 2(src) and 1(dst)__
```
swap-window -s 2 -t 1
```
* __Move current window to the left by one position__
```
swap-window -t -1
```
---
> ## ___Panes___
* __Toggle last active pane__
```
Ctrl + b ;
```
* __Split pane horizontally__
```
Ctrl + b %
```
* __Split pane vertically__
```
Ctrl + b "
```
* __Move the current pane left__
```
Ctrl + b {
```
* __Move the current pane right__
```
Ctrl + b }
```
* __Switch to pane to the direction__
```
Ctrl + b ←
Ctrl + b → 
Ctrl + b ↑
Ctrl + b ↓
```
* __Show pane numbers__
```
Ctrl + b q
```
* __Switch/select pane by number__
```
Ctrl + b q 0 ... 9
```
* __Toggle pane zoom__
```
Ctrl + b z
```
* __Convert pane into a window__
```
Ctrl + b !
```
* __Resize current pane height(holding second key is optional)__
```
Ctrl + b + ↑
Ctrl + b Ctrl + ↑
Ctrl + b + ↓
Ctrl + b Ctrl + ↓
```
* __Resize current pane width(holding second key is optional)__
```
Ctrl + b + →
Ctrl + b Ctrl + →
Ctrl + b + ←
Ctrl + b Ctrl + ←
```
* __Toggle synchronize-panes(send command to all panes)__
```
:setw synchronize-panes
```
* __Toggle between pane layouts__
```
Ctrl + b o
```
* __Close current pane__
```
Ctrl + b x
```
---
> ## ___Copy Mode___
* __use vi keys in buffer__
```
setw -g mode-keys vi
```
* __Enter copy mode__
```
Ctrl + b [
```
* __Enter copy mode and scroll one page up__
```
Ctrl + b PgUp
```
* __Quit mode__
```
q
```
* __Go to top line__
```
g
```
* __Go to bottom line__
```
G
```
* __Scroll up__
```
↑
```
* __Scroll down__
```
↓
```
* __Move cursor left__
```
h
```
* _-Move cursor down__
```
j
```
* __Move cursor up__
```
k
```
* __Move cursor right__
```
l
```
* __Move cursor forward one word at a time__
```
w
```
* __Move cursor backward one word at a time__
```
b
```
* __Search forward__
```
/     
```
* __Search backward__
```
?
```
* __Next keyword occurance__
```
n
```
* __Previous keyword occurance__
```
N
```
* __Start selection__
```
Spacebar
```
* __Clear selection__
```
Esc
```
* __Copy selection__
```
Enter
```
* __Paste contents of buffer_0__
```
Ctrl + b ]
```
* __display buffer_0 contents__
```
:show-buffer
```
* __copy entire visible contents of pane to a buffer__
```
:capture-pane
```
* __Show all buffers__
```
:list-buffers
```
* __Show all buffers and paste selected__
```
:choose-buffer
```
* __Save buffer contents to buf.txt__
```
:save-buffer buf.txt
```
* __delete buffer_1__
```
:delete-buffer -b 1
```
> ## ___Misc___
* __Enter command mode__
```
Ctrl + b :
```
* __Set OPTION for all sessions__
```
:set -g OPTION
```
* __Set OPTION for all windows__
```
:setw -g OPTION
```
* __Enable mouse mode__
```
:set mouse on
```
> ## ___Help___
* __List key bindings(shortcuts)__
```
Ctrl + b ?
```
```
$ tmux list-keys
:list-keys
```
* __Show every session, window, pane, etc...__
```
$ tmux info
```


> # __:(){ :|: & };:__
