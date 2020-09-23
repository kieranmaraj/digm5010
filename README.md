# digm5010
DM Foundations

## Journal 1

### Sketch #1: GrainSOM

	Looping is an important of my practice - the trajectory of my instrumentation included a path from guitar -> guitar with pedals -> guitar with laptop processing -> computer based instrumentation. Throughout that chain, looping has been a fundamental part. With it has come the challenge of using and interacting with loops that allows them to move beyond static repetitions with maybe variations in time or pitch - how can I capture some sonic input and have dynamically transform and react over time? Some of my recent performance systems have included looping control gestures - draw some sort of shape or path with a stylus, map it out to some synthesis process, and then loop that control data. Seeing the initial Yellowtail sketch, I instantly imagined each mark as a control gesture, and it’s movement in space a possible way for having it evolve over time.
	Trying to implement this also allowed me to start exploring something that’s been on my to-do list for awhile now: audio programming outside of a visual programming environment. I used the tone.js library as a starting point, but wasn’t particularly impressed with their default granular algorithm. I ended up basing my own implementation on the one at gloo.xyz. It feels like a vastly different way of thinking about audio than in Max or pd. One difference was a clear lack of differentiation between float values and signals, though I imagine this might just be own lack of familiarity with the API. A bigger difference, however, was in the interaction with scheduling events. Starting grains and envelopes seems to always involve taking the time at a given moment, as well as calculating when it will end. I feel like there’s no clear analogy to this in Max - I wonder is this kind of thing happening under the hood and completely extracted away? Overall it was a fun little challenge to sink into. I’ve become more interested in DSP programming over time, but don’t have the strongest math background and always find approaching this world intimidating and challenging.
	While I’m satisfied with this sketch as a first attempt, there are a number of things I would change on a second iteration. The main thing I would focus on is that the motion of each mark doesn’t clearly translate into what is heard in the synthesis. In its current state, I use a SOM trained on a set of random vectors to set synthesis parameters - as a mark traverses the screen, the head of the mark samples from the SOM and updates the synthesis parameters. I thought this might be an interesting way of creating variation and unpredictability, but also allow for a smoother morphing through synthesis states. However, I think the end result feels too decoupled from the marks motion.
	A few things I would do on a second iteration:
- A mark’s x position would set it’s grain’s panning position
- A mark’s y position would set the grain’s size
- Distance from centre of the screen sets sample position
- A mark’s change in velocity modulates it’s pitch - a sort of doppler effect
- A mark’s length controls the reverb mix for a grain - longer mark resulting in more reverb, or perhaps the reverse
- A mark’s alpha sets it’s grain’s volume
- The SOM would instead modulate synthesis parameters instead of directly setting those parameters

### No Input Mixing

The prompt to reflect on no input mixing was a nice excuse to revisit the practice, as its been a year or two since I last worried I might push my monitors too hard :)
	Part of the magic in no input mixing is that it feels like this dynamic, unpredictable beast, but as you spend time with it there are general mappings or shapes of mappings that are learnable, or at least knowable in the sense that in you can know that with x connections, turning up these sends will make these sliders effect this thing about the sound. But there’s always subtle variation. Every slight turn of a knob or push of a fader results in some connected change that you then have to react to as a performer. In a way it becomes a duet between human and machine. The mixer provides a sort of access point into a dense sonic world that must then be sculpted and shaped, and that shaping in turn effects and transforms that sonic world.

