# Surrogate Model results

<div style="text-align: center;">
  <img id="slideshow_surrogate_model" src="img/surrogate_model//animation.0000.png" alt="Animation Frame" style="max-width: 90%; border: 2px solid #fff;"/>

  <div class="controls" style="margin-top: 10px;">
    <button onclick="togglePlaySurrogateResults()">▶️ Play / ⏸ Pause</button>
    <button onclick="resetSurrogateResults()">🔄 Reset</button>
  </div>
</div>

<script>
  let frame = 0;
  const totalFrames = 2048;
  const img = document.getElementById("slideshow_surrogate_model");
  let playing = true;
  const fps = 2;
  let interval = null;

  function pad(num, size) {
    return String(num).padStart(size, '0');
  }

  function updateFrameSurrogateReuslts() {
    const padded = pad(frame, 4);
    img.src = `img/surrogate_model/animation.${padded}.png`;
    frame = (frame + 1) % totalFrames;
  }

  function startSurrogateResults() {
    interval = setInterval(updateFrame, 1000 / fps);
  }

  function stopSurrogateResults() {
    clearInterval(interval);
  }

  function togglePlaySurrogateResults() {
    playing = !playing;
    if (playing) startSurrogateResults();
    else stopSurrogateResults();
  }

  function resetSurrogateResults() {
    frame = 0;
    img.src = `img/surrogate_model/animation.0000.png`;
  }

  startSurrogateResults();
</script>

# Iverse Model results

<div style="text-align: center;">
  <img id="slideshow_inverse_model" src="img/inverse_model/animation.0000.png" alt="Animation Frame" style="max-width: 90%; border: 2px solid #fff;"/>

  <div class="controls" style="margin-top: 10px;">
    <button onclick="togglePlayInverseResults()">▶️ Play / ⏸ Pause</button>
    <button onclick="resetInverseResults()">🔄 Reset</button>
  </div>
</div>

<script>
  let frame = 0;
  const totalFrames = 2048;
  const img = document.getElementById("slideshow_inverse_model");
  let playing = true;
  const fps = 2;
  let interval = null;

  function pad(num, size) {
    return String(num).padStart(size, '0');
  }

  function updateFrameInverseReuslts() {
    const padded = pad(frame, 4);
    img.src = `img/inverse_model/animation.${padded}.png`;
    frame = (frame + 1) % totalFrames;
  }

  function startInverseResults() {
    interval = setInterval(updateFrame, 1000 / fps);
  }

  function stopInverseResults() {
    clearInterval(interval);
  }

  function togglePlayInverseResults() {
    playing = !playing;
    if (playing) startInverseResults();
    else stopInverseResults();
  }

  function resetInverseResults() {
    frame = 0;
    img.src = `img/inverse_model/animation.0000.png`;
  }

  startInverseResults();
</script>

# Real case optimization results
