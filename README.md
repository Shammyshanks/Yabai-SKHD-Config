# Yabai-SKHD-Config
My personal Yabai and SKHD config files.

# The problem with most tiling window manager configs
Tiling Window Managers are, by design, ment to be keyboard-driven. This requires that some modifiers be almost completely reserved for operating the window manager. MacOS only has 4 modifiers to begin with, and we need to choose a modifier combination that won't conflict with applications.

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

The only 3 key combinations we have left are `Control` + `Option`, `Control` + `Shift`, and `Control` + `Option` + `Shift`. These are the 3 key combinations we will be using to manage Yabai.

Note: if you don't care about typing unique charecters with `Option` and `Shift`, you can also add those combinations to the final list of shortcuts.

# A quick note on left vs right modifiers and the Function Key
Yabai *does* support differentiating left vs right modifiers, but since we are going to be using "vim-style" keybindings, we are going to try and keep our hands on the home row as much as possible. This means it will be easier to type commands using the left modifiers than the right. We will be coming back to the right modifiers as `Greek` and `Top` modifiers later on. If you are left-handed, you could flip the modifiers you use, the rc files should support both configurations, but it is expected that the user will use the left modifiers as there is no `RControl` on most Mac Keyboards.

As for the function key, this is a weird one. It *is* recognized by yabai but acts differently than the other modifiers and cannot always be picked up by applications. This, combined with the fact that it will not be found on most keyboards made me hesitant to rely on it for WM control. Instead, I will be using it for mouse control later on. If you don't mind, feel free to use it for Yabai.
