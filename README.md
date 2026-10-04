# Gruvbox GRUB Theme

A minimalistic, terminal-inspired Gruvbox theme for GRUB.

![Gruvbox GRUB Theme Preview](preview/gruvbox-boot.png)

## How to use

### Install theme

Copy the `gruvbox` theme folder into your system's GRUB themes directory:

```bash
sudo mkdir -p /boot/grub/themes
sudo cp -r gruvbox /boot/grub/themes/
```

### Select theme

Edit GRUB config `/etc/default/grub` by adding following line

```bash
GRUB_THEME="/boot/grub/themes/gruvbox/theme.txt"
```

### Update GRUB

Dependign on your distro you might need to look it up by yourself.
Here is how you can do it for some of them:
* **Arch:** `sudo grub-mkconfig -o /boot/grub/grub.cfg`
* **Debian / Ubuntu:** `sudo update-grub`
* **Fedora / RHEL:** `sudo grub2-mkconfig -o /boot/grub2/grub.cfg`

## Additional steps

### Gruvbox terminal color palette

Edit GRUB config `/etc/default/grub` by adding following string at the end of the `GRUB_CMDLINE_LINUX_DEAFULT`:
```bash
vt.default_red=40,204,152,215,69,177,104,168,146,251,184,250,131,211,142,235 vt.default_grn=40,36,151,153,133,98,157,153,131,73,187,189,165,134,192,219 vt.default_blu=40,29,26,33,136,134,106,132,116,52,38,47,152,155,124,178
```

So it would look like this:
```bash
GRUB_CMDLINE_LINUX_DEFAULT="vt.global_cursor_default=1 ... nvidia_drm.modeset=1 nvidia-drm.fbdev=1 psi=1 vt.default_red=40,204,152,215,69,177,104,168,146,251,184,250,131,211,142,235 vt.default_grn=40,36,151,153,133,98,157,153,131,73,187,189,165,134,192,219 vt.default_blu=40,29,26,33,136,134,106,132,116,52,38,47,152,155,124,178"
