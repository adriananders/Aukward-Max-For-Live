<h1>User Guide</h1>

Inspired by tempo automation patterns found in IDM productions, Aukward is a 16-step tempo automation sequencer for Ableton Live with Max For Live. It is a "MIDI Effect" which does not produce any output, not even pass through. It is intended to be placed on its own MIDI lane seperate from instrument tracks. Aukward based on sequencer position sends tempo automation data to Live based on either interpolated sequenced values or random noise. Sequencer is not free-running, dependent upon Live's internal sequencer position for position in the step sequence. For performance reasons frequency of tempo update signals are set to a maximum of 96ppq (pulse per quarter note) which can be further quantized with "Quant" parameter values up to a full sequencer beat. Product has been tested with internal Ableton Live devices, but may experience unexpected behavior with software or extrenal devices which rely on a stable MIDI clock. By its nature, the fast ramping of tempo in Aukward may distrupt timing in unexpected (and interesting) ways. Feel free to reach out to share your experiences with syncing tools to Live being manipulated by Aukward as well as any other feedback.

<h2>Requirements</h2>
  <ul>Ableton Live 10</ul>
  <ul>Max 4 Live 8</ul>

<h2>Usage</h2>

Add the file [Aukward-Tempo-Sequencer.amxd](/devices/Aukward-Tempo-Sequencer.amxd) to your preferred Max For Live MIDI Effects Path.<br>
Drag and drop the patch into an available empty MIDI channel.<br>
<b>Note</b>: Aukward does not contain MIDI pass through and will block MIDI from reaching instruments in the same MIDI channel.<br>
Upon playback, Aukward takes over project tempo automation and settings from Live. <br>
Automation and global tempo "center" should be set from Aukward rather than default Live settings and automation.<br>
Defaults are set to a fixed 120 BPM with no sequencer adjustments or random BPM fluxuations. <br>
Change sequncer step values or random amount then press play to see the effect in action.<br>

<h2>Parameter Guide</h2>

<h4>Step Sequencer</h4>
<img src="/img/01-seq.png" alt="Step Sequencer">
16-step sequencer which can have individual steps set +/- 0.0-999.0 BPM. <br>
These values are interpolated between individual steps, producing gradual tempo shifts around the central BPM point.<br>

<h4>Tempo Center</h4>
<img src="/img/02-center.png" alt="Tempo Center">
BPM value which acts as a "center" point for further tempo adjustments. Replaces Live's master tempo.<br>

<h4>Random Amount</h4>
<img src="/img/03-random.png" alt="Random Amount">
Range for random BPM value adjustments. From 0.0-999.0 BPM.<br>

<h4>Random Quantization</h4>
<img src="/img/03-rquant.png" alt="Random Quantization">
"Quantizes" or reduces the ppq for random BPM variation from 96.0 down to once per sequence step (whose ppq varies). Produces slower random variation.<br>

<h4>Sequencer Speed</h4>
<img src="/img/04-sspeed.png" alt="Sequencer Speed">
How fast the sequencer moves between steps. 1 is one beat per step.<br>
Moving to the right from the center increases the speed to sub-step divisions.<br>
Moving to the left from the center slows the seqence down to multiples of beats per step.<br>

<h4>Sequencer Quantization</h4>
<img src="/img/05-squant.png" alt="Sequencer Quantization">
"Quantizes" or reduces the ppq for ramped BPM interpolation between steps from 96.0 down to no interpolation.<br>
Produces a "stair-step" rather than gradual change between BPM values.<br>

<h4>Enabled</h4>
<img src="/img/06-enabled.png" alt="Enabled">
Bypasses the effect, snapping the BPM back to the value set before the effect was turned on.<br>
Intended to allow the user to switch from Aukward controlled tempo to native Live master and back.<br>


<h2>Tips, Tricks, Notes, & Recommendations</h2>
  <ul>Aukward is capable of extreme settings, please be aware of this with initial usage. Start with small changes.</ul>
  <ul>Aukward should only be used on its own individual MIDI channel as it offers no MIDI passthrough.</ul>
  <ul>No testing with external MIDI devices nor software with internal sequencing has been performed. May produce unexpected behavior.</ul>
  <ul>Ableton Live's BPM range is 20.00 - 999.00. As a result all values produced from Aukward are truncated to fit in this range.</ul>
  <ul>Use enable/disable to switch from Aukward back to native Live master tempo and automation.</ul>
  <ul>Quantization can slow the BPM changes down to be less busy and therefore may reduce CPU overhead and negative erratic timing errors which Aukward may produce in certain situations.</ul>
  <ul>Precise "average" tempo from Aukward may be difficult to calculate prior to audio rendering. This is not a product recommended for producing easy to DJ-mix steady-state bpm tracks.</ul>
  <ul>Aukward is not a "free-running" sequencer and may not appear to be doing anything when initially loaded. Requires Live to be playing in order to see any tempo adjustments.</ul>