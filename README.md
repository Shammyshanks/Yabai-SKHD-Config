# Yabai-SKHD-Config
My personal Yabai and SKHD config files.

# Installation
Download all files and drag into home folder.

# The problem with most tiling window manager configs
Tiling Window Managers are, by design, meant to be keyboard-driven. This requires that some modifiers be almost completely reserved for operating the window manager. MacOS only has 4 modifiers to begin with, and we need to choose a modifier combination that won't conflict with applications.

# Taking inventory
The 4 modifiers we can work with are `Shift`, `Control`, `Option`, and `Command`.
The following are all of the possible variations we can work with.

| One Key   | Two Keys              | Three Keys                       | Four Keys                                  |
| --------- | --------------------- | -------------------------------- | ------------------------------------------ |
| `Command` | `Shift` + `Command`   | `Option` + `Shift` + `Command`   | `Control` + `Option` + `Command` + `Shift` | 
| `Shift`   | `Option` + `Command`  | `Control` + `Shift` + `Command`  |                                            |
| `Option`  | `Option` + `Shift`    | `Control` + `Option` + `Command` |                                            |
| `Control` | `Control` + `Command` | `Control` + `Option` + `Shift`   |                                            |
|           | `Control` + `Shift`   |                                  |                                            |
|           | `Control` + `Option`  |                                  |                                            |


