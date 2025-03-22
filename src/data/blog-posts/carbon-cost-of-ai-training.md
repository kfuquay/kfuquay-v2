---
title: The Carbon Cost of AI Training
slug: carbon-cost-of-ai-training
description: Assessing the environmental impact of AI training.
publishDate: 14 Mar 2025
---

As someone who spent several years working in the conservation field before transitioning into software engineering, I’ve always been mindful of the environmental impact of technology. Recently, while checking out Hugging Face's NLP course, I was struck by the section on AI's carbon cost. It got me thinking about how the energy demands of training AI models could affect our planet in the long run.

Back in **2019**, a [study by **Strubell et al.**](https://arxiv.org/pdf/1906.02243) highlighted just how energy-hungry AI training could be. They estimated that training a single large transformer model could emit as much carbon as **five American cars over their lifetime**.

It’s been over five years since this paper sparked widespread discussion and concern. Let’s take a quick look at how the conversation around AI’s environmental footprint has evolved—what progress, if any, have we made in reducing energy consumption, and where are we headed now?

## How AI's Carbon Footprint is Evolving

### Energy Use is Soaring

AI’s hunger for computational power has only grown. More complex models, larger datasets, and expanding infrastructure all require vast amounts of energy. Google’s most recent environmental report revealed a **48% increase in emissions over five years**, primarily due to the rising demand for AI services and data center expansions. As cloud computing and AI become more integrated into everyday applications, maintaining sustainable energy practices is becoming a significant challenge.

[Google's 2024 Environmental Report](https://www.gstatic.com/gumdrop/sustainability/google-2024-environmental-report.pdf)

### New Approaches to Training

Some AI researchers and companies are working on more efficient training methods. For example, **DeepSeek** has proposed techniques that aim to reduce computational costs, such as **auxiliary-loss-free strategies** designed to streamline learning without unnecessary redundancies. However, while these approaches improve training efficiency, it remains unclear whether they lead to a net reduction in carbon emissions. Some studies suggest that efficiency gains might be offset by the increasing scale of AI training.

[DeepSeek Research](https://arxiv.org/abs/2408.15664) | [MIT Technology Review Analysis](https://www.technologyreview.com/2025/01/31/1110776/deepseek-might-not-be-such-good-news-for-energy-after-all/)

### Growing Environmental Concerns

A recent **2025 AI Safety Report** flagged the rising emissions and water usage associated with AI infrastructure, particularly as data centers expand at an unprecedented rate. Cooling these massive facilities requires significant water and electricity, creating further environmental strain. Meanwhile, companies like **xAI**, founded by Elon Musk, have built large-scale AI data centers in record time—one in just **19 days**—but often rely on high-pollution energy sources like gas turbines. The rapid expansion of AI infrastructure without sufficient investment in renewable energy exacerbates the environmental impact.

[UK Government AI Safety Report](https://assets.publishing.service.gov.uk/media/679a0c48a77d250007d313ee/International_AI_Safety_Report_2025_accessible_f.pdf) | [Time: Musk’s AI Data Center](https://time.com/7021709/elon-musk-xai-grok-memphis)

## What Can We Do?

AI isn’t going anywhere, but we can make it greener:

- **Use Pre-trained Models** – Instead of starting from scratch, leverage existing models that have already been trained. This avoids duplicating energy-intensive computations and significantly reduces emissions.
- **Optimize Training** – Smarter training techniques like **gradient accumulation, mixed precision, and early stopping** can reduce power usage without sacrificing performance.
- **Use Efficient Hardware** – Choosing energy-efficient GPUs and TPUs can cut emissions while maintaining AI performance.
- **Power AI with Renewables** – Data centers running on **solar, wind, or hydroelectric power** can significantly lower carbon impact.
- **Track Carbon Footprint** – Tools like [ML CO₂ Impact](https://mlco2.github.io/impact/) and [CodeCarbon](https://codecarbon.io/) help monitor emissions and guide greener AI decisions.

## Resources

- [Energy and Policy Considerations for Deep Learning in NLP](https://arxiv.org/pdf/1906.02243)
- [Hugging Face: Transformers are big models](https://huggingface.co/learn/nlp-course/chapter1/4#transformers-are-big-models)
- [Hugging Face: The carbon footprint of Transformers](https://www.youtube.com/watch?v=ftWlj4FBHTg)
- [Google's 2024 Environmental Report](https://www.gstatic.com/gumdrop/sustainability/google-2024-environmental-report.pdf)
- [DeepSeek Research](https://arxiv.org/abs/2408.15664)
- [MIT Technology Review](https://www.technologyreview.com/2025/01/31/1110776/deepseek-might-not-be-such-good-news-for-energy-after-all/)
- [Time - Musk’s AI Data Center](https://time.com/7021709/elon-musk-xai-grok-memphis)
- [UK Government AI Safety Report](https://assets.publishing.service.gov.uk/media/679a0c48a77d250007d313ee/International_AI_Safety_Report_2025_accessible_f.pdf)
- [CodeCarbon](https://codecarbon.io/)
- [ML CO₂ Impact](https://mlco2.github.io/impact/)
