---
layout: about
title: about
permalink: /
subtitle: Data Engineer at <a href='https://viettel.com.vn/'>Viettel Telecom</a>. BSc Information Technology, FPT University.

profile:
  align: right
  image: prof_pic.jpg
  image_circular: false # crops the image to make it circular
  more_info: # the reference site keeps this empty; add lines here to show text under the photo

selected_papers: false # includes a list of papers marked as "selected={true}"
social: true # includes social icons at the bottom of the page

announcements:
  enabled: false # includes a list of news items
  scrollable: true # adds a vertical scroll bar if there are more than 3 news items
  limit: 5 # leave blank to include all the news in the `_news` folder

latest_posts:
  enabled: false
  scrollable: true # adds a vertical scroll bar if there are more than 3 new posts items
  limit: 3 # leave blank to include all the blog posts
---

I rebuilt the pipelines behind a company-wide fee settlement system at [Viettel Telecom](https://viettel.com.vn/). At Aubot, I took a multi-agent path finding planner from recent literature into production on a live AGV fleet.

Building a hybrid retrieval system over internal policy documents was where the two halves of my work met: the model was only as good as the pipeline feeding it. I want to keep working at that intersection: the data infrastructure that makes large models work, from the pipelines that train them to the systems that serve them.

Welcome to drop me an email if you want to discuss or collaborate.

<!-- Selected projects. Mirrors the "selected publications" block of the theme,
     but driven by the _projects collection instead of a bibliography. -->
<style>
  /* Hold the profile photo to the reference site's near-square 8:9 frame, whatever
     the source file's proportions are. object-fit crops rather than squashes, so a
     tall portrait is trimmed top and bottom instead of being distorted. */
  .profile img {
    width: 100%;
    aspect-ratio: 8 / 9;
    object-fit: cover;
    object-position: center top;
  }

  /* The profile photo is floated right. Without clearing it, a short bio lets this
     block ride up beside the photo and sit in the narrow column left over. */
  .selected-projects-wrap { clear: both; padding-top: 2rem; }

  /* Heading sized like the theme's own "selected publications" block. */
  .selected-projects-wrap h2 { font-size: 2rem; font-weight: 400; margin-bottom: 1.6rem; }

  .selected-projects .proj { margin-bottom: 2rem; }

  /* Solid badge, matching the venue badges on publication entries. */
  .selected-projects .tag {
    display: inline-block; background-color: var(--global-theme-color); color: #fff;
    border-radius: 4px; font-size: 0.75rem; font-weight: 500;
    line-height: 1.6; padding: 0.1rem 0.5rem; white-space: nowrap;
  }
  .selected-projects .when { display: block; font-size: 0.85rem; color: var(--global-text-color-light); margin-top: 0.4rem; }

  .selected-projects .ptitle { font-size: 1.05rem; line-height: 1.4; margin-bottom: 0.15rem; }
  .selected-projects .pmeta { font-size: 0.95rem; color: var(--global-text-color-light); line-height: 1.5; }
  .selected-projects .ptitle a { color: inherit; }
  .selected-projects .ptitle a:hover { color: var(--global-theme-color); }

  .selected-projects .plinks { margin-top: 0.7rem; }
  .selected-projects .plink { font-size: 0.85rem; line-height: 1.55; margin-bottom: 0.3rem; }
  .selected-projects .plink a { font-weight: 600; color: var(--global-theme-color); }
  .selected-projects .plink a:hover { text-decoration: underline; }
  .selected-projects .pldesc { color: var(--global-text-color-light); }

  .selected-projects .demo { margin-top: 0.9rem; }
  .selected-projects .demo video {
    display: block; width: 100%; height: auto;
    border: 1px solid var(--global-divider-color); border-radius: 4px;
  }
  .selected-projects .vcaption {
    font-size: 0.8rem; color: var(--global-text-color-light);
    margin: 0.5rem 0 0; line-height: 1.5;
  }
</style>

<div class="selected-projects-wrap">

<h2>selected projects</h2>

<div class="selected-projects">
  {% assign ordered = site.projects | sort: "importance" %}
  {% for p in ordered limit: 1 %}
  <div class="proj row">
    <div class="col-sm-2 abbr">
      <span class="tag">{{ p.tag | default: "project" }}</span>
      <span class="when">{{ p.period }}</span>
    </div>
    <div class="col-sm-10">
      <div class="ptitle"><a href="{{ p.url | relative_url }}">{{ p.headline | default: p.title }}</a></div>
      <div class="pmeta">{{ p.summary | default: p.description }}</div>
      <div class="pmeta">{{ p.stack }}</div>
      {% if p.links %}
      <div class="plinks">
        {% for l in p.links %}
        <div class="plink">
          <a href="{{ l.url }}" target="_blank" rel="noopener">{{ l.name }}</a>{% if l.desc %}<span class="pldesc"> - {{ l.desc }}</span>{% endif %}
        </div>
        {% endfor %}
      </div>
      {% endif %}
      {% if p.demo %}
      <div class="demo">
        <video autoplay loop muted playsinline poster="{{ p.demo_poster | relative_url }}">
          <source src="{{ p.demo | relative_url }}" type="video/mp4">
        </video>
        {% if p.demo_caption %}<p class="vcaption">{{ p.demo_caption }}</p>{% endif %}
      </div>
      {% endif %}
    </div>
  </div>
  {% endfor %}
</div>

</div>