# Consulting the Apple Style Guide
According to the Keyboard section of [Apple's Style Guide](https://developer.apple.com/design/human-interface-guidelines/macos/user-interaction/keyboard/):

> Prefer the Command key as the main modifier key in a keyboard shortcut

> Prefer the Shift key as a secondary modifier when a shortcut complements another shortcut

> Use the Option key as a modifier sparingly

> As much as possible, avoid using the Control key as a modifier

This tells us which key combinations are most likely to be used by various applications on MacOS. We know now to avoid all single-key shortcuts, and any shortcut combination involving the `Command` key as it is the primary modifier in MacOS. We also know to avoid `Control` shortcut keys by themselves as they are often used by terminal applications (like vim) and Emacs-style keybindings are still found within MacOS when in any textbox (shortcuts like <C-a> goes to the beginning of the line, <C-d> deletes forward, etc...). We should also probably leave the `Option` + `Shift` modifier alone since it's used to write capital, accented charecter like `ü`, `æ`, and `ß`. We also want to reserve the four-key shortcut alone since we will be using that to make a new modifier, the `Hyper` key.

Remember, we want to preserve as much of the original functionality as possible.

This leaves our possible key combinations looking like this:

| One Key       | Two Keys                  | Three Keys                           | Four Keys                                      |
| ------------- | ------------------------- | ------------------------------------ | ---------------------------------------------- |
| ~~`Command`~~ | ~~`Shift` + `Command`~~   | ~~`Option` + `Shift` + `Command`~~   | ~~`Control` + `Option` + `Command` + `Shift`~~ | 
| ~~`Shift`~~   | ~~`Option` + `Command`~~  | ~~`Control` + `Shift` + `Command`~~  |                                                |
| ~~`Option`~~  | ~~`Option` + `Shift`~~    | ~~`Control` + `Option` + `Command`~~ |                                                |
| ~~`Control`~~ | ~~`Control` + `Command`~~ | `Control` + `Option` + `Shift`       |                                                |
|               | `Control` + `Shift`       |                                      |                                                |
|               | `Control` + `Option`      |                                      |                                                |

The only 3 key combinations we have left are 

`Control` + `Option`

`Control` + `Shift`

`Control` + `Option` + `Shift` 

These are the 3 key combinations we will be using to manage Yabai.

Note: if you don't care about typing unique charecters with `Option` and `Shift`, you can also add those combinations to the final list of shortcuts.

# A quick note on left vs right modifiers and the Function Key
Yabai *does* support differentiating left vs right modifiers, but since we are going to be using "vim-style" keybindings, we are going to try and keep our hands on the home row as much as possible. This means it will be easier to type commands using the left modifiers than the right as there is no `RControl` on most Mac Keyboards and this configuration should work on both the built-in keyboard and external keyboards.

Since the user will be using the left modifier keys, all of the shortcuts will be executed using the keys on the right hand of the keyboard.

As for the function key, this is a weird one. It *is* recognized by yabai but acts differently than the other modifiers and cannot always be picked up by applications. This, combined with the fact that it will not be found on most keyboards made me hesitant to rely on it for WM control. Instead, I will be using it for mouse control later on. If you don't mind, feel free to use it for Yabai.

# How to use Keyboard shortcuts
From now on, I will be referring to 

`Control + Option` as `mod1`

`Control + Shift` as `mod2`

`Control + Option + Shift` as `mod3`

In this configuration, `mod1` will the be the main modifier and as such it will be the most used modifier and control the most frequent actions.

`mod2` is for actions similar to it's `mod1` counterpart but less frequently used.

`mod3` is for more rare actions and as such will be used the least.

The keyboard shortcuts are designed to be easy to remember. Most shortcuts are just using the last 4 keys on the left hand side e.g. h/j/k/l on the homerow, u/i/o/p on the top row, and v/b/n/m on the bottom row. 

Some keys are inherited from the base operating system (like creating and destroying spaces and selecting displays) so it is easy to remember. 

The remaining, most important actions are tied to large easy to hit keys like backspace, return, backslash, zero, plus, minus, and semicolon. 

The most difficult keys to remember are the open and close brackets but they are rarely going to be used by most users.

# Special features
Many actions have carrousel enabled. For example, if you focus the previous space while you are on the first space, you will be takes to the last space.

Several actions also use exit codes to figure out if the current space is `bsp`, `float`, or `stack`. This way the shortcut to resize a window in `bsp` can also be used to resize the window in `float`.

This reduces the number of discrete keyboard shortcuts the user has to remember.

This script also integrates with my [SwiftBar](https://github.com/swiftbar/SwiftBar) plugin [Yabai-Spaces](https://github.com/SxC97/Yabai-Spaces) which shows you the current space you are on, the total number of spaces, the current space type, and weather the current window is floating or not. The refresh code at the end of several commands can be removed if you don't plan on using this feature.

Several actions execute external scripts found in the `.scripts` folder. The script expects this folder and it's files to be in the home folder.

These actions include
* turning borders off if there is only 1 managed window in the current space via [Limelight](https://github.com/koekeishiya/limelight)
* turning gaps off if there is only 1 managed window in the current space (This is where you would change the gaps settings, not .yabairc)
* turning some Übersicht widgets off if there are any windows in the current space (This would require configuration if you plan on using it)
* cycling through space management types
* creating a new terminal window

This yabairc configuration file also integrates with [pywal](https://github.com/dylanaraps/pywal)

There is a section near the bottom of .yabairc that creates exceptions for various apps that mess with the .gaps and .border scripts in .scripts folder. If you are having trouble with an app, try adding it here.

This config also eshews yabai's built-in border feature for [limelight](https://github.com/koekeishiya/limelight) due to better compatibility with MacOS Big Sur's new rounded window corners. `.yabairc` and `.scripts/.border` both expect you to have the `.limelightrc` file in your home directory. If you want to adjust the border thickness, it needs to be done in the `.limelightrc` file as `.script/.border` only toggles Limelight on and off.

This .yabairc will also auto-update yabai if you installed yabai via --HEAD.
```
brew install yabai --HEAD
```

NOTE: if you want the focus spaces shortcut to work in mission control you need to follow these steps:
1. System Preferences -> Keyboard -> Shortcuts -> Mission Control -> Mission Control -> "Move left a space" to "ctrl + cmd + left"
2. System Preferences -> Keyboard -> Shortcuts -> Mission Control -> Mission Control -> "Move right a space" to "ctrl + cmd + right"

NOTE: The create new terminal action only works with iTerm2

# Keyboard Shortcut Table
| Shortcut                    | Action                                                                         | Notes |
| --------------------------- | ------------------------------------------------------------------------------ | ----- |
| `mod1 + h/j/k/l`            | focus window west/south/north/east                                             | Carrousel, works in `bsp` |
| `mod1 + j/k`                | focus window next/prev                                                         | Carrousel, works in `stack` |
| `mod1 + h/l`                | swap window next/prev                                                          | Carrousel, works in `stack` |
| `mod2 + h/j/k/l`            | move window west/south/north/east                                              | Carrousel, works in `bsp` and `float` |
| `mod3 + h/j/k/l`            | swap window west/south/north/east                                              | Carrousel
| `mod1 + u/i/o/p`            | resize window left/down/up/right                                               | Only works in `float` |
| `mod2 + u/i/o/p`            | set insertion point west/south/north/east | Only works in `bsp`                |
| `mod1 + v/b/n/m`            | make window fill left/bottom/top/right half of screen                          | works in `float` |
| `mod2 + v/b/n/m`            | make window fill top-right/top-left/bottom-right/bottom-left quarter of screen | works in `float` |
| `mod1 + backspace`          | toggle float and center window on screen | works in all space types            |
| `mod2 + backspace`          | make floating window fill screen | works in `float`                            |
| `mod3 + backspace`          | cycle space management type `bsp`->`stack`->`float`->`bsp`                     | works in all space types |
| `mod1 + return`             | rotate windows clockwise                                                       | works in `bsp` |
| `mod2 + return`             | rotate windows counter-clockwise                                               | works in `bsp` |
| `mod3 + return`             | balance window sizes                                                           | works in `bsp` |
| `mod1 + left/down/up/right` | fill left/bottom/top/right half of screen                                      | works in `float` |
| `mod1 + \`                  | toggle split type for current space                                            | works in `bsp` |
| `mod2 + \`                  | toggle parent zoom                                                             | works in `bsp` |
| `mod3 + \`                  | toggle picture-in-picture                                                      | works in all space types |
| `mod1 + ;`                  | toggle fullscreen                                                              | works in `bsp` |
| `mod1 + [`                  | mirror tree y-axis                                                             | works in `bsp` |
| `mod1 + ]`                  | mirror tree x-axis                                                             | works in `bsp` |
| `mod2 + [`                  | swap current window with the largest window                                    | works in `bsp` |
| `mod2 + ]`                  | swap current window with the smallest window                                   | works in `bsp` |
| `mod1 + 0`                  | set desktop offset to 0                                                        | works in `bsp` and `stack` |
| `mod2 + 0`                  | set window offset to 0                                                         | works in `bsp` |
| `mod3 + 0`                  | set desktop and window offset to 0                                             | works in `bsp` and kind-of `stack` |
| `mod1 + -`                  | decrease desktop offset                                                        | works in `bsp` and `stack` |
| `mod2 + -`                  | decrease window offset                                                         | works in `bsp` |
| `mod3 + -`                  | decrease desktop and window offset                                             | works in `bsp` and kind-of `stack` |
| `mod1 + +`                  | increase desktop offset                                                        | works in `bsp` and `stack` |
| `mod2 + +`                  | increase window offset                                                         | works in `bsp` |
| `mod3 + +`                  | increase desktop and window offset                                             | works in `bsp` and kind-of `stack` |
| `mod1 + t`                  | create new space and focus                                                     | works in all space types |
| `mod2 + t`                  | create new space, moves window to new space and focus                          | works in all space types |
| `mod1 + w`                  | destroy space and focus first space                                            | works in all space types |
| `control + 1-9`             | focus a specific desktop                                                       | works in all space types |
| `mod1 + 1-9`                | send window to a specific space and focus said desktop                         | works in all space types |
| `mod2 + 1-9`                | swap current space with specified space                                        | works in all space types |
| `mod3 + 1-9`                | send window to a specific display and focus said display                       | works in all space types |
| `control + left/right`      | fast focus prev/next space                                                     | Carrousel, works in all space types, works in mission control |
| `mod1 + left/right`         | move window to prev/next space and focus prev/next space                       | Carrousel, works in all space types |
| `mod2 + left/right`         | swap space left/right                                                          | Carrousel, works in all space types |
| `mod3 + left/right`         | send window to prev/next display                                               | Carrousel, works in all space types |
| `option + tab`              | focus next display                                                             | Carrousel, works in all space types |
| `option + shift + tab`      | focus prev display                                                             | Carrousel, works in all space types |
| `mod3 + r`                  | reload yabai                                                                   | works in all space types |
| `ctrl + return`             | open new terminal                                                              | works in all space types |

# Future Roadmap
* Implement thirds for floating windows (will be more useful if I ever upgrade to an ultrawide/super ultrawide.
* Export gaps variable for use in .gaps script when using keyboard shortcuts for changing gaps. Might require some changes to yabai.
* Implement dynamic desktops, as seen in gnome desktop. (I already have a working script but it's glitchy)
* Shortcut to display keyboard shortcuts and maybe execute actions (maybe use [Menu-Hammer](https://github.com/FryJay/MenuHammer)?) like AwesomeWM.
* Implement quick way to lable current space, maybe via alfred? Also add specific apps for spaces.
* Add support for focusing specific display
