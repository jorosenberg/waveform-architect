As a music producer learning sound design, I have been having trouble learning how to use different waveform modulations properly. I decided an app for visualizing just this would be perfect. This app helps me view the two oscillator waveforms creating a new waveform, showing how it affects loudness, and visualization of the phase as I change parameters. The web audio api was able to pretty much do all of this in the backend so learning the visualization math was the only real challenge. I believe it shows what I need it to, but I will play around with it and see what it shows me.    


# **🎹 Waveform Architect**

**Waveform Architect** is a high-fidelity, browser-based modular synthesis and signal visualization environment. Built with the **Web Audio API**, it allows users to explore complex frequency, amplitude, and phase modulation through a professional "rack-style" interface.

## **🚀 Quick Start**

1. **Power On**: Click the large **POWER** button in the top-left corner (or press Space) to initialize the Web Audio context.  
2. **Presets**: Select a preset (1–6) from the top bar to instantly load pre-configured modulation states like "Bell FM" or "Filter Sweep".  
3. **Controls**:  
   * **Click \+ Drag (Vertical)**: Change knob values.  
   * **Scroll Wheel**: Fine-tune parameters.  
   * **Double Click**: Manually type a numeric value.  
   * **Arrow Keys**: Shift the root note pitch (Shift for octaves).

## **🛠 Functional Modules**

### **1\. The Oscillators**

* **OSC A (Carrier)**: The core sound generator. Choose between Sine, Square, Sawtooth, and Triangle waves. Adjust octaves and semitones to set the fundamental frequency.  
* **OSC B (Modulator)**: A secondary oscillator that "shapes" the carrier. It features a unique **Routing Matrix** to determine how it interacts with Osc A.

### **2\. Modulation Routing**

Waveform Architect supports four distinct modulation modes:

* **AM (Amplitude Modulation)**: Osc B controls the volume of Osc A, creating sidebands.  
* **FM (Frequency Modulation)**: Osc B shifts the pitch of Osc A rapidly for metallic, bell-like, or harsh textures.  
* **PM (Phase Modulation)**: Similar to FM but maintains better pitch stability; the classic sound of 80s digital synths.  
* **RM (Ring Modulation)**: Multiplies the signals of Osc A and Osc B, stripping away the fundamental frequency for "robotic" or inharmonic tones.

### **3\. LFO & Filtering**

* **LFO**: A global low-frequency modulator that can be mapped to Pitch (Vibrato), Amplitude (Tremolo), Filter Cutoff, or Modulation Depth.  
* **Biquad Filter**: A state-variable filter (Low-pass, High-pass, Band-pass, etc.) with resonance (Q) control to carve out the frequency spectrum.

## **📊 Visualisation Suite**

The application includes four real-time monitoring panels to help you "see" the sound:

* **Chart Recorder**: A slow-scrolling time-domain view of the final output.  
* **Oscilloscope**: High-speed waveform traces. It visualizes the raw waves of Osc A and B alongside the resulting modulated output.  
* **Audio Imager (Lissajous)**: Plots Osc A (X-axis) against the Output (Y-axis). Ideal for visualizing phase relationships and harmonic complexity.  
* **Spectrum Analyser**: A 1024-band FFT analysis showing the frequency distribution from 20Hz to 20kHz.

## **💻 Under the Hood**

* **Web Audio API**: Uses a non-linear signal chain. Oscillators are connected to GainNodes and DelayNodes (for PM) which are updated at the audio thread level.  
* **Canvas API**: All visualizers are rendered at 60 FPS using requestAnimationFrame, pulling data from AnalyserNodes.  
* **Performance**: The app utilizes a global master compressor and a tanh saturation (Drive) function to ensure the output remains loud and saturated without digital clipping.

## **⌨️ Hotkeys Reference**

| Key | Action |
| :---- | :---- |
| Space | Toggle Power |
| Up / Down | Adjust Root Note (Semitone) |
| Shift \+ Up/Down | Adjust Root Note (Octave) |
| Esc | Reset all visualizers |

*Developed for experimental sound design and educational synthesis demonstrations.*
