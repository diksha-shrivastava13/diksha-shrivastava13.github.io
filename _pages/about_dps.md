### Digital Product School by UnternehmerTUM

`AI Engineer | Feb '24 - Sept '24`

DPS deserves a different section since even outside the products I worked on with SAP and BMZ (in partnership with DPS),
this was a different experience. The Digital Product School is a training program by UnternehmerTUM, the largest 
start-up ecosystem in Europe.

They form product teams of 4-5, with a Product Manager, an Interaction Designer, SWEs and an AI Engineer and give them
a wide problem space where they are supposed to conduct user interviews, identify pain points, identify which are the most
`critical problems for the user that they can solve in 3 months` and start rapid prototyping. Afterwards comes the phase
of conducting user tests, iterating on feedback and more rapid prototyping. 

Since it's in a very active start-up environment, we get multiple opportunities to pitch to investors and receive 
feedback. All my major "news" about the `pitches made to people at Meta, SAP, IBM, Seroton, MTZ, AWS, 
UnternehmerTUM and United Internet Media GmBH` has come through the time spent in this program. The best thing about DPS
is that no one tells you how to do things or what are the right directions, and you are supposed to figure everything
out on your own. That's the biggest learning. They `treat you like an independent start-up team` with an advisory board
and stakeholders. And the stakes are real. 

I have met the `nicest, sweetest people` here who were always ready to discuss and share wisdom, every achievement was
widely celebrated and every setback opened a whole new learning path. The people at DPS are extremely nice, it's a 
little hard to process that people can be that sweet, especially as they gift you [The Mom Test: How to talk to 
customers & learn if your business is a good idea when everyone is lying to you](https://www.momtestbook.com/) on the 
first day and recommend the Blue Bible ([The Lean Startup](https://theleanstartup.com/book)) later. And trust me, users
lie all the time, no one wants to be mean. As an undergraduate, I cannot imagine a better place to have learnt engineering.

There was way too much compressed learning in a short duration of 3 months when I was on-contract with SAP. The only 
experience I had with generative AI before this had been finetuning a model for a hackathon by Complex Systems Lab, IIIT Delhi,
using Cohere's API. Two months in, I was `customising LlamaIndex modules to perform on queries from 100,000+ users`.

I was actually very nervous when I joined, considering I was the youngest in my batch and almost everyone else was a Masters
student. My biggest fear was that while there's a good enough chance I would be able to build the expected level of amazing,
which is still an achievement, but it does not blow your mind and that way more learning is required to `leap to the unexpected,
people-can't-stop-talking level of amazing`. And it gave me many sleepless nights.

Fun Fact: After I threw away the AI backend, and we decided to pivot to building internal Perplexity/SearchGPT/Phind.ai,
the Chief Strategy and Operating Officer of SAP, Sebastian, was visiting the Munich office and our co-working site, and so 
there were a lot of SAP employees in the building. I was in the kitchen getting chai when I heard someone talking about `there's
this team here, and they're doing crazy stuff...`. Cue * happy, little hops *.

It was actually wild to see how excited people were about the product we built for SAP! I have heard "they're doing _crazyyy_
stuff" a lot of times in the final few weeks of product shows and that we crossed all expectations that were there before us
in the history of DPS and set the bar much, much higher. 

**In hindsight**, that fear of maybe not being good enough actually worked wonders.

When I later accepted the contract with BMZ, I was expecting to build something `to automate data science`, much like recent
demos from PremAI or PandasAI or this other beautiful product which had released when ChatGPT was still new. And I thought
God, _that_ is cool!

It turned out that the problem was so insane that there was no way the solution would be that straight-forward. It took so
much time to even understand all the nuances of the problem space. I did not speak German, and all the reports were in German,
and as an AI Engineer, I absolutely could not go on without understanding my data. It was due to the `insane effort put in
by the Product Manager` that we managed to build so much (and outperform British Data Scientists struggling with the same
issues). 

Consider this, you are building a system which helps make decisions for country policies of ~60 countries. The work you
do is going to `inevitably affect the entire population of those 60 countries`. The responsibilities are huge! You have to
build a reliable system, both in terms of AI and UX. 

The secret to a good life as an AI Engineer is to `respect structured outputs if it's not directly user-facing`. "Agents"
without agency are an UX component, and it would be more accurate to call them style-guides or machines but that's strictly
my own opinion. While the experience with SAP taught me AI Engineering, the experience with BMZ was `solely research-focused`,
although I had to write the backend for the AI features and always pay attention to the product side. 

The highest value generated here, in my opinion, would be the research I did and the methods I tried for this system. God,
it was a hard problem. It in only recently I realised that `LLM-driven Monte Carlo Tree Search`, in a little different way from the 
[NeurIPS '23 paper](https://arxiv.org/abs/2305.14078), would have solved the search needed to assess previous outcomes of projects in same conditions and 
predict outcomes. This came after obsessing over the problem for more than a month after the product handover.

About the product handover, I honestly did not expect it to be _that_ celebrated. This was the `first project` DPS had in
partnership with the Government, and hopefully the success here means nice things for the expansion of this program 
in Europe. It gave me many more sleepless nights than I care to count now. And that comes because this problem required us
to solve `the problem of reasoning`. The lucky thing was that the problem domain here is narrow, so we could still perform
guided reasoning which could be generalised to future reports without struggling too much with generality. 

I eventually got so used to product shows, that my best moments in this contract have been `developing 2 prototypes with
7 AI features in 6 hours which had complex pipelines`. When you've spent enough time engineering, writing the code itself
is a lot faster. 

"Digital product development never stops", that's what I tell myself as I struggle to move on. This was an open-ended 
problem and while we did solve a major chunk of it, it feels like I still left it open. And that's where the deep dive
into everything LM Reasoning began 🙂.