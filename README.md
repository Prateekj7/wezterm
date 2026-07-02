# wezterm

My personal [WezTerm](https://wezterm.org) config and lua scripts.

## Setup on a new machine

1. Install WezTerm: `brew install --cask wezterm`
2. Install the [JetBrains Mono](https://www.jetbrains.com/lp/mono/) font (regular + italic weights).
3. Clone this repo to `~/.config/wezterm`:
   ```sh
   git clone https://github.com/Prateekj7/wezterm.git ~/.config/wezterm
   ```
4. Launch WezTerm — `wezterm.lua` is picked up automatically, and `automatically_reload_config = true` means any further edits apply live without a restart.

## What's in the config

- **Cursor**: steady bar cursor (`default_cursor_style`)
- **Window**: resize-only decorations (no native title bar buttons), no confirmation prompt on close, no auto-resize when font size changes, update checks disabled
- **Tab bar**: disabled (`enable_tab_bar = false`) — pane management is done via the leader-key bindings below instead
- **Font**: JetBrains Mono, bold weight, 12.5pt, with explicit `font_rules` so italic and bold-italic text render with the font's real italic glyphs instead of a faked slant
- **Scrollback**: 10,000 lines
- **Bell**: audible bell disabled
- **Background**: `dark-desert.jpg` wallpaper with a dark color overlay (`#282c35` at 55% opacity) for readability
- **Hyperlinks**: custom rules (adapted from [akos.ma](https://akos.ma/blog/adopting-wezterm/)) that linkify URLs wrapped in `()`, `[]`, `{}`, `<>`, or bare in text — only the URL itself is made clickable, not the surrounding brackets

## Keyboard shortcuts

### Enter key variants
| Keys | Action |
|---|---|
| `Ctrl+Enter` | Sends `\x1b[13;5u` (CSI-u encoded Ctrl+Enter, useful for apps/TUIs that distinguish it from plain Enter) |
| `Shift+Enter` | Sends `\x1b[13;2u` (CSI-u encoded Shift+Enter) |

### Leader key (tmux-style pane management)
Leader is `Ctrl+A`. Tap it, release, then press the next key within 1 second.

| Keys | Action |
|---|---|
| `Leader` then `\|` | Split pane horizontally (new pane to the right) |
| `Leader` then `-` | Split pane vertically (new pane below) |
| `Leader` then `h` | Move to the pane on the left |
| `Leader` then `j` | Move to the pane below |
| `Leader` then `k` | Move to the pane above |
| `Leader` then `l` | Move to the pane on the right |
| `Leader` then `z` | Toggle zoom on the current pane |
| `Leader` then `x` | Close the current pane (no confirmation) |

### Text selection
| Keys | Action |
|---|---|
| `Cmd+Shift+Space` | Quick Select mode — highlight and copy URLs/paths/hashes etc. with the keyboard |
| `Cmd+Shift+X` | Copy mode — vim-style keyboard-driven text selection |

All other default WezTerm keybindings (new tab, new window, font zoom, etc.) remain active since this config only adds to, not replaces, the defaults.

## Links
https://github.com/hendrikmi/dotfiles/blob/main/zsh/custom.zsh
