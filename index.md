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
          <span><strong>Venue:</strong> {{ site.event.venue }}</span>
          <span><strong>Location:</strong> {{ site.event.location_short }}</span>
        </div>

        <div class="hero__actions">
          <a class="btn" href="{{ site.event.registration_url }}" target="_blank" rel="noopener">Register</a>
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
      <p class="section__sub">This table is generated from <code>_data/program.yml</code>. Update that file as the agenda is finalized.</p>
    </div>
    {% include program_table.html %}
  </div>
</section>

<section id="speakers" class="section">
  <div class="container">
    <div class="section__head">
      <h2>Targeted speakers</h2>
      <p class="section__sub">Speaker cards are generated from <code>_data/speakers.yml</code>. Add more speakers any time.</p>
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
      <p class="section__sub">The symposium takes place at the historic monastery in Disentis, Switzerland — an ideal setting for focused exchange and community building.</p>
    </div>

    <div class="grid">
      <div class="panel panel--half">
        <h3>Location</h3>
        <p><strong>{{ site.event.venue }}</strong></p>
        <p class="muted">{{ site.event.location_short }}</p>

        <h3 style="margin-top:18px;">Travel & accommodation</h3>
        <p class="muted">Placeholder: add travel tips, nearest train station, directions, and accommodation notes here.</p>
      </div>

      <div class="panel panel--half">
        <h3>At a glance</h3>
        <ul>
          <li>Welcome apéro and dinners included (details TBA)</li>
          <li>Poster sessions and networking activities</li>
          <li>Student-led workshops on Day 4 (morning)</li>
        </ul>
        <p class="muted">Placeholder: add accessibility information and venue facilities here.</p>
      </div>
    </div>
  </div>
</section>

<section id="sponsors" class="section">
  <div class="container">
    <div class="section__head">
      <h2>Sponsors</h2>
      <p class="section__sub">We’re grateful for partners who support enterovirus research, training, and European collaboration. Add logos in <code>_data/sponsors.yml</code>.</p>
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
              <div class="sponsor">{{ s.name }}</div>
            {% endif %}
          {% endfor %}
        </div>
      </div>
    {% endfor %}
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
        <p class="muted">{{ site.event.organizer }}</p>
        <p><strong>Email:</strong> <a href="mailto:{{ site.event.contact_email }}">{{ site.event.contact_email }}</a></p>
        <p class="muted">Placeholder: add organizer names, roles, and acknowledgements here.</p>
      </div>

      <div class="panel panel--half">
        <h3>Registration</h3>
        <p class="muted">Registration will open via an external system.</p>
        <p><a class="btn btn--ghost" href="{{ site.event.registration_url }}" target="_blank" rel="noopener">Go to registration</a></p>
        <p class="muted">Tip: set <code>event.registration_url</code> in <code>_config.yml</code> once you have the link.</p>
      </div>
    </div>
  </div>
</section>
