# 📁 Double Commander — Arch Linux + i3

A quick guide for installing and configuring **Double Commander Qt6** with **dark mode** on **Arch Linux + i3**.

---

## 📦 Installation

Search available Double Commander packages:

```bash
pacman -Ss doublecmd
```

Install the Qt6 version:

```bash
sudo pacman -S doublecmd-qt6
```

Verify the installation:

```bash
pacman -Q doublecmd-qt6
```

Launch Double Commander:

```bash
doublecmd
```

---

## 🌙 Dark Mode

To launch Double Commander using the GTK3 theme backend:

```bash
QT_QPA_PLATFORMTHEME=gtk3 doublecmd
```

If your system is configured with a dark GTK theme, Double Commander will use the corresponding dark appearance.

### Test the configuration

Run:

```bash
QT_QPA_PLATFORMTHEME=gtk3 doublecmd
```

If Double Commander starts with the expected dark theme, you can add the same command to your i3 configuration.

---

## ⌨️ i3 Keybinding

Edit your i3 configuration:

```bash
nano ~/.config/i3/config
```

Add:

```i3
# 📁 Double Commander
bindsym $mod+Control+m exec QT_QPA_PLATFORMTHEME=gtk3 doublecmd
```

Now pressing:

```text
Super + Ctrl + M
```

will launch Double Commander with the GTK3 theme backend.

---

## 🔄 Reload i3

After modifying the i3 configuration, reload it:

```text
Super + Shift + R
```

Or use:

```bash
i3-msg reload
```

---

## 💡 Using an i3 Variable

For a cleaner configuration, you can store the launch command in a variable:

```i3
# 📁 Double Commander
set $doublecmd QT_QPA_PLATFORMTHEME=gtk3 doublecmd

bindsym $mod+Control+m exec $doublecmd
```

This makes it easier to modify the command later.

---

## 🎨 Double Commander Appearance

Double Commander also provides its own appearance settings.

Open:

**Configuration → Options → Colors**

You can customize:

* 🖥️ File panel background
* 📝 Text color
* 🔵 Selection color
* 📂 Directory appearance
* 📑 Tabs
* 🖱️ Active item

---

## 🛠️ Troubleshooting

### Double Commander does not use the dark theme

First test the command directly:

```bash
QT_QPA_PLATFORMTHEME=gtk3 doublecmd
```

If this works, make sure the exact same command is used in your i3 configuration:

```i3
bindsym $mod+Control+m exec QT_QPA_PLATFORMTHEME=gtk3 doublecmd
```

Then reload i3:

```bash
i3-msg reload
```

---

## 📋 System Configuration

| Component      | Configuration      |
| -------------- | ------------------ |
| OS             | Arch Linux         |
| Window Manager | i3                 |
| File Manager   | Double Commander   |
| Package        | `doublecmd-qt6`    |
| Theme Backend  | GTK3               |
| Dark Mode      | 🌙 Enabled         |
| Shortcut       | `Super + Ctrl + M` |

---

## 🚀 Quick Setup

Install Double Commander:

```bash
sudo pacman -S doublecmd-qt6
```

Test dark mode:

```bash
QT_QPA_PLATFORMTHEME=gtk3 doublecmd
```

Add to `~/.config/i3/config`:

```i3
# 📁 Double Commander
bindsym $mod+Control+m exec QT_QPA_PLATFORMTHEME=gtk3 doublecmd
```

Reload i3:

```bash
i3-msg reload
```

Done! 🎉
