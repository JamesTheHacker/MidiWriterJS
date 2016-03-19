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
```js
// Start with a new track
var track = new MidiWriter.Track();

// Define an instrument (optional):
track.addEvent(new MidiWriter.ProgramChangeEvent({instrument : 1}));

// Add some notes:
var note = new MidiWriter.NoteEvent({pitch:['C4', 'D4', 'E4'], duration: '4'});
track.addEvent(note);

// Generate a data URI
var write = new MidiWriter.Writer([track]);
console.log('data:audio/midi;base64,' + write.base64());

```