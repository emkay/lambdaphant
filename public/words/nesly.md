When I [announced nesly-split](/words/introducing-nesly-split) here a couple weeks ago I also talked a little bit about the direction this was all going. Here is the progress of that so far.

The idea is that the entire project will make it easier to write and work with [NES](https://en.wikipedia.org/wiki/Nintendo_Entertainment_System) programs. To accomplish this I initially started writing [nesly](https://github.com/emkay/nesly). The eventual goal of `nesly` is to have it target a javascript like language and compile that down to [6502](https://en.wikipedia.org/wiki/MOS_Technology_6502) assember. I have some demos working, but overall it's pretty clunky and hacked together. It still is impressive though, at least to me. Along the way I realized it would be helpful to have tools to help out piece together these programs. One was [nesly-split](https://github.com/emkay/nesly-split), which allows you to rip out the CHR file, or character data, out of the program. This gives you access to the sprite sheet of many games. This is awesome, but I also want to be able to edit that data. There are some desktop tools that allow you to do this, but many of them are Windows only. There is one for OSX called [NES CHR Editor](http://www.romhacking.net/utilities/460/) that I've been using for testing, and it's great, but I still want an editor that works in the browser.

## Sprites!

While doing some research I came across [nodeNES](http://gutomaia.net/nodeNES/). This is pretty awesome as it almost does what I want. I wanted to build some smaller modules and throw them on npm though, so I contacted [Guto Maia](http://gutomaia.net/)and asked if I could rip apart some of his code and make it a module. He agreed, and now we have [nesly-sprite](https://github.com/emkay/nesly-sprite). It's not completed quite yet as I am just starting to actually use it now, and will be making changes to it along the way. The goal with this is to use it to read/write sprite data to a CHR file. I've started the [sprite editor](https://github.com/emkay/nesly-chr-edit) here.

## Demos

I gave a [short demo](https://github.com/emkay/spec-la-talk) recently and included the source, assembler, CHR file, and ROM. There is a lot of hacky stuff going on, but it's getting better. A couple things to note about the demos. 

* The `write` method is pointing to a specific range in the CHR file where the alphanumeric characters are
* When `write` doesn't fill up the row it throws in a default background
* There is some hard coded assmbler in there exposed through an `asm` method

Basically if the CHR file changes things will break. I'm trying to come up with ways around this, and I think better tooling will help. For example, if the sprite editor could save a CHR file and also save out data ranges of sprites it will be easier for the programmer to load sprites and backgrounds.

## JSFest

I'm speaking at [jsfest](http://jsfest.com)! I will be presenting specifically about these projects. If you want to know more, read [the abstract](http://jsfest.com/mains.html#emkay).
