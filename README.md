# Music Player

A visually appealing and functional music player built with HTML, CSS, and JavaScript. This project demonstrates the use of modern web technologies to create a responsive and interactive music player interface.

## Features

- **Responsive Design**: Adjusts to different screen sizes for optimal user experience.
- **Animated Background**: Beautiful gradient background animation.
- **Audio Controls**: Play, pause, forward, and backward controls.
- **Progress Bar**: Displays and updates the current time of the song.
- **Icon Integration**: Uses FontAwesome icons for controls and navigation.

## Installation

1. Clone the repository:
    ```sh
    git clone https://github.com/your_username/music-player.git
    ```
2. Navigate to the project directory:
    ```sh
    cd music-player
    ```
3. Open `index.html` in your favorite web browser:
    ```sh
    open index.html
    ```

## Usage

### HTML Structure

The HTML structure includes a container with the music player, navigation controls, song information, audio element, progress bar, and control buttons.

### CSS Styling

The CSS file `style.css` includes styles for the layout, responsiveness, and animations. It uses media queries to adjust the layout for different screen sizes.

### JavaScript Functionality

The JavaScript code controls the audio playback, updates the progress bar, and manages the play/pause functionality.

```js
let progress = document.getElementById("progress");
let song = document.getElementById("song");
let ctrlIcon = document.getElementById("ctrlIcon");

song.onloadedmetadata = function () {
  progress.max = song.duration;
  progress.value = song.currentTime;
};

function playPause() {
  if (ctrlIcon.classList.contains("fa-pause")) {
    song.pause();
    ctrlIcon.classList.remove("fa-pause");
    ctrlIcon.classList.add("fa-play");
  } else {
    song.play();
    ctrlIcon.classList.add("fa-pause");
    ctrlIcon.classList.remove("fa-play");
  }
}

if (song.play()) {
  setInterval(() => {
    progress.value = song.currentTime;
  }, 500);
}

progress.onchange = function () {
  song.play();
  song.currentTime = progress.value;
  ctrlIcon.classList.add("fa-pause");
  ctrlIcon.classList.remove("fa-play");
};
```
## Customization

### Change Song

Replace the `source` element inside the `audio` tag with your own song file:
```html
<audio id="song">
  <source src="path_to_your_song.mp3" type="audio/mpeg" />
</audio>
```
### Change Song Image
Replace the src attribute of the img tag with your own image file:
```html
<img src="path_to_your_image.png" class="song-img" />
```
### Update Icons
This project uses FontAwesome for icons. You can replace the icons with any other icons from the FontAwesome library by changing the class attribute of the i tags.
```html
<div class="circle">
  <i class="fa-solid fa-caret-left"></i>
</div>
<div class="circle">
  <i class="fa-solid fa-ellipsis-vertical"></i>
</div>
<div class="controls">
  <div>
    <i class="fa-solid fa-backward-step"></i>
  </div>
  <div onclick="playPause()">
    <i class="fa-solid fa-play" id="ctrlIcon"></i>
  </div>
  <div>
    <i class="fa-solid fa-forward-step"></i>
  </div>
</div>
```

### Contributing
Contributions are welcome! Please feel free to submit a pull request or open an issue if you have any suggestions or improvements.

### Acknowledgements
**FontAwesome & Boxicons**
