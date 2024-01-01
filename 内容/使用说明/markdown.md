---
layout: default
title: markdown说明
date: 2023-12-19
---

# <center>markdown说明</center>

## 介绍

markdown 是一种轻量级标记文本，方便记录编程经验。


## 基础语法

| 名称   | 格式   |
|--------|--------|
| 关键字 | `文本` |
| 加粗   | *文本* |
| 下划线 | _文本_ |
| 标题   | ##     |
| 分割线 | ---    |

## 在markdown中使用mermaid

在markdown尾部添加

```markdown
<script type="module">
	import mermaid from 'https://cdn.jsdelivr.net/npm/mermaid@10/dist/mermaid.esm.min.mjs';
	mermaid.initialize({ startOnLoad: true });
</script>

```

在文档中按如下格式启用mermaid

```markdown
<pre class="mermaid">
graph TD
A---->B
</pre>
```

效果图：


<pre class="mermaid">
graph TD
A---->B
</pre>


## 在markdown中使用katex

在文档尾部添加

```markdown
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/katex@0.15.6/dist/katex.min.css" integrity="sha384-ZPe7yZ91iWxYumsBEOn7ieg8q/o+qh/hQpSaPow8T6BwALcXSCS6C6fSRPIAnTQs" crossorigin="anonymous">
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.15.6/dist/katex.min.js" integrity="sha384-ljao5I1l+8KYFXG7LNEA7DyaFvuvSCmedUf6Y6JI7LJqiu8q5dEivP2nDdFH31V4" crossorigin="anonymous"></script>
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.15.6/dist/contrib/auto-render.min.js" integrity="sha384-+XBljXPPiv+OzfbB3cVmLHf4hdUFHlWNZN5spNQ7rmHTXpd7WvJum6fIACpNNfIR" crossorigin="anonymous"
    onload="renderMathInElement(document.body);"></script>
```

使用方式：

```markdown
方式一
\\(x^2\\)
方式二
$$x^2 + y^2 = z^2$$
```


效果图：

方式一：
\\(x^2\\)

方式二：
$$x^2 + y^2 = z^2$$


## 参考

- [Yet another guide for using Mermaid diagrams in GitHug pages](https://andykuszyk.github.io/2023-05-03-yet-another-mermaid-in-github-pages-guide.html)
- [Katex: Auto-render Extension](https://katex.org/docs/autorender.html)
- [How to support latex in Github-pages?](https://stackoverflow.com/questions/26275645/how-to-support-latex-in-github-pages#30389289)



<script type="module">
	import mermaid from 'https://cdn.jsdelivr.net/npm/mermaid@10/dist/mermaid.esm.min.mjs';
	mermaid.initialize({ startOnLoad: true });
</script>
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/katex@0.15.6/dist/katex.min.css" integrity="sha384-ZPe7yZ91iWxYumsBEOn7ieg8q/o+qh/hQpSaPow8T6BwALcXSCS6C6fSRPIAnTQs" crossorigin="anonymous">
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.15.6/dist/katex.min.js" integrity="sha384-ljao5I1l+8KYFXG7LNEA7DyaFvuvSCmedUf6Y6JI7LJqiu8q5dEivP2nDdFH31V4" crossorigin="anonymous"></script>
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.15.6/dist/contrib/auto-render.min.js" integrity="sha384-+XBljXPPiv+OzfbB3cVmLHf4hdUFHlWNZN5spNQ7rmHTXpd7WvJum6fIACpNNfIR" crossorigin="anonymous"
    onload="renderMathInElement(document.body);"></script>
