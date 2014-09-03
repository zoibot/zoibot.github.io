---
layout: base
title: nes
---

A while ago I wanted to see how hard it would be to write an emulator. I picked the NES because it seemed relatively simple and very well documented.
I started writing it in python, but quickly gave up due to performance issues. I got far enough to show the title screen of a few simple games like Donkey Kong and Mario Bros., but only was able to manage 6-7 FPS even after attempting some optimizations. I plan to write a little more about what I learned regarding python performance later. (As a side-note, I have been experimenting with this again now that pypy is stable enough and can run pyglet. Initial results seem promising.)
Since I wasn't going to get a playable NES emulator that way, I decided to take this opportunity to start learning Go, which was still fairly new at the time. I actually got to the point where some games were playable.
Finally, something kept drawing me back to C++. There's something it that seems to make certain aspects of low level emulation much easier. Compared to python, having defined number types that overflow in a predictable way is extremely useful. Go was good, but there were a few minor annoyances that made it less pleasant to code in. Part of the problem was the fact that it was so new and I was having to update my code all the time as the compilter updated. There were also some bugs I ran into in the SDL bindings. I also had some nit-picky style disagreements with it, like being forced to write if((var & 0xf0) != 0) instead of just if(var & 0xf0).
So anyway, my C++ version ended up being the most complete. It still has some major omissions, most notably audio. It also only has a handful of mappers implemented. I still plan on finishing the audio part before calling this project done.
