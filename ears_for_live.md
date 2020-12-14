# Ears For Live
## Kieran Maraj

## 1. INTRODUCTION

Listening is perhaps the most important process in the creation of music. Musicians must listen to each other, be sensitive to the tendencies of their collaborators, and be dynamic and responsive to the things that they hear. Without listening, the creation process cannot happen. Ears for Live attempts to extend the work of listening to the machine.

Ears for Live brings an abstracted listening process into the realm of digital music creation.It is a tool that allows electronic musicians to create control signals through machine listening of real time audio. It allows for the creation of interactive instruments and sonic systems where control can be fully or partially driven by real time sound signals. The device can “listen” to a sound for particular acoustic features, including loudness, pitch, and timbre. The output of the listening is used to create control signals that can be mapped by the user to other sound control parameters in the digital audio workstation. Multiple ears can be loaded in the environment to listen to different sources and different features and used to create complex feedback networks where multiple processes can influence each other. An Ear device can listen to individual performers or streams of audio, or listen more globally to entire mixes or live microphone feeds. An Ears for Live device allows for sound to control sound.

Ears for Live was developed to facilitate the creation of digital musical systems and instruments that can be responsive and dynamic. Often in working with digital music systems, a musicians’ attention can often be pulled and focused on the technological system - tuning and tweaking parameters, in a way pulled away from the sound itself. This can become more apparent in collaboration, where attention is pulled away from what other performers are doing and instead pulled towards the system itself. Ears for Live will instead extend and augment the performers’ listening, controlling parts of the sound generating system according to what it hears in real time. 

Ears for Live has been developed as a Max for Live device that can be used in the digital audio workstation Ableton Live. Ableton is a very common piece of software for studio production and live performance. Ears for Live attempts to bring real time machine listening to Ableton in the form of an accessible tool. While I am particularly interested in experimental music, I’m curious as to whether people working in other styles of music would find Ears for Live to be useful additions.

