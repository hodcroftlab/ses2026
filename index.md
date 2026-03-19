---
layout: default
title: "Home"
---

{% include banner.html %}

<section class="hero">
  <div class="container">
    <div class="hero__card">
      <div class="hero__img" style="background-image:url('{{ site.design.hero_image | relative_url }}');"></div>
      <div class="hero__content">
        <div class="kicker">In-person · 60–80 participants · Early-career friendly</div>
        <h1>{{ site.event.name }}</h1>
        <p>{{ site.tagline }}</p>
        <div class="hero__meta">
          <span><strong>Dates:</strong> {{ site.event.dates }}</span>
          <span>
            <strong>Venue:</strong>
            {% if site.event.venue_url %}
              <a href="{{ site.event.venue_url }}" target="_blank" rel="noopener">
                {{ site.event.venue }}
              </a>
            {% else %}
              {{ site.event.venue }}
            {% endif %}
          </span>
          <span><strong>Location:</strong> {{ site.event.location_short }}</span>
        </div>

        <div class="hero__actions">
          {% if site.event.registration_open %}
            <a class="btn" href="{{ site.event.registration_url }}" target="_blank" rel="noopener">Register</a>
          {% endif %}
          <a class="btn btn--ghost" href="#program">View program</a>
          <a class="btn btn--ghost" href="#speakers">Speakers</a>
          <a class="btn btn--ghost" href="#contact">Contact</a>
        </div>
      </div>
    </div>
  </div>
</section>

<section id="about" class="section">
  <div class="container">
    <div class="section__head">
      <h2>About</h2>
      <p class="section__sub">A focused meeting uniting virology, epidemiology, bioinformatics, and clinical science to drive progress in enterovirus research and surveillance.</p>
    </div>

    <div class="grid">
      <div class="panel panel--half">
        <h3>Why this symposium?</h3>
        <p>
          Enteroviruses are an increasingly important yet underrepresented global health challenge, with evolving genotypes
          (including EV-A71 and EV-D68) linked to rising disease burden. This symposium creates a platform to spotlight
          cutting-edge science, new detection technologies, and clinical insights.
        </p>
      </div>

      <div class="panel panel--half">
        <h3>Format</h3>
        <ul>
          <li>Keynotes, contributed talks, and poster sessions</li>
          <li>Interactive workshops (Nextstrain, Nextclade, Pathoplexus)</li>
          <li>Structured discussion forum + networking</li>
          <li><strong>In-person only</strong> to maximize collaboration</li>
        </ul>
      </div>
    </div>
  </div>
</section>

<section id="program" class="section">
  <div class="container">
    <div class="section__head">
      <h2>Program overview</h2>
      <p class="section__sub">Our program aims to combine world-class plenaries, submitted talks, and interactive poster and discussion sessions, finalized by a skill-building workshop.</p>
    </div>
    {% include program_table.html %}
  </div>
</section>

<section id="speakers" class="section">
  <div class="container">
    <div class="section__head">
      <h2>Confirmed speakers</h2>
      <p class="section__sub"><i>Stay tuned as we confirm more speakers!</i></p>
    </div>

    <div class="grid">
      {% for speaker in site.data.speakers %}
        <div class="panel panel--third" style="padding:0; border:none; box-shadow:none; background:transparent;">
          {% include speaker_card.html speaker=speaker %}
        </div>
      {% endfor %}
    </div>
  </div>
</section>

