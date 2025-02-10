---
# Leave the homepage title empty to use the site title
title: ""
date: 2022-10-24
type: landing

design:
  # Default section spacing
  spacing: "6rem"

sections:
  - block: resume-biography-3
    id: about
    content:
      # Choose a user profile to display (a folder name within `content/authors/`)
      username: admin
      text: ""
      # Show a call-to-action button under your biography? (optional)
      button:
        text: download CV
        url: uploads/resume.pdf
  - block: resume-experience
    id: experience
    content:
      title: Experience
      username: admin
    design:
      # Hugo date format
      date_format: 'January 2006'
      # Education or Experience section first?
      is_education_first: false
  - block: collection
    id: papers
    content:
      title: Publications
      text: ""
      count: 100
      sort_by: weight
      order: asc # asc | desc
      filters:
        folders:
          - publication
        exclude_featured: true
    design:
      view: citation # article-grid/card/citation/date-title-summary
  - block: resume-awards
    id: awards
    content:
      title: Awards
      username: admin
  - block: collection
    id: projects
    content:
      title: Projects
      text: I enjoy making things. Here are a selection of projects that I have worked on over the years.
      filters:
        folders:
          - project
    design:
      view: article-grid
      fill_image: false
      columns: 3
---


