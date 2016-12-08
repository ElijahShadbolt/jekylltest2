---
layout: post
title:  "Code Example"
date:   2016-12-08 16:40:46 +1300
categories: coding
sources: 
  - "snippet.cpp"
  - "htmlexample.html"
---

{% for script in site.scripts %}
<hr/>

path: {{ script.path }}

scriptname: {{ script.scriptname }}

codetype: {{ script.codetype }}

```{{ script.codetype }}
{{ script.content }}
```
{% endfor %}

{% for scriptname in page.sources %}
{% assign scripts = site.scripts | where: 'scriptname', {{scriptname}}%}
{% for script in scripts %}

<hr/>

path: {{ script.path }}

scriptname: {{ script.scriptname }}

codetype: {{ script.codetype }}

[Download: {{ script.scriptname }}]({{ site.baseurl }}/_scripts/{{ script.scriptname }})

```{{ script.codetype }}
{{ script.content }}
```

{% endfor %}
{% endfor %}
<hr/>