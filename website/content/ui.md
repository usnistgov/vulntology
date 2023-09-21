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

<script>
  document.write(`<base href="${location.pathname}${location.pathname.endsWith('/') ? '' : '/'}"/>`);
</script>
<link id="app-theme" rel="stylesheet" type="text/css" href="/editor/saga-blue.css" media="print" onload="this.media='all'"><noscript><link rel="stylesheet" href="/editor/saga-blue.css"></noscript>
<style>.surface-ground{background-color:var(--surface-ground)!important}</style>
<link rel="stylesheet" href="/editor/styles.css" media="print" onload="this.media='all'"><noscript><link rel="stylesheet" href="/editor/styles.css"></noscript>

<div class="surface-ground">
<app-root></app-root>
<script src="/editor/runtime.js" type="module"></script>
<script src="/editor/polyfills.js" type="module"></script>
<script src="/editor/main.js" type="module"></script>
</div>
