### Digital Product School by UnternehmerTUM

`AI Engineer | Feb '24 - Sept '24`

In a five-membered cross-functional team consisting of a Product Manager, SWEs and an Interaction Designer,
I was responsible for the AI features of a product for the problem space `Wouldn’t it be great if Country Policy Officers 
could drive forward their projects by always having the right conclusions from a sea of reports?` Internally, it meant 
using AI to generate insights not written in the reports to aid in policy decisions and negotiations.

Externally, we were asked to do "something innovative". And this problem really *did* need innovation. To paint a simple
rosy picture of the challenge, consider this scenario -

At the lowest level Z, you have 7-8 reports of 30-200 pages each which are contained into folders at level Y. There exist 
50-60 such folders at level Y which are kept into the boxes of level X. There exist 50-60 such boxes at level X which are kept into
at least 7 rooms of level W at that you know about. There exist 60-80 houses, all of which have the rooms of level W.

<div style="float: right; width: 500px; height: 270px; margin: 8px;">
  <img src="/assets/img/bmz_fig_lab.jpg" style="width: 100%; height: 100%; object-fit: cover;" alt="">
</div>

Now, you need to draw a system which can look into `one complex flowchart inside a report at level Z and find all flowcharts,
tables and text which exist in this entire neighbourhood by comparing the similarities and understanding all relationships
between every entity at every level`. This is sometimes numerical, sometimes textual data, which changes frequently, 
has very limited structural similarities, through which you need to answer critical questions.

Room X3, House W5 won't be happy if it got flooded the same way as Room X45 in House W12 had in year 2012 because you 
didn't point out that it had the same conditions of earthquake!

*And*, this has to scale up!

Now, "you" are an LLM and you gotta answer these questions to the most unforgiving users: `Policy Officers of 60+ 
Countries`, in charge of overseeing programs under country partnerships with Germany who do this task manually without a
system in place to even draw the levels of hierarchy. 

In another rosy way, consider you only have 1 node per page for the reports at level Z (which is a terrible idea IRL), how
many nodes do you have to look at for every minute detail?

So when I say "task", I mean answering questions like `anomalies in reports, risk assessment, chances and causes of delay,
impact of risks, projecting budget changes, scope of improvement in programs, recommendations for policy dialogue, KPI 
growth analysis, generating comparative reports of the impact delivered throughout years, making decisions for "rooms"
by looking at their contribution to the "neighbourhood".`

**And this would explain why I got immersed in exploring reasoning for language models afterwards 🙃.**

Long story short, we beta-launched the product with reasoning and analysis pipelines for the "task" and submitted a 
one-year roadmap to generate enough planning-reasoning-thinking data on which SLMs can be trained to act as mixture-of-experts for
each of the subtasks.

**Three weeks later, o1 was released.**

Read more: [Building a what now? - My Experience on Working with Agents, LMs and the Challenge of Reasoning](my blog link).
