<frontmatter>
title: "Admin (All admin info in one page!)"
footer: footer.md
siteNav: adminSiteNav-flat.md
</frontmatter>

<link rel="stylesheet" href="../css/main.css">
<link rel="stylesheet" href="../css/admin.css">

<div class="website-content">

<include src="../common/header.md" />

{% from "common/admin.njk" import topics with context %}


{% macro show_hr()%} 
<hr style="border-width: 3px; background-color: #f3ccff">
{% endmacro %}


{% macro show_thin_hr()%} 
<hr style="border-width: 1px; border-color: #f3ccff; border-style: dotted">
{% endmacro %}


{% for topic in topics %} 
{% if topic.level in [1,2] %} 
{% if (not loop.first) and (topic.level == 1)%} 
{{ show_hr() }}
{% elif (not loop.first) and (topic.level == 2)%}
{{ show_thin_hr() }}
{% endif %}
<div id="admin-{{ topic.id }}-anchor"></div>
<div id="admin-{{ topic.id }}">
  <include src="{{ topic.id }}.md#main" />
</div>
<br>
{% elif topic.level == 0 %}
{{ show_hr() }}

# {{ topic.title }}
{% endif %}
{% endfor %}

</div>
