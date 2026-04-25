# Instructions to Merge birthday_v2 (2).html with birthday_surprises (1).html

## Step 1: Add Navigation Button to birthday_v2 (2).html

Find the last page (Page 5 - Music page) in birthday_v2 (2).html and add this button after the music tracks section:

```html
<div style="text-align:center; margin-top: clamp(20px,4vw,32px);">
  <button class="btn-main" onclick="goToSurprises()">See Rest of the Surprise 🎁</button>
</div>
```

## Step 2: Add JavaScript Function in birthday_v2 (2).html

Add this JavaScript function before the closing `</script>` tag:

```javascript
function goToSurprises() {
  // Get the currently playing song
  const currentAudio = document.querySelector('audio');
  let songSrc = '';
  
  if (currentAudio && !currentAudio.paused) {
    songSrc = currentAudio.src;
  } else {
    // If no song is playing, use the first song as default
    const firstTrack = document.querySelector('.music-track-card');
    if (firstTrack) {
      const audioSrc = firstTrack.getAttribute('data-audio');
      songSrc = audioSrc || '';
    }
  }
  
  // Navigate to birthday_surprises with song parameter
  window.location.href = `birthday_surprises (1).html?song=${encodeURIComponent(songSrc)}`;
}
```

## Step 3: Add Background Music Player to birthday_surprises (1).html

Add this code right after the opening `<body>` tag in birthday_surprises (1).html:

```html
<!-- Background Music Player -->
<audio id="bgMusic" loop style="display:none;"></audio>
```

## Step 4: Add JavaScript to birthday_surprises (1).html

Add this script before the closing `</body>` tag:

```javascript
<script>
// Get song from URL parameter and play it
window.addEventListener('DOMContentLoaded', function() {
  const urlParams = new URLSearchParams(window.location.search);
  const songSrc = urlParams.get('song');
  
  if (songSrc) {
    const bgMusic = document.getElementById('bgMusic');
    bgMusic.src = decodeURIComponent(songSrc);
    bgMusic.volume = 0.3; // Set volume to 30%
    
    // Try to play (may require user interaction)
    bgMusic.play().catch(function(error) {
      console.log('Autoplay prevented. Music will play after user interaction.');
      
      // Add click listener to start music on first interaction
      document.body.addEventListener('click', function playOnce() {
        bgMusic.play();
        document.body.removeEventListener('click', playOnce);
      }, { once: true });
    });
  }
});
</script>
```

## Summary

These changes will:
1. Add a "See Rest of the Surprise" button on the music page
2. Pass the currently playing song (or first song if none playing) to the next page
3. Play that song as background music throughout birthday_surprises (1).html
4. Handle autoplay restrictions by playing on first user click if needed

The transition will be smooth and the music will continue playing in the background!
