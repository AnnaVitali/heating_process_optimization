---
layout: default
---

## Surrogate Model results

The initial image corresponds to the prediction derived from the Surrogate Model, the subsequent image represents the ground-truth, and the final image illustrates the absolute error that has been obtained.

<div style="text-align: center;">
  <img id="slideshow_surrogate_model" src="img/surrogate_model//animation.0000.png" alt="Animation Frame" style="max-width: 90%; border: 2px solid #fff;"/>

  <div class="controls" style="margin-top: 10px;">
    <button onclick="togglePlaySurrogateResults()">▶️ Play / ⏸ Pause</button>
    <button onclick="resetSurrogateResults()">🔄 Reset</button>
  </div>
</div>

<script>
  const totalFrames = 2048;
  const fps = 2;
  const imgSurrogate = document.getElementById("slideshow_surrogate_model");
  let frameSurrogate = 0;
  let playingSurrogate = true;
  let intervalSurrogate = null;

  function pad(num, size) {
    return String(num).padStart(size, '0');
  }

  function updateFrameSurrogateResults() {
    const padded = pad(frameSurrogate, 4);
    imgSurrogate.src = `img/surrogate_model/animation.${padded}.png`;
    frameSurrogate = (frameSurrogate + 1) % totalFrames;
  }

  function startSurrogateResults() {
    intervalSurrogate = setInterval(updateFrameSurrogateResults, 1000 / fps);
  }

  function stopSurrogateResults() {
    clearInterval(intervalSurrogate);
  }

  function togglePlaySurrogateResults() {
    playingSurrogate = !playingSurrogate;
    if (playingSurrogate) startSurrogateResults();
    else stopSurrogateResults();
  }

  function resetSurrogateResults() {
    frame = 0;
    imgSurrogate.src = `img/surrogate_model/animation.0000.png`;
  }

  startSurrogateResults();
</script>

## Inverse Model results

The initial image illustrates the prediction derived from the Surrogate Model, the subsequent image depicts the prediction from the Inverse Model, and the final image shows the absolute error that was obtained.


<div style="text-align: center;">
  <img id="slideshow_inverse_model" src="img/inverse_model/animation.0000.png" alt="Animation frameSurrogate" style="max-width: 90%; border: 2px solid #fff;"/>

  <div class="controls" style="margin-top: 10px;">
    <button onclick="togglePlayInverseResults()">▶️ Play / ⏸ Pause</button>
    <button onclick="resetInverseResults()">🔄 Reset</button>
  </div>
</div>

<script>
  let frameInverse = 0;
  const imgInverse = document.getElementById("slideshow_inverse_model");
  let playingInverse = true;
  let intervalnverse = null;

  function pad(num, size) {
    return String(num).padStart(size, '0');
  }

  function updateFrameInverseResults() {
    const padded = pad(frameInverse, 4);
    imgInverse.src = `img/inverse_model/animation.${padded}.png`;
    frameInverse = (frameInverse + 1) % totalFrames;
  }

  function startInverseResults() {
    intervalnverse = setInterval(updateFrameInverseResults, 1000 / fps);
  }

  function stopInverseResults() {
    clearInterval(intervalnverse);
  }

  function togglePlayInverseResults() {
    playingInverse = !playingInverse;
    if (playingInverse) startInverseResults();
    else stopInverseResults();
  }

  function resetInverseResults() {
    frameInverse = 0;
    imgInverse.src = `img/inverse_model/animation.0000.png`;
  }

  startInverseResults();
</script>

## Real case optimization results

The video presents the iteration results obtained by the optimiser for the real-use case of the lion that was tested.

<div style="text-align: center;">
  <video width="640" height="360" controls>
    <source src="video/ottimizzatore.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>
</div>
