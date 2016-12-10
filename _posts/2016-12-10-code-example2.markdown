---
layout: post
title:  "Code Example (markdown post)"
date:   2016-12-08 16:40:46 +1300
categories: coding
sources: 
  - "snippet.cpp"
  - "htmlexample.html"
  - "stylesheet.css"
  - "markdownexample.markdown"
---
This is a paragraph full of random things and snippets of code like {% include codeblock.md content='public void Destroy() { }' codetype='csharp' %} and {% include codeblock.md content='int *p = new int(4);' codetype='cpp' %}.

{% for scriptname in page.sources %}
{% assign scripts = site.scripts | where: 'scriptname', {{scriptname}}%}
{% for script in scripts %}

---

[Download: {{ script.scriptname }}]({{ site.baseurl }}/{{ script.relative_path }}){:download="{{ script.scriptname }}"}

{% include codeblock.md block=true codetype=script.codetype content=script.content %}

{% endfor %}
{% endfor %}