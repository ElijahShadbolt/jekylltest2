{% if include.block %}
```{{ include.codetype }}
{{ include.content }}
```
{:.codeblock}
{% else %}
`{{ include.content }}`{:.language-{{ include.codetype }}}
{% endif %}