# Sound Design

## Basic Waveforms

1. Sine Wave
    * "Smooth sounding".
    * Only one harmonic.
    * Useful in bass sound designs.
    * Often kick drums are reinforced with a sine wave.
2. Triangle Wave
    * "Buzzing sound".
    * Fundamental tone with added harmonics.
3. Square Wave
    * A lot more buzz.
    * Many more harmonics.
    * Harmonically rich in the top-end.
4. Saw-tooth Wave
    * Even more "harmonically rich" and "buzzy" sounding.
    * Also rich in the top-end.

## Additive Synthesis
Start with one waveform and add another waveform to it.

For example, start with square wave and add a sine wave to it.

## Subtractive Synthesis
Start with one waveform and subtract from it.

For example, start with saw wave and filter off the top-end with an equalizer.

Many synthesizers have filters built in.

## Unison
Adds more voices to the sound. Make it sound more "rich".

Duplicate, pan, and detune sound around stereo field.

Each voice is *sligthly* detuned from the original voice, to make it sound thicker and fuller.

## Filters
Like EQ.

Low pass filter. Move cutoff. Allows low frequencies to pass and cuts-off high frequencies.

## Envelopes (ADSR)
Determines volume and shape of sound when we press keys.

* **A**ttack
    * More attack for a "pad sound".
* **D**ecay
    * How long it takes to "decay" from maximum to where we sustain.
* **S**ustain
    * After we reach maximum (attack), what value do we want to hold the sound on?
* **R**elease
    * How quickly the sound dies off.

Decay and sustain are closely linked.

## LFOs (Low Frequency Oscillators)
Can add movement an automation to any parameter in the synth -- usually the filter.

Not used to make sounds by themselves, but change parameters (like frequencies, amplitudes, or the filters).

## Visualizing Waveforms
An **oscilloscope** provides a visual representation of a waveform over time using a two-axis graph.

* [x42/sisco.lv2](https://github.com/x42/sisco.lv2) - Simple Scope

```
sudo apt install x42-plugins
```

A **spectrum analyzer** can view harmonics.

## Sounds

### Korg M1 Organ Bass Robin S. "Show Me Love"

https://www.musicradar.com/tuition/tech/how-to-create-a-korg-m1-style-organ-bass-sound-642650

## References

* [[YouTube] In The Mix: Sound Design and Synth Fundamentals](https://www.youtube.com/watch?v=NJLIS2MkFe4&t=286s&ab_channel=InTheMix)
