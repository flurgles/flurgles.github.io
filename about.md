---
layout: default
title: About
permalink: /about/
---
<div class="page">
  <h1>About This Site</h1>

  <p>
    This site tracks development updates for the
    <a href="https://github.com/flurgles/dock6">dock6</a> molecular docking
    software — specifically work happening on my development branch.
  </p>

  <h2>What is dock6?</h2>
  <p>
    <a href="https://dock.compbio.ucsf.edu/DOCK_6/">DOCK 6</a> is a molecular
    docking program developed by the <a href="https://bkslab.org/">Kuntz Lab /
    Shoichet Lab / Irwin Lab</a> at UCSF. It is used for structure-based drug
    discovery, predicting how small molecules bind to protein targets.
  </p>

  <h2>What's being tracked here?</h2>
  <p>
    My development branch includes work on:
  </p>
  <ul>
    <li><strong>GPU acceleration</strong> — Metal-based GPU kernels for scoring, simplex minimization, and flexible docking</li>
    <li><strong>Clustering</strong> — WL graph symmetry detection, Hungarian algorithm RMSD, new cluster RMSD modes</li>
    <li><strong>Performance</strong> — Internal energy optimizations, tiled gather kernels, batch evaluation</li>
    <li><strong>Infrastructure</strong> — Apple Silicon build templates (clang/clang.gpu), CI cleanup</li>
  </ul>

  <h2>Source</h2>
  <p>
    The code is on GitHub at
    <a href="https://github.com/flurgles/dock6">github.com/flurgles/dock6</a>.
    Pull requests are welcome.
  </p>
</div>
