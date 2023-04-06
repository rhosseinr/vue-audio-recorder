# vue-audio-recorder

> New version of audio recorder for Vue.js with vite.
> It allows to record, play, download and store records on a server. It is based on vue-audio-recorder which is not longer being supported by the original author (grishkovelli).

#### [Live demo](https://jsfiddle.net/grishkovelli/rb1anxyj/)

#### Default mode

![](https://raw.githubusercontent.com/rhosseinr/vue-audio-recorder/master/screenshot.png)

#### Minimal mode

![](https://raw.githubusercontent.com/rhosseinr/vue-audio-recorder/master/minimal.png)

### Features

- Beautiful clean UI
- Download/upload/play record
- Time limit
- Records limit
- A lot of callbacks
- Individual an audio player
- MP3/WAV support

### Tested in (desktop)

- Edge
- Chrome
- Firefox
- Safari

## Installation

```
npm i vuejs2-audio-recorder --save
```

## AudioRecorder props

| Prop                 | Type     | Description                                                                                                    |
| -------------------- | -------- | -------------------------------------------------------------------------------------------------------------- |
| attempts             | Number   | Number of recording attempts                                                                                   |
| headers              | Object   | HTTP headers                                                                                                   |
| time                 | Number   | Time limit for the record (minutes)                                                                            |
| bit-rate             | Number   | Default: 128 (only for MP3)                                                                                    |
| sample-rate          | Number   | Default: 44100                                                                                                 |
| filename             | String   | Download/Upload filename                                                                                       |
| format               | String   | WAV/MP3. Default: mp3                                                                                          |
| upload-url           | String   | URL for uploading                                                                                              |
| show-download-button | Boolean  | If it is true show a download button. Default: true                                                            |
| show-upload-button   | Boolean  | If it is true show an upload button. Default: true                                                             |
| before-upload        | Function | Callback fires before uploading                                                                                |
| successful-upload    | Function | Callback fires after successful uploading                                                                      |
| failed-upload        | Function | Callback fires after failure uploading                                                                         |
| mic-failed           | Function | Callback fires if your microphone doesn't work                                                                 |
| before-recording     | Function | Callback fires after click the record button                                                                   |
| pause-recording      | Function | Callback fires after pause recording                                                                           |
| after-recording      | Function | Callback fires after click the stop button or exceeding the time limit                                         |
| select-record        | Function | Callback fires after choise a record. Returns the record                                                       |
| mode                 | String   | **[New]** A minimal interface to record just one audio and play it. Options: default/minimal. Default: default |
| countdown            | Boolean  | **[New]** Will show the time remaining instead of current recorded time. Options: true/false. Default: false   |
| countdownTitle       | String   | **[New]** Title over time remaining when countdown is set to true. Default: "Time remaining"                   |

## AudioPlayer props

| Prop | Type   | Description                         |
| ---- | ------ | ----------------------------------- |
| src  | String | Specifies the URL of the audio file |

## Usage

```js
import RecorderWidget from "vuejs2-audio-recorder";
import PlayerWidget from "vuejs2-audio-recorder";
```

```html
<recorder-widget
  upload-url="YOUR_API_URL"
  :attempts="3"
  :time="2"
  :headers="headers"
  :before-recording="callback"
  :pause-recording="callback"
  :after-recording="callback"
  :select-record="callback"
  :before-upload="callback"
  :successful-upload="callback"
  :failed-upload="callback"
  compact
/>
```

```html
<player-widget src="/demo/example.mp3" />
```

## Build Setup

```bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification (must be built with node v12.x)
npm run build
```

## TODO

- Clear record list
- Responsive design

## PUBLISH TO NPM

```
npm publish --access public
```

## Authors

[Gennady Grishkovtsov](https://www.linkedin.com/in/grishkovtsov/) - Developer
[Olga Zimina](https://www.behance.net/zimin4ik) - UIX Designer

## Contributors

[Jonathan Arias](https://github.com/jonalxh) - Developer
[Rhosseinr](https://github.com/rhosseinr) - Developer
