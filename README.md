# osu!next Signature Generator v3
This is a signature generator written in PHP for osu!next style signatures. The design is based on flyte's design. Live version with the generator can be found [here](https://sig.sirohi.xyz).

## Usage
The generator itself is in `sig.php`. All templates accepts the following parameters:

* `uname` - **required** The username of the user you want to generate a signature for
* `colour` - The background and stroke colour of the signature. Valid values are any 6 digit hex value prepended by `hex` or `%23`, or:

	| Colour name | Hex colour |
	| ----------- | ---------- |
	| red | `#ee3333` |
	| orange | `#ee8833` |
	| yellow | `#ffcc22` |
	| green | `#aadd00` |
	| blue | `#66ccff` |
	| purple | `#8866ee` |
	| bpink | `#ff66aa` |
	| darkblue | `#2255ee` |
	| pink | `#bb1177` |
	| black | `#000000` |

* `mode` - The gamemode you wish to view stats for. `0` is osu!standard, `1` is osu!taiko, `2` is osu!catch and `3` is osu!mania.

TemplateNormal accepts the following:

* `pp` - Where you want the pp to be displayed. Undefined does not show at all, `0` shows in place of the level, `1` shows next to the accuracy and `2` shows above the rank.
* `removeavmargin` - If specified (no value required), there will not be a 3px margin between the card's stroke and the profile picture.
* `flagshadow` - Adds a shadow to the flag
* `flagstroke` - Adds a stroke to the flag
* `countryrank` - Shows your country rank (experimental)
* `darkheader` - Darkens the text in the header
* `darktriangles` - Darkens the triangles
* `opaqueavatar` - Adds a white background behind the avatar
* `avatarrounding` - Sets a custom rounding for the avatar - must be a numeric value
* `rankedscore` - Whether to show the ranked score in place of the Play Count or not

## Requirements

The generator requires ImageMagick and memcached.  
It also needs the file `p/.priv.php`. It's used to configure memcached's host and port. If you're not doing anything special and you're running memcached on `localhost:11211` (default), simply run `cp p/.priv.sample.php p/.priv.php` and you're good to go.

## Credits

Original project was made by Lemmmy. The mode icons and flags are designed by Flyte and can be found at his pixelapse [here](https://www.pixelapse.com/flyte/projects/osu!designs/files/). `triangles.png` and `triangles2.png` are made by Lemmmy, again.

## License

Everything except the following files are licensed under GPL-v3:

```
fonts/*
flags/*
modes/*
img/ctb.png
img/mania.png
img/taiko.png
img/osu.png
img/tris.png
```

The following files are licensed under AGPL-v3 and are from [this](https://github.com/ppy/osu-web) repository:
```
fonts/osu!font.ttf
img/ctb.png
img/mania.png
img/taiko.png
img/osu.png
```

The flags in `flags/*` are created by Muharrem Şenyıl and can be found on his [Dribbble](https://dribbble.com/shots/1211759-Free-195-Flat-Flags).