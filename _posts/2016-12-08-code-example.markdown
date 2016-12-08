---
layout: post
title:  "Code Example"
date:   2016-12-08 16:40:46 +1300
categories: coding
sources: 
  - "snippet.cpp"
  - "htmlexample.html"
---

{% for fileid in page.sources %}
{% assign scripts = site.scripts | where: 'id', {{fileid}}%}
{% for file in scripts %}

<hr/>

id: {{ file.id }}

codetype: {{ file.codetype }}

path: {{ file.path }}

[Download: {{ file.id }}]({{ site.baseurl }}/_code_snippets/{{ file.id }})

```{{ file.codetype }}
{{ file.content }}
```

{% endfor %}
{% endfor %}
<hr/>