---
layout: post
title: "How to record a high quality video with Quicktime and Soundflower"
date: 2017-05-14
---

The QuickTime Player shipped with Mac OS is able to record the screen with native resolution. When it comes to audio, you can easily configure it to use the internal microphone. 
However, you have to expect a poor sound, mixed up with noises in the house.
A better idea is to route the sound output of the recorded app to the input of
Quicktime. Default Mac OS is not flexiable to configure this.


Well, I came across an opensourced project that has this capablity.
Although seems obsolete and not maintained, it still works.
To use [Soundflower][sf], you have to first install the released dmg pacakge.
Then you should configure the `Audio MIDI setup` app shipped with Mac OS. With it,
you add a `Multi-Output Device`, which will output configured audios simutaneously.
Of course, you should check Soundflower as one of the output ports.
Then, you open the `Sound` setting in the `preference` panal, select Soundflower
as input, and `Multi-Output Device` as output.
Finally, in the Quicktime Recording interface, select microphone as soundflower. That's it. Now you can enjoy both native video and audio.

Some explainations.
I'm not a Mac expert, nor familiar with sound driver.
I suspect the recorded app outputs its audio signal to the 
`Multi-Output Device`, which outputs to both the build-in speaker and 
the emulated Soundflower. Soundflower, is simply a pipe that 
connects the input and output ports of itself.
Therefore, the output port of Soundflower is also streamed with
the audio signal of the recorded app, which is further captured by
QuickTime player.

[sf]: https://github.com/mattingalls/Soundflower/releases
