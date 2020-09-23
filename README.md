# digm5010
DM Foundations

## Journal 1

### Sketch #1: GrainSOM

Looping is an important of my practice - the trajectory of my instrumentation included a path from guitar -> guitar with pedals -> guitar with laptop processing -> computer based instrumentation. Throughout that chain, looping has been a fundamental part. With it has come the challenge of using and interacting with loops that allows them to move beyond static repetitions with maybe variations in time or pitch - how can I capture some sonic input and have dynamically transform and react over time? Some of my recent performance systems have included looping control gestures - draw some sort of shape or path with a stylus, map it out to some synthesis process, and then loop that control data. Seeing the initial Yellowtail sketch, I instantly imagined each mark as a control gesture, and it’s movement in space a possible way for having it evolve over time.


<p class="codepen" data-height="377" data-theme-id="dark" data-default-tab="js,result" data-user="kieranmaraj" data-slug-hash="YzqvMPw" data-preview="true" style="height: 377px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="GrainSOM">
  <span>See the Pen <a href="https://codepen.io/kieranmaraj/pen/YzqvMPw">
  GrainSOM</a> by Kieran Maraj (<a href="https://codepen.io/kieranmaraj">@kieranmaraj</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>



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

Part of the magic in no input mixing is that it feels like this dynamic, unpredictable beast, but as you spend time with it there are general mappings or shapes of mappings that are learnable, or at least knowable in the sense that in you can know that with *this set of* connections, turning up *these* sends will make *those* sliders effect *this* thing about the sound. But there’s always subtle variation. Every slight turn of a knob or push of a fader results in some connected change that you then have to react to as a performer. In a way it becomes a duet between human and machine. The mixer provides a sort of access point into a dense sonic world that must then be sculpted and shaped, and that shaping in turn effects and transforms that sonic world.

The complexity and surprises of the system, while wonderful and exciting, present an interesting challenge, though. While it's a joy to play solo, and undoubtedly works well in improvised and/or noise contexts, playing no input mixer in anything even approaching a "traditional" ensemble is difficult. The sonic aesthetics of the system are one aspect of why this might be, but I think it's actually the unpredictability and reactivity of the instrument that present a bigger challenge. I can certainly imagine NIM squeals and jitters working in a rock context, or its overwhelming bass working in dance music - but perhaps only if performing those things is repeatable? 

This leads me towards an a potential area of research. I subscribe to Christopher Small's definition of 'music' as being socially constructed - that music is not the score, it's not the vinyl record, it's not the encoded mp3 file, or even the human perception of modulated air. Small defines music as being the set of social relations that come together to make up a musical performance - everyone from the performers themselves to the audience, sound engineer to custodial staff, all are involved to varying degrees in the act of musicking. So my question then is how does the involvement of machines, particularly 'intelligent' machines (whatever that might mean), complicate that set of relations? What does it mean if a machinic instrument can only be performed with other machines, or only in particular ways, to the exclusion of human performers?

## Literature Review - Part 1

I have to admit, the suggestion to project into the future an imagine what a field might look like has thrown me for a bit of a loop. Projections of the future look increasingly apocalyptic. I find myself asking questions about the purpose of music, performance, art in a climate apocalypse - and these questions are actually, I think, a little easier to grapple with. There is always value in art and expression, and comfort in times of strife. But, more specifically, what is the role of technologically mediated art in that environment? And, thinking of Small's definition above, who gets to be involved? Do technology based music become reserved for an affluent few? Are there ways that digital instruments/music making/performing exist to benefit a wider swath of people? Do these practices take on new roles? I don't know how to answer or really even engage with these questions, but they were in mind throughout my research process.

Some keywords:
- Digital music instruments
- Gestural interfaces
- Machine learning
- Computer music
- Interactive music systems
- Sound art
- Environmental sound
- Machine listening

On the last point, machine listening, I found something unexpected. In looking into machine listening, I was expecting to find work dealing with machine analysis and interpretation of sound, spectral analysis, auditory scene analysis, and so on. What was surprising was finding an emerging use of the term to refer to devices that listen and observe - smart phones that record audio surreptitiously, Amazon Alexas and Google Homes, smart TVs and IoT connected appliances - related to present issues around surveillance, privacy, control, and manipulation. This is another area that I'm very interested in - and that I do think is related in issues around machine learning and big data - but have struggled to figure out how to engage with creatively, or to synthesize with my sound and music interests. The apparent synchronicity of stumbling upon this new use of "machine listening" has me wondering if there is an interesting way to think about surveillance, sound performance, and musical systems - but maybe I'm going to broad when I should be narrowing in.



