# Font configuration in Linux distros suck – write your own font.conf

- You can write your own font configuration file:
  `fonts.conf`.
- You can use it to specify what fonts will be rendered at websites.
- You can change default choices.
- Common places for storing fonts in Linux systems are
  `$HOME/.local/share/fonts`, `/usr/local/share/fonts`

Wen you're visiting a website with *font-face* configured as
*serif, sans-serif* or more specifically, *Helvetica, Arial*
you can see one of the Linux world not-so-good sides.
Your visual experience is likely worst than those who actually can
see *Helvetica* or even *Arial*.
You probably got something like *Liberation Sans*, *DejaVu Sans*, or *Ubuntu*,
which often don't look good on a page made with something else in mind.

With help from devtools, I picked some typical settings:
- *-apple-system, BlinkMacSystemFont, "Segoe UI",
  "Liberation Sans", sans-serif* — used at StackOverflow.
- *Arial, sans-serif* — at google.com.

There are good, open source typefaces that
blend better in the web context.
They look closer to Sand Francisco or Helvetica —
clean, familiar, standard-like — and
have similar basic parameters.

Here's a list of popular choices I like and you can download.
Sans-serif:
- [Roboto](https://fonts.google.com/specimen/Roboto)
  (used often at Google's sites)
- [IBM Plex Sans](https://github.com/IBM/plex)
- [Inter](https://rsms.me/inter/)

Serif:
- [Merriweather](https://fonts.google.com/specimen/Merriweather)
- [IBM Plex Serif](https://github.com/IBM/plex)

Put them into one of those places:
- `$HOME/.local/share/fonts`
- `/usr/local/share/fonts`

Here's an exemplary *font.config* content.
It uses XML format.

`
<?xml version="1.0"?>
<!DOCTYPE fontconfig SYSTEM "urn:fontconfig:fonts.dtd">
<!-- $XDG_CONFIG_HOME/fontconfig/fonts.conf for per-user font configuration -->
<fontconfig>
<alias>
	<family>sans-serif</family>
	<prefer><family>Roboto</family></prefer>
</alias>
<alias>
	<family>serif</family>
	<prefer><family>IBM Plex Serif</family></prefer>
</alias>
<alias>
	<family>monospace</family>
	<prefer><family>IBM Plex Mono</family></prefer>
</alias>

<!-- Replace popular fonts with my favs -->
<match target="pattern">
  <test qual="any" name="family"><string>Helvetica</string></test>
  <edit name="family" mode="assign" binding="same"><string>Roboto</string></edit>
</match>
<match target="pattern">
  <test qual="any" name="family"><string>Arial</string></test>
  <edit name="family" mode="assign" binding="same"><string>Roboto</string></edit>
</match>
<match target="pattern">
  <test qual="any" name="family"><string>Georgia</string></test>
  <edit name="family" mode="assign" binding="same"><string>IBM Plex Sans</string></edit>
</match>
<match target="pattern">
  <test qual="any" name="family"><string>Times New Roman</string></test>
  <edit name="family" mode="assign" binding="same"><string>IBM Plex Serif</string></edit>
</match>
</fontconfig>
`

A file like this should be placed most likely at
<code>$HOME/.config/fontconfig/</code>.
It uses XML format

This is just basic use example. Read more at
[official documentation](https://www.freedesktop.org/wiki/Software/fontconfig/)

[ArchLinux docs](https://wiki.archlinux.org/title/font_configuration)
have good tips too.

## Quick sum-up
- You need all the fonts you want to be on your system,
  at <code>$HOME/.fonts/</code>.
- All your configuration stuff write into <code>$HOME/.config/fontconfig/fonts.conf</code>
  file.
- Use fonts made for UIs that look clean and standard — you want predictable
  behavior.




