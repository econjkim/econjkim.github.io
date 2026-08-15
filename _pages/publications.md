---
layout: page
permalink: /research/
title: Research
description:
nav: true
nav_order: 1
---

<!-- Sections are driven by the `status` field in _bibliography/papers.bib:
     jmp | pub | wp | wip.  A heading is shown only when at least one entry
     carries that status, so "Job Market Paper" appears automatically once
     an entry is tagged status={jmp}. -->

<div class="publications">

{% capture n_jmp %}{% bibliography_count --query @*[status=jmp] %}{% endcapture %}
{% capture n_pub %}{% bibliography_count --query @*[status=pub] %}{% endcapture %}
{% capture n_wp  %}{% bibliography_count --query @*[status=wp]  %}{% endcapture %}
{% capture n_wip %}{% bibliography_count --query @*[status=wip] %}{% endcapture %}

{% if n_jmp != "0" %}
<h2 class="bibliography">Job Market Paper</h2>
{% bibliography --query @*[status=jmp] %}
{% endif %}

{% if n_pub != "0" %}
<h2 class="bibliography">Publications</h2>
{% bibliography --query @*[status=pub] %}
{% endif %}

{% if n_wp != "0" %}
<h2 class="bibliography">Working Papers</h2>
{% bibliography --query @*[status=wp] %}
{% endif %}

{% if n_wip != "0" %}
<h2 class="bibliography">Work in Progress</h2>
{% bibliography --query @*[status=wip] %}
{% endif %}

</div>
