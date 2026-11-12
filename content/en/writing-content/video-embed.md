---
title: Video Embeds
description: Embed a video already hosted on YouTube, Vimeo, or Loom.
---

Use a video embed when the video is already hosted somewhere else. For a short, silent demo loop you host yourself, use a [clip](/writing-content/clip) instead.

Mordoc supports native video embed player for Youtube, Vimeo and Loom. 

## Add a video embed

```markdown {% process=false %}
{% videoEmbed 
  src="https://www.youtube.com/watch?v=AF8d72mA41M" 
  title="Why it was almost impossible to make the blue LED" 
/%}
```

**How it renders**

{% videoEmbed 
  src="https://www.youtube.com/watch?v=AF8d72mA41M" 
  title="Why it was almost impossible to make the blue LED" 
/%}


## Unrecognized hosts

If `src` isn't one of the providers above, Mordoc doesn't try to render a broken embed. It shows a link-out card instead, using `thumbnail` if you set one:

```markdown {% process=false %}
{% videoEmbed src="https://example.com/watch/123" thumbnail="/images/demo-thumb.jpg" title="Demo video" /%}
```

`thumbnail` is ignored for a recognized provider — YouTube, Vimeo, and Loom already show their own real thumbnail the moment the embed loads.

## Video embed attributes

{% table %}
* Attribute
* Description
* Values
* Required
---
* `src`
* The video's public page URL
* URL
* Required
---
* `title`
* A caption shown below the embed
* Any text
* Optional
---
* `alt`
* Overrides the accessible label. Otherwise the provider name, or `title`, is used
* Any text
* Optional
---
* `thumbnail`
* Used only on the fallback link-out card, for an unrecognized host `src`
* Image path
* Optional
---
* `aspectRatio`
* Overrides the default 16:9 box
* CSS ratio, e.g. `"4 / 3"`, `"9 / 16"`
* Optional
{% /table %}

## Next step

- [Highlight messages with callouts](/writing-content/callouts).
