---
title: Home
layout: default
---

<div class="hero">
  <img
  class="avatar"
  src="{{ '/assets/img/profile-400.jpg' | relative_url }}"
  srcset="{{ '/assets/img/profile-400.jpg' | relative_url }} 400w,
          {{ '/assets/img/profile-800.jpg' | relative_url }} 800w"
  sizes="(min-width: 900px) 200px, 160px"
  alt="Ali Hasnain Khowaja"
  loading="eager" decoding="async" fetchpriority="high"
/>

  <div>
    <h1>Ali Hasnain Khowaja</h1>
    <div class="subtitle">Aerospace Engineer • Guidance, Navigation & Control</div>
    <div class="contacts">
      <a href="tel:+17702356937"><i class="fa-solid fa-phone"></i> 770-235-6937</a>
      <a href="mailto:alikhowaja17@gmail.com"><i class="fa-solid fa-envelope"></i> alikhowaja17@gmail.com</a>
      <a href="https://linkedin.com/in/alikhowaja/"><i class="fa-brands fa-linkedin"></i> linkedin.com/in/alikhowaja/</a>
    </div>
  </div>
</div>

<div class="section">
  <h2>About Me</h2>
  <p>I’m an aerospace engineer focused on guidance, navigation, and control for autonomous systems. I’m a SMART scholar on contract with NAVAIR after graduation. In my free time I cook, play sports, and make music.</p>
</div>

<div class="section">
  <h2>Highlights</h2>
  <div class="grid cards">
    <div class="card">
      <h3>Engineering & Mathematics Primer</h3>
      <p>Short, LaTeX-ready notes with embedded mini-lectures.</p>
      <p><a href="{{ '/primer/' | relative_url }}">Browse the Primer →</a></p>
    </div>
    <div class="card">
      <h3>Projects</h3>
      <p>Research, lab work, and personal builds—one page per project with links and media.</p>
      <p><a href="{{ '/projects/' | relative_url }}">See Projects →</a></p>
    </div>
  </div>
</div>
