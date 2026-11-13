---
title: Home
layout: landing
---

{% hero
  title="One docs framework"
  titleAccent="to rule them all."
  description="Mordoc turns your Markdown into clean, elegant documentation websites. Write content, configure once, and ship anywhere."
  background="/images/hero-images/mordoc-hero.png"
%}
{% button path="/introduction" %}Get started{% /button %}
{% /hero %}

{% section title="Everything you need" %}
{% cardGrid cols="3" %}
{% card title="Getting Started" path="/getting-started/create-project" icon="/icons/card-icons/getting-started.svg" %}
Create your first project, run it locally, and learn how Mordoc works from the ground up.
{% /card %}
{% card title="Writing Content" path="/writing-content/markdown-basics" icon="/icons/card-icons/writing.svg" %}
Markdown basics, callouts, tables, cards, landing pages, and everything in between.
{% /card %}
{% card title="Configuration" path="/configuration/site-configuration" icon="/icons/card-icons/configuration.svg" %}
Tailor your site with navigation, branding, themes, variables, and multi-language support.
{% /card %}
{% /cardGrid %}
{% /section %}

{% section title="When you're ready to ship" %}
{% cardGrid cols="2" %}
{% card title="Build and Deploy" path="/publishing/build-your-site" icon="/icons/card-icons/deploy.svg" %}
Generate a static site and deploy it to any hosting platform in minutes.
{% /card %}
{% card title="Preview Before Publishing" path="/publishing/preview-before-publishing" icon="/icons/card-icons/preview.svg" %}
See exactly how your site looks before it goes live — no surprises.
{% /card %}
{% /cardGrid %}
{% /section %}
