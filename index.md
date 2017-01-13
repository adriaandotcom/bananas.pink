<style>
.wrapper {
  position: relative;
}
.overlay {
  position: absolute;
  z-index: 1;
  width: 100%;
  height: 90%;
  transition: background-color;
  transition-duration: 500ms;
  background-color: rgba(255, 255, 255, 0.5);
}
.wrapper:hover .overlay {
  background-color: rgba(255, 255, 255, 0);
}
.letters {
  position: absolute;
  z-index: 2;
  width: 100%;
  height: 100%;
  background-image: url('/pink-overlay.png');
  background-size: cover;
  background-position: center;
}
iframe {
  width: 800px;
  height: 450px;
}
</style>

<div class="wrapper">
  <div class="overlay"></div>
  <div class="letters"></div>
  <iframe id="background-video" src="https://www.youtube.com/embed/JzwLky3TP2U?rel=0&version=3&autoplay=0&controls=0&showinfo=0&loop=1&cc_load_policy=0&disablekb=1&enablejsapi=1&iv_load_policy=3&modestbranding=1" frameborder="0" allowfullscreen></iframe>
</div>

<script>
var tag = document.createElement('script');
tag.src = "https://www.youtube.com/iframe_api";
var firstScriptTag = document.getElementsByTagName('script')[0];
firstScriptTag.parentNode.insertBefore(tag, firstScriptTag);

var player;

function onYouTubeIframeAPIReady() {
  player = new YT.Player('background-video', {
    events: {
      onReady: onPlayerReady,
      onStateChange: function() {
        console.log('arguments', arguments);
      }
    }
  });
}

function onPlayerReady() {
  player.playVideo();
  player.mute();
}
</script>
