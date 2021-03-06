---
Title: Agenda
container: "container-fluid"
hide_sidebar: true
---

Agendas can be added to the site through an `agenda.yaml` data file added in a subfolder of the data folder for the target locale (for localization, for default, create/use the "en" folder). An example of this path is as follows, `data/en/agenda.yaml`. The data should be similar to the following format: 


```
complete: true
types:
    - name: Demo
      id: 1
      color: "#e44"
    - name: Keynote
      id: b2 
      color: "#a0a"

items:
    - name: Open-source software
      presenter: Ken K.
      type: 1
      vod: "#1"
    - name: How to 'how to'
      presenter: Jim Bob
      type: b2
      vod: "#2"
    - name: Industry Keynote
      presenter: Eclipse Foundation, .etc
      type: b2
      vod: "#3"
    - name: Best practices for Interneting your Things
      presenter: Adam A.
      type: b2
      vod: "#4"
```

Types represent the different types of sessions being held at the event. Normally creating the CSS for these types will be created automatically on render based on the `color` passed in the data file. If no color is set, no CSS would be generated for the type. Additionally, a new CSS rule may be added via custom code. This rule should resemble the following, replacing `<id>` with the `id` value set in the type and `<color>` with a hex color code:  

```
.eclipsefdn-agenda-legend-icon-<id>::after {
    background-color: <color>;
}
```

Items in these data files represent the actual sessions to be represented in the agenda.  

---

## Basic  

Targets ./data/en/agenda.yaml:  


{{< events/agenda >}}

---

## Sub-site version  

Targets ./data/en/2019/agenda.yaml:


{{< events/agenda event="sample">}}

---

## No session types  

Targets ./data/en/no_types/agenda.yaml:


{{< events/agenda event="no_types">}}

---

## Active agenda

Targets ./data/en/active/agenda.yaml:


{{< events/agenda event="active">}}

---

## Agenda w/ slides

Targets ./data/en/slides/agenda.yaml:


{{< events/agenda event="slides">}}

---

## Agenda w/ event+year

Targets ./data/en/2020/sample/agenda.yaml:


{{< events/agenda year="2020" event="sample">}}