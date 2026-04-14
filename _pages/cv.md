---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

<div class="cv-pdf-wrapper">
  <div class="cv-pdf-actions">
    <a href="{{ '/files/resume.pdf' | relative_url }}" target="_blank" class="btn btn--primary">Open in new tab</a>
    <a href="{{ '/files/resume.pdf' | relative_url }}" download class="btn">Download PDF</a>
  </div>

  <iframe
    src="{{ '/files/resume.pdf' | relative_url }}"
    class="cv-pdf-frame"
    title="Ameya Phadnis — Resume">
    <p>Your browser does not support embedded PDFs.
      <a href="{{ '/files/resume.pdf' | relative_url }}">Download the PDF</a> to view it.
    </p>
  </iframe>
</div>
