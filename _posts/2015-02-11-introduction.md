---
layout: post
title: Introduction
---

MidiWriterJS is a JavaScript library providing an API for generating expressive multi-track MIDI files from code.

```sh
npm install midi-writer-js
```
-----

### Quick Start
<div id="editor">// Start with a new track
var track = new MidiWriter.Track();

// Define an instrument (optional):
track.addEvent(new MidiWriter.ProgramChangeEvent({instrument : 1}));

// Add some notes:
var note = new MidiWriter.NoteEvent({pitch:['C4', 'E4', 'G4'], duration: '4'});
track.addEvent(note);

// Generate a data URI
var write = new MidiWriter.Writer([track]);
console.log('data:audio/midi;base64,' + write.base64());
</div>
<p>
	<a class="button" href="javascript:;" onclick="document.getElementById('midi-check').style.visibility='hidden';eval(editor.getValue());">Run</a>
	<a href="javascript:;" class="button" id="download-midi">Download Midi</a> <span id="midi-check" style="visibility:hidden;">&#10003;</span>
</p>
<script src="{{ site.github.url }}/public/js/ace/ace.js" type="text/javascript" charset="utf-8"></script>
<script src="{{ site.github.url }}/public/js/ace/mode-javascript.js" type="text/javascript" charset="utf-8"></script>
<script src="{{ site.github.url }}/public/js/midi-writer-js.js" type="text/javascript" charset="utf-8"></script>

<script>
    var editor = ace.edit("editor");
    var JavaScriptMode = ace.require("ace/mode/javascript").Mode;
    editor.session.setMode(new JavaScriptMode());
</script>
