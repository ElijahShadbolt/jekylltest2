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
This is a paragraph full of random things and snippets of code like `public void Destroy() { }`{:.language-csharp .highlight} and `int *p = new int(4);`{:.language-cpp .highlight}.

{% for scriptname in page.sources %}
{% assign scripts = site.scripts | where: 'scriptname', {{scriptname}}%}
{% for script in scripts %}
{::options parse_block_html="true" /}
<div>

---

[Download: {{ script.scriptname }}]({{ site.baseurl }}/{{ script.relative_path }}){:download="{{ script.scriptname }}"}
{% include codeblock.html codetype=script.codetype content=script.content %}

</div>
{% endfor %}
{% endfor %}

---