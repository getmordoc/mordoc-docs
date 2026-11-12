---
title: Clips
description: Add short, self-hosted demo clips with a click-to-play toggle.
---

A clip is a short, muted, looping demo video. Mordoc recommends this way to show a UI interaction instead of an animated GIF.

A GIF autoplays with no way to pause it, which is both distracting and an accessibility problem. A clip renders paused on its thumbnail and only plays once a reader clicks it, so it stays under the reader's control.

## Add a clip

```markdown {% process=false %}
{% clip 
  src="/clips/animated-dinosaur.mp4" 
  title="Animated Dinosaur" 
  alt="Animated Dinosaur" 
/%}
```

**How it renders**

{% clip 
  src="/clips/animated-dinosaur.mp4" 
  title="Animated Dinosaur" 
  alt="Animated Dinosaur"
/%}


Put the video file in `public/`, then reference its path the same way you would an image. See [Images and Files](/getting-started/images-and-files) if you haven't added an asset before.

## Clip attributes

{% table %}
* Attribute
* Description
* Values
* Required
---
* `src`
* The video file itself
* Video path
* Required
---
* `thumbnail`
* Shown paused before the reader clicks play
* Image path
* Optional
---
* `title`
* A caption shown below the clip
* Any text
* Optional
---
* `alt`
* Accessible label for the play/pause toggle button
* Any text
* Optional
{% /table %}

## Keep clips short and silent

Clips are for short, decorative demo loops, not a narrated walkthrough. Mordoc always mutes them.

For a longer audible video, use a [video embed](/writing-content/video-embed) instead, linking out to a video already hosted on YouTube, Vimeo, or Loom rather than a file you host yourself.

## Next step

- [Embed a hosted video](/writing-content/video-embed).