![E4L](https://github.com/kieranmaraj/digm5010/blob/gh-pages/images/e4l/defaultDevice.jpg?raw=true)

[![IMAGE ALT TEXT](http://img.youtube.com/vi/C5HYo9AVDkc/0.jpg)](https://www.youtube.com/watch?v=C5HYo9AVDkc "Loudness to Volume")

*Video demonstrating drum loudness to synth volume mapping*

[![IMAGE ALT TEXT](http://img.youtube.com/vi/ZlhP1QAwRbQ/0.jpg)](https://www.youtube.com/watch?v=ZlhP1QAwRbQ "Pitch to Pitch")

*Cello pitch to synthesizer pitch mapping*

## 2. CONTEXT

Ears for Live draws on inspiration from several different areas within and around the field of computer music, including Music Information Retrieval, audio descriptor-driven synthesis systems, and sonic feedback systems.

### 2.1 Music Information Retrieval

Music Information Retrieval (MIR) is a field in which pieces of digital audio are computationally analyzed and perceptual qualities of given audio files are quantified (“What Is Music Information Retrieval?” n.d.).. The audio, as the name suggests, is usually musical, though the analysis tools can be applied to any digital audio file. MIR attempts to analyze the qualities of a sound that humans can identify - qualities like pitch, timbre, tempo, structure, and genre, to name a few - and translate those qualities into numerical representations. 

MIR draws on the world of digital signal processing and signal analysis. From a piece of audio, MIR analyses attempt to produce different descriptors of the sound. These can be high level descriptors - qualities such as mood or style - or lower level - fundamental frequency of a sound or various descriptions of a sounds spectral representation. These descriptors can be used for a wide range of purposes, from tasks like music recommendation algorithms, to computational transcription of songs, or to separate out the source instruments of a song into their own audio files. MIR algorithms allow for computational understanding of psychoacoustics (Jehan 2005) as experienced by human listeners, providing an entry point for constructing digital listening systems.

### 2.2 Descriptor-Driven Synthesis

Within the field of digital musical instruments (DMI), there have been a number of systems that make use of audio descriptors. One of the common tasks in MIR is to take databases of music, extract features from that music, and use the descriptors to organize the database. DMIs, such as the CatART (Schwarz 2007) system, have made use of the organizational capabilities to create instruments that function through the use of constructed timbre spaces (Wessel 1979). In CatART, a set of audio files is segmented into smaller portions and each segment of audio is analyzed for it’s timbral characteristics, making use of descriptors like fundamental frequency, spectral skew, periodicity, and other audio descriptors. These grains of sound can be organized in a 2D space according to their descriptors. A performer can move through this space, with a mouse or digital tablet, for example, and as they pass over a grain, it is played back via concatenative synthesis. Performing the instrument becomes an act of moving through timbral space.

Timbre spaces like those found in CatART have also been a fundamental part of the audio mosaicing technique. In audio mosaicing, a database of sound sources is segmented and organized, similar to CatART. Performance of this database, however, takes place using an input sound. In the Moesevius (Lazier and Cook 2003) system, a realtime audio input is analyzed with the same descriptors as the sounds in the database (or a subset of those descriptors) and as bits of realtime audio audio are analyzed, the closest matching segment in the database is played back. It is a process of timbral matching and weaving a new audio signal out of the pieces of a multitude of already existing pieces of audio.

Realtime audio feature extraction can also be used as parameters to control sound synthesis. In (Jehan 2001) the authors describe a system that makes use of an analyzed database, analyzes an incoming realtime sound, and spectrally resynthesizes the input sound. Through use of audio descriptors, the input sound can be cross-synthesized and morphed to sound partially like itself and partially like material in the database - for example, the authors describe an instrument that is part flute and part saxophone, with spectral qualities of both. Audio descriptors here are used to generate novel timbres.

A common feature of these systems is that they aim to match timbral characteristics of an input sound to sounds within a database. Ears for Live deviates from this - matching is not the goal. In my experience working with amplitude envelope following tools, the most interesting results have often been in creating arbitrary mappings. Instead of mapping amplitude of one sound to amplitude of another, it has been more fruitful to create a coupling between, say, amplitude of one sound, and the delay feedback of another process. It can become a method of creating liveliness and variety. Ears for Live attempts to open up audio features for arbitrary mappings to any synthesis process, as opposed to matching the feature of an input sound to the corresponding feature of some synthesis process.

### 2.3 Sonic Feedback Systems

Sound based feedback systems have a rich history in electronic and experimental music. In a sonic feedback system, an input sound is fed into the system, transformed in some way, and then sent to the systems outputs, which are connected back to its inputs. It is an abstracted listening process - the system takes an input, responds to it, takes an input again, and responds again, ad infinitum. Feedback systems can produce incredibly rich and dynamic results - small adjustments to the systems parameters can result in massive sonic changes. Feedback systems are nonlinear in their response, oftentimes with chaotic tendencies or behaviours that converge to a singular point (Sanfilippo and Valle 2013). A classic example of a musical feedback system is the no-input mixer - an instrument in which a standard audio mixer is taken and its output channels directly plugged back into its inputs, resulting in a sonic space that can be chaotic and noisy, or performed in beautiful, minimalistic fashion (Nakamura 2000).

A more complex example is the Audible Eco-Systemic Interface (AESI) (Di Scipio 2003). AESI is a system in which all interaction takes place, and its builder argues that all interactions within an interactive sonic system should take place through sound. The system makes use of microphones as ears to listen to the real world acoustic output of a synthesis process. The signal from the microphones has feature extraction performed on it, and is used to control the audio generation - all interaction with the piece takes place through sound. A person in the room making noise will get picked up by the microphones, and even though that noise might not have originated in the system, it affects the system. Di Scippio particularly notes that it is the rate of events, and not usually the direct features themselves, that are used to control the sound generation processes. 

Ears for Live allows this sonic interaction to take place within the Ableton environment. Multiple ears can be loaded at once to listen to different qualities of different sources and mapped out to different processes. The output of one Ear can even be applied to the listening parameters of another Ear. Ears for Live can be set up to create complex feedback systems where listening and processes become coupled. For example, a pair of Ears could be listening to a pair of synthesizers. Ear A listens to Synth A and maps controls to Synth B. Ear B listens to Synth B and maps controls to Synth A. A change in either synthesizer will result in a change in the other, and then process repeats. From this can emerge unexpected sonic behaviour. Additionally, it allows for shared control - the performer can still play and perform aspects of one or both synthesizers, while the control from the Ears happens in parallel.

![E4L](https://github.com/kieranmaraj/digm5010/blob/gh-pages/images/e4l/crossMapping.jpg?raw=true)

[![IMAGE ALT TEXT](http://img.youtube.com/vi/yKXx3FKVUzA/0.jpg)](https://www.youtube.com/watch?v=yKXx3FKVUzA "Cross Mapping")

*Video demonstrating cross mapping*


## 3. IMPLEMENTATION

Ears for Live are constructed as Max for Live devices and operate within the Ableton Live digital audio workstation. Making use of Live’s audio routing system(“Mixing — Ableton Reference Manual Version 10” n.d.), an individual Ear can listen to audio at a number of points from within the total sonic environment. These include: 

	-	Listening internally to a single channel of the Live system
	-   Listening internally to a group of channels of the Live system
	-   Listening externally to a close miced instrument or direct signal from an electronic instrument
	-   Listening externally to a room microphone

An Ear can listen to an individual track - as in a microphone feed, a recorded piece of audio, or an audio stream from a synthesizer plugin - or groups of tracks can be routed to the Ear. By making use of Live’s routing, the musician can shift the Ears listening focus from a specific scope, like listening to an individual kick drum, to an increasingly global scope, like listening to an entire drum kit, or listening to entire submixes of several instruments. A musician could also potentially take in a direct audio feed from a collaborator, or a room mic capturing the entire performance space, and feed these signals into the Ear. This defining of scope is dynamic and can be changed within performance. 

From there, an Ear device performs feature extraction on the input signal, generates a control signal, and controls some set of user defined parameters.

### 3.1 Audio Feature Extraction

An Ears for Live device can perform one of three types of feature extraction to generate a control signal. Just as a musician might change the specific aspect of sound they are listening to - the precise feel and timing of a drummer versus the timbral quality of an electronic drone - an Ear can listen in different ways and to specific qualities of a sound. There are three features an Ear device can listen for, and the feature extraction is performed using the Mubu (Schnell et al. 2009) library of Max MSP external objects. The three types of perceptual features an Ear can listen for are:

	-   Loudness: The simplest listening mode in which the Ear listens to the perceptual loudness envelope of the incoming signal
	-   Pitch: In this mode the Ear attempts to extract the fundamental frequency of the incoming signal via a yin pitch tracking algorithm (De Cheveigné and Kawahara 2002).
	-   Timbre: In addition to the fundamental pitch, the yin algorithm also produces a ‘periodicity’ value. This is used as a simple estimate for timbral quality. At one end of the spectrum is a ‘noisy’ signal, like a wall of insects chirping or a drum kit, and at the other is a ‘tonal’ quality, like singing bowls.
	
Next, the extracted feature is used to generate either a continuous or discrete control signal.

### 3.2 Continuous Control Signals

Continuous controls directly control a user specified parameter. An Ear device can generate a continuous control signal from either the normalized extracted feature, or from the first derivative of the extracted feature - how much has the feature changed over a period of time. This period of time is also dynamic and can be changed. Then the signal is passed through a smoothing filter, with the degree of smoothing itself being a mappable control. The user can choose from one of these two control signals, or they can choose to use one of these signals to measure a “density of events.” In this density mode, the user defines a threshold, and the frequency with which either the raw feature or its derivative passes the threshold becomes the control signal. 
Next, the control signal is passed through a transfer function. This transfer function can be graphically and intuitively defined by the user, with the potential to create plateaus and curves in the mapping. Finally, they press the Ear’s “map” button and then click on the parameter in Ableton that they want the Ear to control and the mapping is created.

![E4L](https://github.com/kieranmaraj/digm5010/blob/gh-pages/images/e4l/mainDisplay.jpg?raw=true)

![E4L](https://github.com/kieranmaraj/digm5010/blob/gh-pages/images/e4l/transferFunction.jpg?raw=true)


### 3.3 Discrete Controls

The other type of control signal an Ear device can produce is a discrete control. Discrete controls are instantaneous impulses. In discrete mode, either the raw feature or the delta of the feature is compared against a user set threshold. Whenever the feature signal passes the threshold, a discrete impulse is generated and a new value is sent to the mapped parameter. This value can either be a random value, or it can be randomly selected from among a set of values that the user can set.

![E4L](https://github.com/kieranmaraj/digm5010/blob/gh-pages/images/e4l/threshold.jpg?raw=true)

[![IMAGE ALT TEXT](http://img.youtube.com/vi/xZdIQjRHhc4/0.jpg)](https://www.youtube.com/watch?v=xZdIQjRHhc4 "Discrete control of granular processing")

*Discrete control of granular processing*

## 4. FUTURE WORK

### 4.1 Adaptation and Memory

An Ear for Live device presents the user with many options for directing the way the Ear might listen - particular features, smoothing, raw vs delta, etc. Part of the goal of this work is to create a tool that allows the user to pay more attention to their collaborators by allowing the machine to take on part of the listening process, to bring embodied human processes to the machine and allow those processes to be augmented (Herndon, Dryhurst, and Dockray 2020). However, the array of available controls could potentially result in the opposite - where the performer spends more time ‘tuning’ the Ear device than they do paying attention to their collaborators. To this end, I hope to develop a system that allows an Ear device to tune itself, to self-adapt.

This process of choosing what is important to listen to and what features to pay attention to happens for humans both through the evolved physical characteristics of the ear, and through psychoacoustic processing of the sounds we hear. I will seek to bring a similar behaviour to Ears for Live. Instead of the performer needing to choose exactly what feature to use, or where to set thresholds, or how much smoothing should apply, the Ear device will do this automatically based on what it hears. It additionally will have a short term memory - keeping track of the sounds it has heard over a given session, and using that information to guide the adaptive listening process. The Ear itself will be able to guide its listening, based on what it has heard previously and what it hears in the present, to move the system towards moments of stasis, or to move dynamically and create variety and diversity. 

### 4.2 User Study

I would also like to distribute Ears for Live to conduct a small user study. How do people end up using it, what kinds of mappings do they find useful? I’d like to hear how people use it in solo contexts, as well as working in small groups. Does working with the device at all change the way they find themselves listening?

## 5. CONCLUSION

Listening is at the heart of music making. By extending the listening capabilities of machines, can that possibly free up human performers to give more attention to their collaborators and listen in new ways? The Ears for Live project attempts to explore this possibility.

## REFERENCES

De Cheveigné, Alain, and Hideki Kawahara. "YIN, a fundamental frequency estimator for speech and music." The Journal of the Acoustical Society of America 111, no. 4 (2002)..

Di Scipio, Agostino. “‘Sound Is the Interface’: from Interactive to Ecosystemic Signal Processing.” Organised Sound 8, no. 3 (2003): 269–77. https://doi.org/10.1017/s1355771803000244.

Herndon, Holly, Mat Dryhurst, and Sean Dockray. 2020. “Inhuman Intelligence: Holly Herndon and Mat Dryhurst in Conversation with Sean Dockray on Disclaimer.” Disclaimer.org.Au. June 2020. https://disclaimer.org.au/contents/holly-herndon-and-mat-dryhurst-in-conversation-with-sean-dockray.

Jehan, Tristan. 2005. “Creating Music by Listening.” https://web.media.mit.edu/~tristan/Papers/PhD_Tristan.pdf.

Jehan, Tristan, and Bernd Schoner. "An Audio-Driven Perceptually Meaningful Timbre Synthesizer." Proc. ICMC'01. Havana, Cuba (2001).

Lazier, Art, and Perry Cook. 2003. “Mosievius: Feature Driven Interactive Audio Mosaicing.” Proc. of the 6th Int. Conference on Digital Audio Effects, September.

“Mixing — Ableton Reference Manual Version 10.” n.d. Www.Ableton.com. Accessed December 11, 2020. https://www.ableton.com/en/manual/mixing/#15-4-return-tracks-and-the-master-track.

Nakamura, Toshimaru. 2000. No-Input Mixing Board. CD. https://www.youtube.com/watch?v=qTi0hom6r44.

Sanfilippo, Dario, and Andrea Valle. 2013. “Feedback Systems: An Analytical Framework.” Computer Music Journal 37 (2): 12–27. https://doi.org/10.1162/comj_a_00176.

Schnell, Norbert, Axel Röbel, Diemo Schwarz, Geoffroy Peeters, and Riccardo Borghesi. "MuBu and friends–assembling tools for content based real-time interactive audio processing in Max/MSP." In ICMC. 2009.

Schwarz, Diemo. 2007. “Corpus-Based Concatenative Synthesis.” IEEE Signal Processing Magazine 24 (2): 92–104. https://doi.org/10.1109/msp.2007.323274.

Wessel, David L. 1979. “Timbre Space as a Musical Control Structure.” Computer Music Journal 3 (2): 45. https://doi.org/10.2307/3680283.

“What Is Music Information Retrieval?” n.d. Musicinformationretrieval.com. Accessed December 11, 2020. https://musicinformationretrieval.com/why_mir.html.


