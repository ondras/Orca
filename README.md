# ORCΛ

<img src='https://raw.githubusercontent.com/hundredrabbits/Orca/master/resources/logo.png' width="600"/>

**Each letter of the alphabet is an operation**, lowercase letters typically operate on bang(`*`), uppercase letters operate on each frame. Bangs can be generated by various operations, such as `E` colliding with a `0`, see the [bang.orca](https://github.com/hundredrabbits/Orca/blob/master/examples/bang.orca) example. Watch a music video of [ORCΛ in action](https://twitter.com/neauoire/status/1064738259077554176).

## Install & Run

There are no public builds available at the moment. 

```
cd desktop
npm install
npm start
```

<img src='https://raw.githubusercontent.com/hundredrabbits/Orca/master/resources/preview.jpg' width="600"/>

## Functions

### alpha functions

- `A` **add**(a, b): Outputs the sum of inputs.
- `B` **banger**(val): Bangs if input is `1`, `N`, `S`, `W`, `Z` or `E`.
- `C` **clock**(min, max): Outputs a constant value based on the runtime frame.
- `D` **unknown**: --
- `E` **east**: Moves eastward, or bangs.
- `F` **if**(a, b): Outputs `1` if inputs are equal, otherwise `0`.
- `G` **generator**(val): Outputs a value on bang.
- `H` **halt**: Stops southward fn from operating.
- `I` **increment**(min, max): Increments southward fn.
- `J` **jump**(val): Outputs the northward fn.
- `K` **kill**: Kills southward fn.
- `L` **loop**('len): Loops a number of eastward fns.
- `M` **modulo**(val, mod): Outputs the modulo of inputs.
- `N` **north**: Moves Northward, or bangs.
- `O` **offset**('x, 'y, val): Reads a distant fn with offset.
- `P` **push**: Moves away on bang.
- `Q` **count**('len): Counts the number of fns present eastwardly.
- `R` **random**(min, max): Outputs a random value.
- `S` **south**: Moves southward, or bangs.
- `T` **track**('len, 'key, val): Outputs character at eastward position with offset.
- `U` **uturn**(n, e, s, w): Reverses movement on inputs.
- `V` **beam**: Bangs the nearest southward fn on bang.
- `W` **west**: Moves westward, or bangs.
- `X` **teleport**('x, 'y, val): Outputs value at offset.
- `Y` **type**(a, b): Compares the type(num/alpha/special) of inputs, and return `1` or `0`.
- `Z` **diagonal**: Moves diagonally.

### special functions

- `.` **null**: empty
- `*` **bang**: Bangs!
- `:` **midi**(channel, octave, note, velocity): Sends Midi a midi note.
- `;` **udp**('len): Sends a string via UDP to localhost.
- `#` **comment**: Comment a line.

## Output

### Midi Output

The midi special function is `:000`, it takes up to 4 inputs('channel, 'octave, 'note, velocity, length). For example, `:25C`, is a **C note, on the 5th octave, through the 3rd MIDI channel**, `:04c`, is a **C# note, on the 4th octave, through the 1st MIDI channel**. 

#### Velocity

Velocity is either from `0-9`(10 steps), or `A-Z`(26 steps). For example, `:34C8`, is a **C note, on the 4th octave, through the 4th MIDI channel with a velocity of 112/127(88%)**, `:34CT`, is a **C note, on the 4th octave, through the 4th MIDI channel with a velocity of 96/127(75%)**. 

#### Note Length

Note length is a value from `1-f`, which is a ratio of a full bar, *1* being `1/1`(a full bar), *2* being `1/2`(half), *3* being `1/3`(third).. and *f* being `1/16`. For example, `:27FZ4`, is a **F note, on the 7th octave, through the 3rd MIDI channel with a velocity of 100%, lasting for 1/4 of a bar**. 

To see it in action, see the [midi.orca](https://github.com/hundredrabbits/Orca/blob/master/examples/midi.orca) example.

### UDP Output

The [UDP](https://nodejs.org/api/dgram.html#dgram_socket_send_msg_offset_length_port_address_callback) special function is `3;MSG`, it has one haste input that gets a string length and locks the eastward ports. It sends the message on bang to the port `49160`. You can use the [listener.js](https://github.com/hundredrabbits/Orca/blob/master/listener.js) to test UDP messages.

To see it in action, see the [udp.orca](https://github.com/hundredrabbits/Orca/blob/master/examples/udp.orca) example.

<img src='https://raw.githubusercontent.com/hundredrabbits/Orca/master/resources/preview.hardware.jpg' width="600"/>

## TODOs

- Implement OSC `=`.
- Implement `D`.
- Implement nested files `/`.
- Implement note length.
- Show UDP bandwidth in UI.

## Extras

- This application supports the [Ecosystem Theme](https://github.com/hundredrabbits/Themes).
- Support this project through [Patreon](https://patreon.com/100).
- See the [License](LICENSE.md) file for license rights and limitations (MIT).
- Pull Requests are welcome!
