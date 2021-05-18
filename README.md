# Scalable Vector Scope
Converts SVGs into 24-bit wav audio files to play into a vectorscope.

NOTE: Works best with graphics consisting of one polygon/polyline/path element. Does not work with curves... yet.

## Instructions
- Use the *scalable_vector_scope.convert()* function to generate audio. (See below)
- Play the audio into a vectorscope. The left audio channel should be connected to the X channel of the scope, and the right audio channel should be connected to the Y channel of the scope.

## scalable_vector_scope.convert(*svg_file, audio_file, cycle_amt=1000, sample_rate=96000, max_point_distance=0.01, split_stereo=False*)
Takes SVG file and writes it to an audio file.


- svg_file: *string*
  - Filename of the SVG file to be converted.
  - e.g. `"example.svg"`


- audio_file: *string*
  - Filename the audio file will be written to.
  - e.g. `"example.wav"`


- cycle_amount: *int, optional*
  - Number of times the resulting waveforms should be repeated.
  - Default is *`1000`* times.
  - Set to 1 if you need a single cycle.
  - Resulting audio file duration varies depending on sample rate, copmlexity of the SVG file, and max_point_distance.


- sample_rate: *int, optional*
  - The sample rate, in hertz, for the audio file.
  - Default is *`96000`* Hz.


- max_point distance: *float, optional*
  - Contiguous points will have points automatically placed in between them depending on their distance. This sets the max distance before a new point is inserted. 
  - Default is *`0.025`*. You should not need to change this.


- split_stereo: *bool, optional*
  - True: writes output to two separate wav files. The filenames are prefixed with *L* and *R*.
  - False: writes output to one stereo wav file.
  - Default is *`False`*.

## Usage


```python
from scalable_vector_scope import convert

convert("example.svg", "example.wav")
```
```
Saved to 'example.wav'
```
