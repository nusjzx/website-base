{% from "common/admin.njk" import topics with context %}
{% from "common/macros.njk" import  show_stars_in_nav with context %}


<navigation>

* [See all in one page (slow!)](index-flat.html)

{% for topic in topics %} 
{% set decoration = "==" if topic.highlight else "" %} 
{% set title = decoration + topic.title + decoration %} 
{% if topic.level == 1%} 
* [{{ title }}]({{ topic.link }}) {{ show_stars_in_nav(topic.priority) }}
{% elif topic.level == 2 %}
* [%%→%% <small>{{ title }}]({{ topic.link }})</small> {{ show_stars_in_nav(topic.priority) }}
{% elif topic.level == 0 %}
* %%{{ title }}%%
{% endif %}
{% endfor %}

</navigation>