{% import "common/macros.njk" as macros with context %}
{% from "common/admin.njk" import topics, policies, faqs with context %}

{% set admin_sections = [
  {topic_id: "project-w09-v12"}
]%}

{{ macros.show_admin_sections_to_read(topics, policies, faqs, admin_sections) }}