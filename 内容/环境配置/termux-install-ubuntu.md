---
layout: default
title: install ubuntu in termux
date: 2024-01-09
---

## <center>install ubuntu in termux</center>

<center>
<pre class="mermaid">
mindmap
termux
    proot-distro
    ubuntu
</pre>
</center>

```bash
pkg update
pkg install proot-distro
proot-distro install ubuntu
proot-distro login ubuntu --user root --shared-tmp
```

## refference

- [ivonblog: termux-proot-dixtro-ubuntu](https://ivonblog.com/en-us/posts/termux-proot-distro-ubuntu)

<script type="module">
	import mermaid from 'https://cdn.jsdelivr.net/npm/mermaid@10/dist/mermaid.esm.min.mjs';
	mermaid.initialize({ startOnLoad: true });
</script>

