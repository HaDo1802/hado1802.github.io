---
title: "Passion & Impact"
layout: default
---

<style>
  .journal-hero {
    margin: 2.5rem auto 1.5rem;
    max-width: 920px;
    text-align: center;
  }

  .journal-hero h1 {
    font-size: 2.6rem;
    margin: 0 0 0.75rem;
    color: var(--text);
  }

  .journal-hero p {
    font-size: 1.2rem;
    color: var(--muted);
    margin: 0 auto;
    max-width: 700px;
    line-height: 1.7;
  }

  .journal-meta {
    display: inline-flex;
    align-items: center;
    gap: 0.75rem;
    margin-top: 1rem;
    padding: 0.4rem 1rem;
    border-radius: 999px;
    border: 1px solid var(--border);
    background: var(--panel);
    box-shadow: var(--shadow-soft);
    font-size: 0.9rem;
    color: var(--muted);
  }

  .journal-content {
    max-width: 900px;
    margin: 0 auto;
    padding: 1.5rem 1rem 3rem;
    font-size: 1.1rem;
    line-height: 1.9;
    color: var(--text);
  }

  .journal-content p {
    margin-bottom: 1.6rem;
    color: var(--muted);
  }

  .journal-lede {
    font-size: 1.2rem;
    color: var(--text);
  }

  .journal-figure {
    margin: 2.2rem 0;
    border-radius: 16px;
    overflow: hidden;
    background: var(--panel);
    border: 1px solid var(--border);
    box-shadow: var(--shadow);
  }

  .journal-figure img {
    width: 100%;
    height: 360px;
    object-fit: cover;
    display: block;
  }

  .journal-caption {
    padding: 0.9rem 1.1rem;
    border-top: 1px solid var(--border);
    font-size: 0.95rem;
    color: var(--muted);
  }

  .journal-caption strong {
    color: var(--text);
  }

  .journal-gallery {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
    gap: 1.2rem;
    margin: 2rem 0;
  }

  .journal-gallery figure {
    margin: 0;
    background: var(--panel);
    border-radius: 14px;
    overflow: hidden;
    border: 1px solid var(--border);
    box-shadow: var(--shadow-soft);
  }

  .journal-gallery img {
    width: 100%;
    height: 220px;
    object-fit: cover;
    display: block;
  }

  .journal-quote {
    border-left: 4px solid var(--accent);
    padding-left: 1.2rem;
    margin: 2rem 0;
    font-style: italic;
    color: var(--text);
  }

  .journal-footer {
    display: flex;
    flex-wrap: wrap;
    gap: 1rem;
    align-items: center;
    justify-content: space-between;
    margin-top: 2.5rem;
    padding: 1.25rem 1.5rem;
    background: var(--panel);
    border: 1px solid var(--border);
    border-radius: 16px;
    box-shadow: var(--shadow-soft);
  }

  @media (max-width: 720px) {
    .journal-hero h1 {
      font-size: 2rem;
    }

    .journal-figure img {
      height: 240px;
    }
  }
</style>

{% assign journal_pdf = '/South Africa Journal.pdf' | relative_url | uri_escape %}

<section class="journal-hero">
  <h1>Finding Purpose in the Wild: My Journey with Rhinos in South Africa</h1>
  <p>Ten days in South Africa changed the way I see nature—and myself.</p>
  <div class="journal-meta">
    <span>Amakhala Game Reserve</span>
    <span>•</span>
    <span>South Africa</span>
  </div>
</section>

<article class="journal-content">
  <p class="journal-lede">
    At Amakhala Game Reserve, I experienced wildlife not as a distant observer, but as someone deeply connected to the land, the animals, and the people protecting them. From my first sunrise game drive to standing beside a rhino during a conservation procedure, every moment reminded me how fragile—and powerful—nature truly is.
  </p>

  <figure class="journal-figure">
    <img src="{{ '/assets/images/passion/IMG_6037.jpeg' | relative_url }}" alt="Rhino conservation moment in South Africa" data-lightbox-src="{{ '/assets/images/passion/IMG_6037.jpeg' | relative_url }}">
    <figcaption class="journal-caption"><strong>Edit caption:</strong> Short, concise description of this image.</figcaption>
  </figure>

  <p>
    Seeing rhinos in the wild was especially emotional for me. Vietnam lost its last wild rhino in 2010 due to poaching, and for years I believed I would never witness one alive in its natural habitat. Touching a rhino’s thick skin, watching conservationists treat them like family, and learning how tracking collars and dehorning protect them from poachers transformed my understanding of conservation. These animals are not statistics—they are lives worth fighting for.
  </p>

  <p>
    Beyond the wildlife, the journey taught me something even deeper. Conservation is not just about animals; it’s about people. From community dog-vaccination programs to supporting local schools, I saw how education, collaboration, and compassion form the foundation of sustainable ecosystems. Protecting wildlife requires trust between humans and nature.
  </p>

  <blockquote class="journal-quote">
    Nature doesn’t need us—but we need nature. And it’s our responsibility to protect it.
  </blockquote>

  <p>
    This trip helped me slow down, reconnect with my values, and rediscover joy outside of career pressure and daily stress. It reminded me that passion matters—and that technology, education, and awareness can be powerful tools for conservation.
  </p>

  <p>
    I carry South Africa with me now: in the sound of birds at sunrise, in the memory of a rhino walking free, and in a renewed commitment to protect the natural world. This journey didn’t just deepen my love for nature—it gave me purpose.
  </p>

  <div class="journal-gallery">
    <figure>
      <img src="{{ '/assets/images/passion/IMG_5880.jpeg' | relative_url }}" alt="Wildlife conservation scene" data-lightbox-src="{{ '/assets/images/passion/IMG_5880.jpeg' | relative_url }}">
      <figcaption class="journal-caption"><strong>Edit caption:</strong> Short, concise description of this image.</figcaption>
    </figure>
    <figure>
      <img src="{{ '/assets/images/passion/IMG_5958.jpeg' | relative_url }}" alt="South African landscape" data-lightbox-src="{{ '/assets/images/passion/IMG_5958.jpeg' | relative_url }}">
      <figcaption class="journal-caption"><strong>Edit caption:</strong> Short, concise description of this image.</figcaption>
    </figure>
    <figure>
      <img src="{{ '/assets/images/passion/IMG_6092.jpg' | relative_url }}" alt="Rhino conservation details" data-lightbox-src="{{ '/assets/images/passion/IMG_6092.jpg' | relative_url }}">
      <figcaption class="journal-caption"><strong>Edit caption:</strong> Short, concise description of this image.</figcaption>
    </figure>
  </div>

  <div class="journal-footer">
    <span>🦏🌍</span>
    <a class="btn" href="{{ journal_pdf }}" target="_blank" rel="noopener">Read the Full Journal (PDF)</a>
  </div>
</article>
