+++
title = "Django templates: Accessing dict keys with colons"
date = 2016-07-27T08:37:00Z
draft = false
tags = ["python", "django", "programming"]
+++

Earlier this week I was updating a dashboard which uses Django templates. The
data included a Python dictionary with a key that contains a colon: `data:foo`.

Normally the dictionary item is accessed using dotted notation such as
`{{ mydict.foo }}` but using a colon results in a syntax error.

```
Exception Type: TemplateSyntaxError
Exception Value: Could not parse the remainder: ':foo' from 'mydict.data:foo'
```

The simple fix is to change the key but I don't own this object and it cannot
be easily changed. I devised a simple "fix" after a little browsing and
experimentation: use a for loop.

```
{% for k, v in mydict.items %}
{% if k == "data:foo" %}
  {{ v }}
{% endif %}
{% endfor %}
```

It's not elegant but it's the best I could devise without creating a new
Template Tag or filter.
