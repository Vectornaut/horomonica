# hormonica

This is a virtual implementation of the instrument described in Bob Penner's ["Music of moduli spaces"](https://www.ihes.fr/bibliotheque/#prepublications) (IHÉS preprint M/21/12).

## To do

* Display (Aaron)
* Click mapping (Aaron)
* Sound
  * The [Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API) seems to include powerful audio synthesis tools. Since we want to play pretty simple waveforms at arbitrary pitches, synthesizing audio in the browser might be best.
* Multitouch (François)
  * To play smoothly, the instrument needs to register very fast sequences of taps, and maybe even simultaneous taps.
  * Dragging with two fingers to move the instrument would be useful for configurations with lots of strings.
* Instrument representation
  * The instrument is made of triangles glued along edges.
  * We need representations for three purposes: tuning, sound, and display.
    * Is the edge adjacency table described under "display" usable for all purposes?
  * Tuning
    * Need ability to "flip" edges, as shown in Figure 1 of the preprint.
    * Need ability to edit a float-valued "λ-length" for each edge.
  * Sound
    * Need access to λ-lengths.
  * Display
    * Given λ-lengths, need to compute a float-valued "shear coordinate" for each edge.
    * Need a table where you can take an oriented edge and look up the other two edges of the triangle you're oriented toward.
    * The shader needs to store this representation using only arrays, since Open GL shader language doesn't have pointers.
