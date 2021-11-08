New computer arrives tomorrow, and to celebrate I thought I'd upload 
some of the proof-of-concept patches I've discussed here. They're 
somewhat academic and not finished patches (as such), just ideas I've 
come up with (or craftily borrowed/adapted) for smashing waves together 
for fun. An oscilloscope and optional spectrograph are recommended 

The patches: 

Windowed Sync 

This is a three oscillator setup meant to be controlled by the pads on 
the Performance page which have been meticulously set up. What this 
patch does, is create smooth "windowed" sync effects by amplitude 
modulating Zebra's normal synced waveforms with a variable waveshape 
(the windowing function) at the same frequency and with locked phase. 

Oscillator one is the basic sync wave, which can be mildly LP'ed and 
HP'ed, swept around, and can smoothly morph into all waveshapes (Tri, 
Saw, Square, Pulse, Impulse). 

Oscillator two is the windowing oscillator and acts effectively as an 
audio rate envelope or "window". This can be morphed thru a variety of 
shapes which have all been designed to smooth out the discontinuities 
and extra jittery harmonics of the nornal sync effect to various 
degrees, and generally alter the character of the formant effect. Notice 
that oscillator two has to be symmetrical, i.e. it's effectively two 
cycles, one pointing upwards and one pointing down (opposite polarity). 
This seems to be required to preserve the zero level of the waveform due 
to the fact that Zebra waveforms can't have DC offset (another way 
around it is to compensate with volume changes on the RM and clean 
lanes, but this only works if you know what waveforms are going to be 
present, and in this situation any wave is selectable). One downside of 
this is that each after each cycle of the master frequency the outputted 
wave changes polarity, and consequently the base saw waveform now sounds 
like a square due to the alternating 'teeth' - but this is only when at 
zero sync level (and as this is for making sync sweeps, it's a 
reasonable workaround!). 

Oscillator three is a sub-oscillator which can also be any waveshape. 
The idea of this is that you can HP the synced waveform a little and use 
the subosc to fill in a stable fundamental. 

Additive Squarewave Saw-Jiggler 

This is an octave stack of four squares balanced to create an 8-bit-ish 
sawtooth. Pressure alters the pulsewidth of all the waveforms in unison, 
creating beautiful fractal-like waveforms which lets you dissolve the 
saw into a cloud of pulses and then re-form it. The modwheel does the 
same thing, but with sync to all waves instead, creating a very busy 
sweep. 

AM Duty Cycle Noise 

Using the AM cancellation trick to cut regular and variable width holes 
in some noise. This has a really raspy crunchy tone to it which I enjoy. 
It's like the sound of stepping on snow squeezed into a note. I'm using 
an envelope to drive the PWM just because I like enveloped PWM effects 

AM Hyper-Sync 

Just two sync sweeps in opposing directions AM'ed together so that they 
cut holes in each-other. Move the modwheel and watch the waveform dance 

Barberpole Harmonics 

A patch showcasing one of my (painstakingly hand crafted) spectroblend 
wavetables with constantly rising harmonics. 

Ever Falling Wrapform 

It's supposed to give a sync-effect which is constantly falling. Works 
best on the higher half of the keyboard. Basically the wave is being 
stretched out, and at a certain point, new wave crests form in-between. 
Both of these opposing "forces" are created with Wrap FX with their own 
MSEG. You hear a constantly falling sync pitch with a cyclically rising 
formant (created by the 'new' wavefronts being drawn out). This 
explanation doesn't quite nail what's happening, but it gets the gist of 
it. 

Plastic Filter 

I mentioned this a while ago. It's a filter constructed out of Osc FX, 
complete with goofy PD-style resonance. Very unique sound I think... 
quite grungy and fizzly... The ironic thing is that after creating my 
"filterless filter", I had to bring in a notch filter to kill the rez 
when it's at it's highest point, because I didn't want the open filter 
sound to have a high-pitched tone all the time. Oh how I laughed! 

Tall Story 

This is an actual finished patch of mine. Just a demo of what you can do 
with one oscillator and a stack of coinciding MSEGs. Hold it for a long 
time. I'm going for complexity and intricacy rather than making one osc 
sound like 47. 

Triangle Wrap PWM 

Very simple example of how the Wrap FX can make PWM-type sounds. The 
trick is to modulate within a range that does not create any sudden 
jumps in timbre by introducing extra discontinuities (or removing them). 
You can increase the modulation amount slightly to see what I mean. 

Vector Maze Tonal 

Vector Maze is the patch I put on Soundcloud with the recursive and 
random vector mixing going on. Hold a note and play with all four X-Y 
pads! Now keep doing it! 

Vector Maze Atonal 

Same as above, except Pad 4 modulates things which disturb the pitches 
of the drone elements, creating something more cacophonous, less 
musically useful, but more amusing 

Vosim Inspired

Inspired by the video I posted the other day[1] on VOSIM and shaping sync
with audio-rate windowing oscillators I produced this patch... which
is nothing like it but uses sync in a similar way regardless.

It's horrible, and you probably won't enjoy listening to it[2], but to me
it's interesting. A sine wave is being multiplied by a phase locked variable
sync waveform, and the sine wave can assume and smoothly become any of 16
harmonics thanks to the spectroblend oscillator mode. No matter which
harmonic it sounds, 0 degrees phase will always be silence, smoothing out
the sync effect.

All the relevant parameters are assigned XY pads and played with, but I
also added parameters to change the ratio between the two oscillators,
creating rough discordant textures and what can only be described as a
downright racket.
1: http://www.youtube.com/watch?v=7GetTjx96D0 
2: http://soundcloud.com/sendysynthdemos/zebra-2-sync-hole
