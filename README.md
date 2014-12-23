# MoodyRain

**MoodyRain** is an ambient soundscape generator for Linux. It is inspired by Rainymood, A Soft Murmur, and similar web services.

## Table of contents

<!-- MarkdownTOC -->

- [Installation](#installation)
    - [Dependencies](#dependencies)
    - [Setup](#setup)
- [Usage](#usage)
    - [Overview](#overview)
    - [Additional sounds](#additional-sounds)
    - [Known issues and limitations](#known-issues-and-limitations)
- [Credits](#credits)
- [License](#license)

<!-- /MarkdownTOC -->

## Installation

### Dependencies

MoodyRain depends on `yad`, `mpv`, and `exiftool`. On Ubuntu 14.04 and up you can install all dependencies with the following commands:

    sudo add-apt-repository ppa:webupd8team/y-ppa-manager
    sudo apt-get update
    sudo apt-get install yad mpv libimage-exiftool-perl

### Setup

1. Install all dependencies

2. Clone this repository or download the latest zip-file and extract it

3. Navigate to the extracted folder and run `moodyrain`

4. (optional) Add `moodyrain` to your PATH and install the launcher by moving `MoodyRain.desktop` to one of the launcher directories (e.g. `~/.local/share/applications`)

## Usage

### Overview

MoodyRain comes with a simple `yad` GUI that consists of a sound selection screen...:

![image of selection screen](https://raw.githubusercontent.com/Glutanimate/MoodyRain/master/screenshots/selection-gui.png)

...and a systray icon:

![image of selection screen](https://raw.githubusercontent.com/Glutanimate/MoodyRain/master/screenshots/systray.png)

From the selection screen you can customize which sounds to play. If you want to disable a sound you can simply set its volume to zero. 

After you're done configuring your soundscape, start the playback by pressing *Play* or *Save and play*, the difference being that the latter saves your soundscape for future use. The config file is written to `~/.config/moodyrain.cfg` by default.

To change your ambience or stop the playback, right-click on the systray icon and select the corresponding option.

### Additional sounds

Moodyrain comes with five different ambiences by default, but these can be extended by placing additional `.ogg` files in the `sounds` directory next to the script. You will be able to achieve the best results with seamless high-fidelity loops. Please make sure to fill out the `Title` and `Artist` tags when creating your `.ogg` files.

For further information on composing your own ambient sound samples check out the [*Sounds* section of the Ambientsounds project](https://github.com/Muges/ambientsounds#sounds) by [Muges](https://github.com/Muges).

Please feel free to file pull requests to add more sounds to the repository, as long as you make sure to only use free sounds (public domain/creative-commons). [Freesound](http://www.freesound.org/) is a great source for such samples.

### Known issues and limitations

- Moodyrain uses a very rudimentary config file that will get confused when you add new sounds or change the order of the existing ones. I might implement a more sophisticated solution when I have some time on my hands. In the meantime please feel free to contribute pull-requests!

- Resource usage scales linearly with the number of sounds you choose. MoodyRain will launch a new `mpv` instance for each file. While this won't be much of an issue for most users, it might pose a problem if you are planning on composing a particularly complicated soundscape (with more than 10 different tracks)

- some `yad` builds suffer from a text misalignment bug. [More details and notes on possible solutions](https://github.com/Glutanimate/PDFMtEd/blob/master/README.md#known-issues).

## Credits

I would like to extend my heartfelt thanks to [all the original artists](https://github.com/Glutanimate/MoodyRain/tree/master/sounds) without whom this project would not have been possible.

In particular I would like to thank [Muges](https://github.com/Muges) for letting me use their seamless samples for MoodyRain. Please make sure to check out their project [Ambientsounds](https://github.com/Muges/ambientsounds), a curses-based ambient sound player with realtime-adjustable sound levels.

I would also like to thank [orschiro](https://github.com/orschiro) for [giving me the idea for this project](https://www.reddit.com/r/linux/comments/2ojm44/is_there_a_linux_alternative_to_noizio_ambient/).

## License

*MoodyRain copyright 2014 Glutanimate*

MoodyRain is licensed under the [GNU GPLv3](http://www.gnu.de/documents/gpl-3.0.en.html). For detailed licensing information concerning the sound files in this repository please consult [this page](https://github.com/Glutanimate/MoodyRain/tree/master/sounds).