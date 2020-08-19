# ASPI

**WORK IN PROGRESS**
This is a python package to convert MIDI files into an ASP representation and back.
It is highly modifiable. If needed the whole behavior can be modified but in general the standard one will do.

# Installation

1. install mido with ```pip install mido```
2. download or clone the git
3. copy the ASPI folder into your working directory
4. finished

# Basic Usage Guide

this guide also uses the clingo python package
```python
from ASPI import MIDI_to_ASP, ASP_to_MIDI
import clingo

atoms = MIDI_to_ASP("./midi_file.mid")
ctl = clingo.Control()
ctl.add("base", [], atoms)
# load more and then ground and solve...

mido_obj = ASP_to_MIDI(model)
mido_obj.save("./output_midi.mid")
```

# Generated Atoms

- note/7: track, position, channel, note, velocity, (length num, length denom), (distance num, distance denom)
- key/3: track, position, key

