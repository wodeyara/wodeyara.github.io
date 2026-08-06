<a href="https://www.youtube.com/watch?v=zITGvFeRvOA" target="_blank" rel="noopener noreferrer">A short demonstration</a> of the **state-space phase estimator** — a method for estimating the phase of a neural rhythm *in real time*, together with a credible interval that tells you how certain that estimate is. 

The key idea: model the oscillation as a damped harmonic oscillator driven by noise, and track it with a state-space model (a Kalman filter). Unlike filter-then-Hilbert approaches, this gives a principled estimate of phase *and* its uncertainty at the present moment — exactly what you need to drive real-time, phase-locked stimulation.

The full method is described in our eLife paper, listed in my [publications](../index.html#publications).

<!--
  The original version of this post embedded a short video demo.
  To add it back: drop the video file into this "posts" folder and embed it, e.g.:

  <video src="../posts/phase-demo.mp4" controls></video>

  (Markdown lets you drop in HTML like the line above.)
-->
