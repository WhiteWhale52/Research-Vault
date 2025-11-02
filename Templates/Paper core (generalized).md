---
Title: "{{title | escape}}"
Authors: {{authors}}
Year: {{date | format("YYYY")}}
Area: {{field | default("General")}}
Tags: [{% for t in tags %}{{t.tag}}{% if not loop.last %}, {% endif %}{% endfor %}]
Citekey: {{citekey}}
DOI: {{doi}}
URL: {{url}}
Zotero PDF Link: {{pdfZoteroLink}}
Created: {{dateCreated | format("YYYY-MM-DD")}}
Reviewed: {{date | format("YYYY-MM-DD")}}
Read Status: {{readStatus | default("To Read")}}
---


## 📄 Brief Summary
{% persist "summary" %}
Write a short (2–5 sentence) high-level summary of the paper: problem, approach, and key result.
{% endpersist %}


## 🔑 Key Contributions
- Contribution 1 — what is new or useful
- Contribution 2
- Contribution 3


## ⚙️ Technical Overview
| Aspect | Short description |
|:------:|:------------------|
| Problem | |
| Approach / Method | |
| Core equations / model | |
| Inputs / Outputs | |
| Complexity / performance | |


## 🧪 Experiments & Results
- Benchmarks used
- Metrics
- Key findings and numbers


## ♻️ Limitations & Caveats
- Known limitations (authors' or your own)


## 🔗 Related Work
Related:: {% for relation in relations | selectattr("citekey") %} [[{{relation.citekey}}]]{% if not loop.last %}, {% endif %} {% endfor %}


## 🧠 Personal Insights / Ideas
{% persist "insights" %}
How could this be applied, improved, or used in your projects? Note implementation ideas and quick experiments to try.
{% endpersist %}


## 📅 Review Metadata
- Date reviewed: {{date | format("YYYY-MM-DD")}}
- Relevance: {{relevance | default("Medium")}}
- Linked project(s): [[YourProject]]


## 📁 Files & Attachments
- PDF: {{pdfZoteroLink}}
- Local assets: ![[assets/{{citekey}}-figure1.png]]