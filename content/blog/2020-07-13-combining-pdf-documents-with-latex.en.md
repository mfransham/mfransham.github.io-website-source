---
title: Combining pdf documents with LaTeX
author: Mark Fransham
date: '2020-07-13'
slug: combining-pdf-documents-with-latex
categories: []
tags:
  - LaTeX
subtitle: ''
summary: 'How to extract pages from pdf documents and combine them in LaTeX'
authors: []
lastmod: '2020-07-13T20:02:42+01:00'
featured: no
image:
  caption: ''
  focal_point: ''
  preview_only: no
projects: []
---

I often find myself needing to select individual pages from a pdf I haven't created, or combine pdfs from many single pdf documents.  With LaTeX this is super straightforward - here's the basic code structure to perform this task.  This code assumes that the `.tex` file is in the same folder as the documents you are combining.  

{{% alert note %}}
This code requires a working installation of LaTeX on your machine, such as [MiKTeX](https://miktex.org/download)
{{% /alert %}}

{{< gist mfransham ace96ab50b84805ce7c02113f8a7b23b>}}