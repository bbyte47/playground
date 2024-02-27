---
title: 'Gemini API Introduction'
date: 2024-02-26T11:18:59-05:00
draft: false
categories:
  - AI LLM's
tags:
  - Content
  - Gemini
description: 'First use of Gemini API'
post: 'gemini_api'
---

## Unlock the Power of Google's Gemini Generative AI API

Back in January Jose Portilla, a Udemy instructor, offered a free course titled "Master Gemini AI - Google Bard Prompt Engineering Bootcamp" which I jumped on. Jose Portilla teaches classes primarily on or with Python and first took several of his finance classes. This class was introduced right around the time Bard was changed to Gemini. Then this month Jose introduced another free course "Google Gemini AI with Python - Quick Start".

In this course he uses Jupyter Notebook to place the code and created a text prompt, chat, and vision application where he uses a pitcure of a fridge and then asks Gemini to create a recipe for a meal based on the picture. Also stumbled on a YouTube video called "Gemini API Is Here ..." by the handle Unconventional Coding. Here is one of the scripts from that video:

---

import google.generativeai as genai
import os

genai.configure(api_key=os.getenv('GEMINI_API_KEY')

model = genai.GenerativeModel('gemini-pro')

response = model.generate_content("Hello")

print(response.text)

---

Here is the video on YouTube
{{< youtube id="f6ZmtKvPni4" autoplay="true" >}}

With Google's docs and what I picked up from Jose and Unconventional Coding was able to start using the API. I still have a lot to work through. With that said, my initial experience has been pleasant with my next steps turning it into a Tinker app. Happy coding...
