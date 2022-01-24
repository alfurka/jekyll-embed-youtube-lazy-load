# Lazy Loading YouTube Videos in Jekyll Posts

`ytdefer.min.js` is taken from https://github.com/groupboard/ytdefer. It is modified for Jekyll posts. 

## How to use?

1. Download the `ytdefer.min.js` file in this repository. 
2. Upload `ytdefer.min.js` to your Jekyll repository (server). JavaScripts files are usually contained `assets` folder.  
3. Create `youtube.html` as follows and save it in `_includes` folder. 

`youtube.html`:

```{html}
<script src="/assets/ytdefer.min.js"></script>

<div style="margin:auto;width:380px;height:250px;max-width:95%;" class="ytdefer" data-alt="Podcast Dinle" data-title="Podcast Dinle" data-src="{{ include.id }}"></div>

<script>
window.addEventListener('load', ytdefer_setup);
</script>
```

4. Add `{% include youtube.html id='YOUTUBE-VIDEO-ID' %}` into your posts where you want to embed the video. Example Jekyll post layout:

```
---
layout: post
title: "Example Post"
---
....
CONTENTS 
....

{% include youtube.html id='ZzeF6SducfQ' %}

....
CONTENTS 
....
```

## Remarks 
- Note that you need to change the first line if `ytdefer.min.js` is saved in a different path.
- You can change `div` style for embedding size/style.
