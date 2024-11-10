### SAP

`AI Engineer | Feb '24 - May '24`

In a five-membered cross-functional team of a Product Manager, SWEs and an Interaction Designer, I was responsible
for the AI features of the product "ai-SAP" for the problem space `Wouldn’t it be great if developers at SAP field 
service management would always know what to do whenever they run into an issue?`

The first three months here gave me many of my firsts. It was my first time developing a product from scratch, 
first time learning the agile mindset of shipping multiple times a week, first time presenting to investors which we 
did so often, that I eventually got used to just being able to show the product up and running at any time.

The hardest part of this problem was the user feedback loop. How to make sure we know `which link is the most
relevant to the user problem and proceed to rank it higher` the next time a question in the same space is asked? What is the
strongest signal?

I was done developing the `semantic search` and completing most of the stakeholders' requirements at Week 3-4, and it was
received a lot better by the users than the keyword-based search that their documentation already had. I had even developed
custom query and chat engines. I spent the next few weeks tinkering with `ML on user behaviour graphs` and determining
what can be some useful signals. The cute part about this problem was that the stakeholders were developers, the user were developers, and we were developers,
so we had good mutual understanding of how things worked and weekly status. 

Since the beginning, we had been taking inspiration from products like Phind.com and Kapa.ai. At the "Rip the Product"
session at week 6, the Core Team at DPS pushed us to `be bold and brave` and afterwards I decided to `throw away the entire
AI` backend. We started building the Internal SearchGPT which can answer user questions from resources scattered
across `internal documentation, Slack and GitHub` with a list of sources and an option to provide feedback from UI as well
as natural conversation.

The interesting parts of this are proprietary work which I should not talk about. Some other highlights here were writing
many `15+ readers and ~13 LLM calls, custom modules for chunking, parsing and metadata augmentation, integrating Mlx 
into LlamaIndex, hosting private LLMs, the continual augmentation of answerable questions which aligns the knowledge 
base closely to user requirements`.

I gave a two-hours long technical presentation during the product handover detailing every part of the code, every technical decision,
all the whys of the models I used, scope for future development, all the custom augmentations I had made. That presentation
was `one of my brightest experiences of 2024`.

*(In partnership with Digital Product School)*