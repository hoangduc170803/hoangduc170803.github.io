---
layout: about
title: about
permalink: /
subtitle: Data Engineer at <a href='https://viettel.com.vn/'>Viettel Telecom</a>. BSc Information Technology, FPT University.

profile:
  align: right
  image: prof_pic.jpg
  image_circular: false # crops the image to make it circular
  more_info: >
    <p>Hanoi, Vietnam</p>

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
  .selected-projects .proj { margin-bottom: 1.1rem; }
  .selected-projects .tag {
    display: inline-block; border: 1px solid var(--global-theme-color);
    color: var(--global-theme-color); border-radius: 4px;
    font-size: 0.72rem; line-height: 1.5; padding: 0 0.45rem; white-space: nowrap;
  }
  .selected-projects .when { display: block; font-size: 0.78rem; color: var(--global-text-color-light); margin-top: 0.25rem; }
  .selected-projects .ptitle { font-weight: 500; }
  .selected-projects .pmeta { font-size: 0.9rem; color: var(--global-text-color-light); }
  .selected-projects .plinks a {
    font-size: 0.78rem; border: 1px solid var(--global-divider-color);
    border-radius: 3px; padding: 0 0.4rem; margin-right: 0.3rem;
  }
</style>

<h2><a href="{{ '/projects/' | relative_url }}" style="color: inherit;">selected projects</a>
  <a href="{{ '/projects/' | relative_url }}" style="font-size: 0.85rem; font-weight: 400;">[full list]</a>
</h2>

<div class="selected-projects">
  {% assign ordered = site.projects | sort: "importance" %}
  {% for p in ordered limit: 3 %}
  <div class="proj row">
    <div class="col-sm-2 abbr">
      <span class="tag">{{ p.tag | default: "project" }}</span>
      <span class="when">{{ p.period }}</span>
    </div>
    <div class="col-sm-10">
      <div class="ptitle">{{ p.headline | default: p.title }}</div>
      <div class="pmeta">{{ p.description }}</div>
      <div class="pmeta">{{ p.stack }}</div>
      <div class="plinks"><a href="{{ p.url | relative_url }}">Details</a></div>
    </div>
  </div>
  {% endfor %}
</div>
