# The Ur-Quan Masters MegaMod Flatpak

A [Flatpak](https://flatpak.org/) build of [The Ur-Quan Masters MegaMod](https://github.com/Serosis/UQM-MegaMod).

## Installation

This is a work in progress. For now you'll need to build the packages yourself.

Building & installing the flatpak locally is simple - ensure flatpak-builder is installed on your system then run:

```bash
# Add the Flathub repo for the freedesktop runtime
flatpak remote-add --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo
# Install the Freedesktop runtime & SDK
flatpak install flathub org.freedesktop.Platform//19.08
flatpak install flathub org.freedesktop.Sdk//19.08
# Build and install the base Ur-Quan Masters MegaMod app
flatpak-builder --install --user builddir net.serosis.megamod.json --force-clean
```

Optional add-ons are available as extensions. To build and install the add-on you want to use, complete the above steps and then:

```bash
# HD content
flatpak-builder --install --user builddir net.serosis.megamod.addon.HD.json --force-clean
# 3DO voices
flatpak-builder --install --user builddir net.serosis.megamod.addon.Voice3DO.json --force-clean
```

## Running

To run the game, either use the launcher shortcut, or:

```bash
flatpak run net.serosis.megamod
```

To uninstall, run

```bash
flatapk remove net.serosis.megamod
```

This will also remove any installed extensions.
