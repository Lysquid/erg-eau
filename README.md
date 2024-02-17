[Erglace](https://lysquid.github.io/Erglace/)
================================================================================

A layout for French, English and programming. It is a fork of [ErgEAU](https://github.com/IgrecL/ErgEAU), initially adapted for compact keyboards compatibility. It uses many conventions of [Ergo-L](https://github.com/Nuclear-Squid/ergol).

TL;DR
--------------------------------------------------------------------------------

* a keyboard layout optimized for French and English
* uses a dead key for the most frequent accented characters
* uses the AltGr layer for programming symbols
* fits on 30 keys for compact keyboards compatibility
* trades easy access to common shortcuts for full optimization
* lower SFB and LSB than most previous French layouts
* few redirects, at the cost of few rolls

See the [design notes](NOTES.md) for the details, and join the [Ergo-L discord](https://discord.gg/RH34GjQEgC) to discuss the layout with us. [Check the stats!][1]

[1]: https://lysquid.github.io/Erglace/stats#/erglace/ol40/en+fr

> La différence avec [Ergo-L](https://ergol.org/) ?
>
> Erglace abandonne l'accès facile au raccourcis usuels (Ctrl+C, Ctrl+V, ...) pour atteindre de meilleurs statistiques, en particulier un SFB plus bas, sous les 1%. Le SFB correspond aux enchaînements de deux caractères qui utilisent le même doigt, ce qui ralentit la vitesse de frappe.
>
> L'autre différence est qu'Erglace cherche à minimiser les redirections, c'est-à-dire les enchaînements de trois caractères d'une même main avec un changement de direction, mouvement considéré comme inconfortable. Pour ce faire, toutes les voyelles se retrouvent d'un côté, comme en Bépo, ce qui favorise l'alternance des mains. Le désavantage est que la disposition a moins de roulements, c'est-à-dire des enchaînements de trois lettres d'une main dans une même direction, qui peuvent être appréciables.
>
> Au-delà du placement des lettres, Erglace a les mêmes fonctionnalités qu'Ergo-L. La couche de symboles est directement reprise de ce dernier.

Layout
--------------------------------------------------------------------------------

![base layout](img/erglace.svg)

The dead key <kbd>★</kbd> gives access to all accented letters you’ll need to write in proper French:

![dead key layout](img/erglace_1dk.svg)

… and the AltGr layer is fully dedicated to programming symbols.

![altgr layout](img/erglace_altgr.svg)

[Try it out!](https://lysquid.github.io/Erglace)

Install
--------------------------------------------------------------------------------

You’ll need the latest version of [Kalamine][2] to build your own layout. We
*highly* recommend using [pipx][5], once you have it installed (by following
their guide), you can just run the following command:

```bash
pipx install kalamine
```

Download the [layouts/erglace.toml][4] file in this repo and build the layout :

```bash
kalamine make erglace.toml
```

You’ll get a `dist` folder containing all of the drivers.

Then, to install Erglace, follow the [install section of Kalamine’s repo][3],
and you should be good to go !

[2]: https://github.com/fabi1cazenave/kalamine
[3]: https://github.com/fabi1cazenave/kalamine#installing-distributable-layouts
[4]: layouts/erglace.toml
[5]: https://github.com/pypa/pipx?tab=readme-ov-file#install-pipx


### Install (Linux only)

`xkalamine` is a linux‑specific tool (shipped with `kalamine`) to easily
install keyboard layouts on Linux. You can drop `sudo` if you use wayland, but
it’s required on Xorg.

```bash
sudo xkalamine install erglace.toml  # Install the layout
```

Then switch to Ergo‑L using the following command:

```bash
setxkbmap fr -variant erglace  # Switch your keyboard layout to erglace
```

Make Your Own !
--------------------------------------------------------------------------------

If you wish to modify the layout, the `layouts/*.{toml,yaml}` are human-readable
ASCII arts of the final layout. You can easily edit them, then run `make` (or
`make watch`) at the root of the repo to generate the `.json` files used to
benchmark layouts on the [stats page][1].

This repo contains all of the code for the [Ergo‑L website](https://ergol.org),
so you can run the page locally to try your prototypes !
