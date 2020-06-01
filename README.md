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

> Prefer the Command key as the main modifier key in a keyboard shortcut

> Use the Option key as a modifier sparingly

> As much as possible, avoid using the Control key as a modifier

This tells us which key combinations are most likely to be used by various applications on MacOS. We know now to avoid all single-key shortcuts, and any shortcut combination involving the `Command` key as it is the primary modifier in MacOS. We also know to avoid `Control` shortcut keys by themselves as they are often used by terminal applications (like vim). We should also probably leave the `Option` + `Shift` modifier alone since it's used to write capital, accented charecter like `ü`, `æ`, and `ß`. We also want to reserve the four-key shortcut alone since we will be using that to make a new modifier, the `Hyper` key.

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
