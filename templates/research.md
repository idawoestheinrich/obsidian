---
Title: "{{title | escape}}" 
Year: {{date | format("YYYY")}} 
Authors: {{authors}} 
Tags: {% if allTags %}{{allTags}}{% endif %} 
---
Zotero PDF Link: {{pdfZoteroLink}} 

{% for relation in relations | selectattr("citekey") %} [[{{relation.citekey}}]]{% if not loop.last %}, {% endif%} {% endfor %} 
### In-text annotations
{% for annotation in annotations -%} 
  {%- if annotation.annotatedText -%}
    {%- if annotation.colorCategory == "Purple" -%}
###### {{annotation.annotatedText | safe}} [Page {{annotation.pageLabel}}](zotero://open-pdf/library/items/{{annotation.attachment.itemKey}}?page={{annotation.pageLabel}}&annotation={{annotation.id}})
    {%- elif annotation.colorCategory == "Yellow" -%}
- {{annotation.annotatedText | safe}} [Page {{annotation.pageLabel}}](zotero://open-pdf/library/items/{{annotation.attachment.itemKey}}?page={{annotation.pageLabel}}&annotation={{annotation.id}})
    {%- else -%}
<mark class="hltr-{{annotation.colorCategory | lower}}">{{annotation.annotatedText | safe}}</mark> [Page {{annotation.pageLabel}}](zotero://open-pdf/library/items/{{annotation.attachment.itemKey}}?page={{annotation.pageLabel}}&annotation={{annotation.id}})
    {%- endif -%}
  {%- endif %}

  {%- if annotation.comment -%}
    *{{annotation.comment | safe}}* [Page {{annotation.pageLabel}}](zotero://open-pdf/library/items/{{annotation.attachment.itemKey}}?page={{annotation.pageLabel}}&annotation={{annotation.id}})
  {%- endif %}

  {%- if annotation.imageRelativePath -%}
    ![[{{annotation.imageRelativePath}}]] 
  {%- endif %}

  {%- if annotation.allTags -%}
    {{annotation.allTags}}
  {%- endif %}
{% endfor -%}