<section id="venue" class="section">
  <div class="container">
    <div class="section__head">
      <h2>Venue</h2>
      <p class="section__sub">The symposium will take place at a former monastery in Disentis, offering a beautiful setting for discussions and informal exchange.</p>
    </div>

    <div class="grid">
      <div class="panel panel--half">
        <h3>Location</h3>
        <p><strong>
          {% if site.event.venue_url %}
            <a href="{{ site.event.venue_url }}" target="_blank" rel="noopener">
              {{ site.event.venue_name }}
            </a>
          {% else %}
            {{ site.event.venue_name }}
          {% endif %}
        </strong></p>
        <p class="muted">{{ site.event.location_short }}</p>
        <p class="muted">{{ site.event.venue_description }}</p>

        <h3 style="margin-top:18px;">Travel & arrival</h3>
        <p class="muted">Disentis is accessible by public transport with scenic rail connections through the Alps:</p>
        <ul class="muted">
              <li><strong>By train:</strong> Disentis/Mustér station has regular connections via Chur or Andermatt. ~10 min walk uphill</li>
            <ul>
              <li><strong>From Zurich:</strong> ~2.5 hours with one change in Chur</li>
              <li><strong>From Basel:</strong> ~3.5 hours with one change in Chur</li>
            </ul>
              <li><strong>By car:</strong> Via Chur or Oberalp Pass; parking available on site</li>
              </ul>
        <p class="muted"><em>Train travel is recommended for convenience and sustainability.</em></p>

        {% include venue_map.html %}
      </div>

      <div class="panel panel--half">
        <h3>Accommodation & costs</h3>
        <p class="muted">Most participants will stay at Hotel Kloster Disentis, so meals, talks, and poster sessions all take place in the same location.</p>
        <ul class="muted">
          <li>Single, double, and triple rooms available</li>
          <li>Breakfast included</li>
          <li>Simple, comfortable rooms in the monastery setting</li>
          <li>A small number may be housed nearby (1–2 min walk away)</li>
        </ul>
        <p class="muted">
          <strong>Registration covers accommodation, meals, materials, and workshops.</strong>
          Travel to Disentis is not included. We offer a limited number of travel grants for students with limited funds. Details will be announced when registration opens.
        </p>

        <h3 style="margin-top:18px;">At a Glance</h3>
        <ul class="muted">
          <li>Welcome reception and all meals included</li>
          <li>Keynote lectures and talks selected from abstracts</li>
          <li>Poster sessions and networking opportunities</li>
          <li>Interactive workshop on Day 4 (Nextstrain, Nextclade or Pathoplexus, TBD)</li>
        </ul>

        <h3 style="margin-top:18px;">Accessibility</h3>
        <p class="muted">Most main conference areas are accessible. As a historic building, some areas may involve stairs or uneven floors. Please <a href="mailto:{{ site.event.contact_email }}">reach out in advance</a> if you have specific requirements so we can help coordinate.</p>
      </div>
    </div>
  </div>
</section>

<section id="sponsors" class="section">
  <div class="container">
    <div class="section__head">
      <h2>Sponsors</h2>
      <p class="section__sub">We thank our partners for supporting enterovirus research and collaboration.</p>
    </div>

    {% for tier in site.data.sponsors.tiers %}
      <div class="panel" style="margin-bottom:18px;">
        <h3 style="margin-top:0;">{{ tier.name }}</h3>
        <div class="sponsor-grid">
          {% for s in tier.sponsors %}
            {% if s.logo %}
              <a class="sponsor" href="{{ s.url | default: '#' }}" {% if s.url %}target="_blank" rel="noopener"{% endif %} style="border-style:solid; background:#fff;">
                <img src="{{ s.logo | relative_url }}" alt="{{ s.name }} logo" style="max-width:100%; max-height:52px;">
              </a>
            {% else %}
              <a class="sponsor" href="mailto:eve-group@swisstph.ch" style="border-style:solid;">{{ s.name }}</a>
            {% endif %}
          {% endfor %}
        </div>
      </div>
    {% endfor %}
  </div>
</section>

<section id="contact" class="section">
  <div class="container">
    <div class="section__head">
      <h2>Contact</h2>
      <p class="section__sub">Questions? Get in touch with the organizing committee.</p>
    </div>

    <div class="grid">

      <div class="panel panel--half">
        <h3>Organizers</h3>
        <div style="display:flex; flex-wrap:wrap; gap:16px; margin-bottom:16px;">
          {% assign organizers = "Prof Emma Hodcroft,emma-hodcroft|Ms Nadia Neuner-Jehle,nadia-neuner-jehle|Ms Nosihle Msomi,nosihle-msomi|Mr Keno Strotjohann,keno-strotjohann" | split: "|" %}
          {% for org in organizers %}
            {% assign parts = org | split: "," %}
            <div style="display:flex; flex-direction:column; align-items:center; gap:6px; width:80px; text-align:center;">
              <img
                src="{{ '/assets/img/speakers/' | append: parts[1] | append: '.jpg' | relative_url }}"
                alt="{{ parts[0] }}"
                style="width:60px; height:60px; border-radius:50%; object-fit:cover; object-position:center;"
              >
              <span style="font-size:0.75rem; line-height:1.2;">{{ parts[0] }}</span>
            </div>
          {% endfor %}
        </div>
        <p class="muted">...and with help from the rest of the <a href="https://eve-lab.org" target="_blank" rel="noopener">EVE Lab</a>.</p>
        <p><strong>Email:</strong> <a href="mailto:{{ site.event.contact_email }}">{{ site.event.contact_email }}</a></p>
      </div>



      <div class="panel panel--half">
        <h3>Registration</h3>
        <p class="muted">Registration will happen via our partner.</p>
        {% if site.event.registration_open %}
          <p><a class="btn btn--ghost" href="{{ site.event.registration_url }}" target="_blank" rel="noopener">Go to registration</a></p>
        {% else %}
          <p class="muted"><em>Registration is not yet open - please stay tuned!</em></p>
        {% endif %}
        <!-- <p class="muted">Tip: set <code>event.registration_url</code> in <code>_config.yml</code> once you have the link.</p> -->
      </div>
    </div>
  </div>
</section>

