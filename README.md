<p align="center">
  <h1 align="center">soundboard</h1>
</p>

## Features
`soundboard` is a simple keyboard driven soundboard that:

* Can be used with any key on your keyboard
* Can have a limitless number of bindings
* Can repeat audio clips with a single key press
* Can play most standard audio file formats
* Is easily configured through a JSON file
* Should work on any operating system

## Why

* I see a lot of streamers playing audio clips during their streams but most of them are on Windows, and can make use of things like an Elgato Stream Deck. Being a Linux user this isn't an option for me so this seemed like the simplest solution.

## Dependencies

* [pynput](https://github.com/moses-palmer/pynput) for keyboard input
* [pydub](https://github.com/jiaaro/pydub) for generic audio playback

## Configuration

### Example Configuration
```json
{
  "bindings": [
    {
      "key": "f11",
      "sound": "/home/brodie/music/sound-clips/ouchie.wav",
      "name": "Ouchie",
      "repeat": 1,
      "start": 0,
      "end": 100
    },
    { "key": "f12", "sound": "/home/brodie/music/sound-clips/idiot.wav" }
  ],
  "help": '`'
}
```

### Bindings

Each binding requires the properties `key` and `sound` all others are optional.

* `key` defines the key to press to play the accompanying sound, any key on the keyboard should be accepted, see Special Keys for names of non-alphanumeric or symbol keys
* `sound` is a path to a sound (mp3, wav, etc.)
* `name` **OPTIONAL** shown in place of the sound path on the help display
* `repeat` **OPTIONAL** how many times the sound should be repeated (Defaults to 1)
* `start` **OPTIONAL** how many milliseconds into the sound file should it play from (Default to 0)
* `end` **OPTIONAL**  how many milliseconds into the sound file should it stop playing at (Default to the end of the clip)

### Help

Defines the key used to print out the list of sound effects and accompanying keys

#### Example Output

```bash
f11: Ouchie: /home/brodie/music/sound-clips/ouchie.wav
f12: None: /home/brodie/music/sound-clips/idiot.wav
```

## Special Keys

Following is a list of the key names used for any special keyboard keys, if any are missing that's because I don't have them on my keyboard and would appreciate a PR.

* f1
* f2
* f3
* f4
* f5
* f6
* f7
* f8
* f9
* f10
* f11
* f12
* esc
* tab
* caps_lock
* shift
* ctrl
* cmd
* alt
* backspace
* enter
* shift_r
* ctrl_r
* menu
* alt_r
* print_screen
* scroll_lock
* pause
* insert
* home
* page_up
* page_down
* delete
* end
* num_lock
* up
* left
* right
* down

## Issues

* Pydub doesn't run ffplay in silent mode **Issue has existed for a while**
* Key combination are not supported
