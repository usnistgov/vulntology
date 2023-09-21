---
title: "Live Editor"
menu:
  primary:
    name: Editor
    weight: 60
sidenav:
  display: false
---

# Vulntology Live Editor

The following tool supports editing Vulntology-based vulnerability information. This tool is currently experimental and we would appreciate your [feedback](/contribute/#contact-us) on its usability and function.

<base href="."/>
<link id="app-theme" rel="stylesheet" type="text/css" href="saga-blue.css" media="print" onload="this.media='all'"><noscript><link rel="stylesheet" href="saga-blue.css"></noscript>
<style>.surface-ground{background-color:var(--surface-ground)!important}</style>
<link rel="stylesheet" href="styles.css" media="print" onload="this.media='all'"><noscript><link rel="stylesheet" href="styles.css"></noscript>

<div class="surface-ground">
  <app-root></app-root>
  <script src="runtime.js" type="module"></script>
  <script src="polyfills.js" type="module"></script>
  <script src="main.js" type="module"></script>
</div>
