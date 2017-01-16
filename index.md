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
#background-video {
  visibility: hidden;
}
.go {
  margin: 0;
  position: absolute;
  bottom: 20px;
  text-align: center;
  left: 0;
  right: 0;
}
.go a {
  text-decoration: none;
}
.go a:hover {
  text-decoration: underline;
}
.print {
  display: none;
}
</style>

<section>
  <h1 class="print">Pink Bananas Vlog</h1>
  <p class="print">Just a little different</p>
  <div class="wrapper">
    <div class="overlay"></div>
    <div class="letters"></div>
    <iframe id="background-video" src="https://www.youtube.com/embed/McABStdJWYA?rel=0&version=3&autoplay=0&controls=0&showinfo=0&loop=1&cc_load_policy=0&disablekb=1&enablejsapi=1&iv_load_policy=3&modestbranding=1" frameborder="0" allowfullscreen></iframe>
  </div>

  <p class="go"><a href="https://www.youtube.com/channel/UCtkiLTzGm8h0Xc2FqmDz8iw">Go to Pink Bananas' YouTube channel</a></p>
</section>

<section>
  <h1>Just a little different</h1>
  <p>With Pink Bananas I will take you on my journey around this world. While travaling I vlog about the cultures I encounter, do something crazy once in a while and show you my world. I want to create an entertaining piece of content but not limited to that. I can be confronting but I will be authentic.</p>
</section>

<script>
var tag = document.createElement('script');
tag.src = "https://www.youtube.com/iframe_api";
var firstScriptTag = document.getElementsByTagName('script')[0];
firstScriptTag.parentNode.insertBefore(tag, firstScriptTag);

var player;

function onYouTubeIframeAPIReady() {
  player = new YT.Player('background-video', {
    events: {
      onReady: function() {
        player.playVideo();
        player.mute();
      },
      onStateChange: function(state) {
        if (state.data === 1) {
          document.getElementById('background-video').style.visibility = 'visible';
        }
      }
    }
  });
}
</script>
