---
Title: "{{title | escape}}"
Year: {{date | format("YYYY")}}
Authors: {{authors}}
Tags: [{% for t in tags %}{{t.tag}}{% if not loop.last %}, {% endif %}{% endfor %}]
Created: {{dateCreated | format("YYYY-MM-DD")}}
Zotero PDF Link: {{pdfZoteroLink}}
Citekey: {{citekey}}
Type: Literature Review
Field: Computer Graphics
---


## 🧠 Concepts & Keywords
- {{title | lower}}
- {% for t in tags %}{{t.tag}}{% if not loop.last %}, {% endif %}{% endfor %}
- Add any domain-specific terms (e.g., BRDFs, FFT, wave spectra, compute shaders, GPU instancing).

## 📄 Summary
{% persist "summary" %}
Write a brief overview of the paper here — what problem does it tackle, why is it important, and what results or contributions does it offer?
{% endpersist %}

## 🧩 Key Contributions
- List the main innovations, algorithms, or models introduced.
- Mention any mathematical models, procedural systems, rendering techniques, or simulation approaches.

## ⚙️ Technical Overview
| Aspect | Details |
|:-------|:---------|
| **Algorithm / Model** | |
| **Pipeline / Architecture** | |
| **Mathematical Basis** | |
| **Implementation Notes** | |
| **Datasets / Inputs** | |
| **Results / Outputs** | |

## 📈 Comparisons & Improvements
- How does this paper differ from or improve upon previous work?
- Mention related algorithms, frameworks, or notable comparisons .

## 🧠 Personal Insights
{% persist "insights" %}
Reflect on what you learned. How might this connect to your own projects or ideas (e.g., fluid simulation, procedural generation, BRG rendering)?
{% endpersist %}

## 🧩 In-text Annotations
{% for annotation in annotations -%}
{%- if annotation.annotatedText -%}
{% if annotation.color %} <mark class="hltr-{{annotation.colorCategory | lower}}">"{{annotation.annotatedText | safe}}"</mark> {% else %} {{annotation.type | capitalize}} {% endif %}[Page {{annotation.pageLabel}}](zotero://open-pdf/library/items/{{annotation.attachment.itemKey}}?page={{annotation.pageLabel}}&annotation={{annotation.id}})
{%- endif %}
{% if annotation.comment %}
> 💬 {{annotation.comment | safe}}  
[Page {{annotation.pageLabel}}](zotero://open-pdf/library/items/{{annotation.attachment.itemKey}}?page={{annotation.pageLabel}}&annotation={{annotation.id}})
{% endif %}
{%- if annotation.imageRelativePath %} 
![[{{annotation.imageRelativePath}}]]
{%- endif %}
{% if annotation.allTags %}
**Tags:** {{annotation.allTags}}
{% endif %}
---
{% endfor -%}

## 🧭 Related Work
Related:: {% for relation in relations | selectattr("citekey") %} [[{{relation.citekey}}]]{% if not loop.last %}, {% endif%} {% endfor %}


## 🖼️ Figures & Visual Notes
Add relevant screenshots or sketches you took:
![[your-figure.png]]
![[another-figure.png]]

## 📅 Review Metadata
- **Date Reviewed:** {{date | format("YYYY-MM-DD")}}
- **Read Status:** 📘 To Read / ✅ Read / 🧩 Reviewed
- **Relevance:** ⭐⭐⭐⭐☆ (adjust as needed)
- **Linked Project:** [[YourProjectName]]
