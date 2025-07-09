# Heating Process Optimization

# Surrogate Model results

<div style="text-align: center;">
  <img id="slideshow" src="img/surrogate_model/animation.0.png" alt="Animation Frame" style="max-width: 90%; border: 2px solid #fff;"/>
  
  <div class="controls" style="margin-top: 10px;">
    <button onclick="togglePlay()">▶️ Play / ⏸ Pause</button>
    <button onclick="reset()">🔄 Reset</button>
  </div>
</div>

<script>
  let frame = 0;
  const totalFrames = 2048;
  const img = document.getElementById("slideshow");
  let playing = true;
  let fps = 30;  // Adjust speed
  let interval = null;

  function updateFrame() {
    img.src = `img/surrogate_model/animation.${frame}.png`;
    frame = (frame + 1) % totalFrames;
  }

  function start() {
    interval = setInterval(updateFrame, 1000 / fps);
  }

  function stop() {
    clearInterval(interval);
  }

  function togglePlay() {
    playing = !playing;
    if (playing) start();
    else stop();
  }

  function reset() {
    frame = 0;
    img.src = `img/surrogate_model/animation.0.png`;
  }

  // Start the animation on page load
  start();
</script>

# Iverse Model results

# Real case optimization results
