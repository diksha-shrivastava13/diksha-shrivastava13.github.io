---
layout: distill
title: Reasoning in Holistic Systems
description: My Compiled Work on Reasoning, Abstract Representation and Similar Link Prediction
permalink: /research/
pretty_table: true
---
# Introduction 👋 

This work presents all the research and engineering I've done in the domain of language model reasoning, abstract representation of linked
entities and similar link prediction. I worked on-contract for the **Federal Ministry of Economic Cooperation and Development
of Germany (BMZ)** in partnership with the Digital Product School by UnternehmerTUM during summer 2024, 
where I explored the efficiency of Large Language Models (LLMs) in designing Decision-Making Systems for unstructured 
reports in a five-level hierarchy to aid in country policy decisions and negotiations.

The work at BMZ required me to design complex reasoning and analysis pipelines which could answer critical questions by finding all 
relevant nodes and comparing the similarities and understanding the relationships between every entity at every level. I 
accomplished this by following a world model along with policy models for each of the subtasks with multi-hop reasoning with
an agentic approach.
I also talk about the fifty-four modifications I tried for this system, including Property Graphs, GraphRAG, Generation 
of Agentic Planning-Reasoning Data for Mixture-of-Experts (MoE), Agentic Standardising of Reports, Reason-Guided Parsing and 
the multiple variations of data representation.

Following the work at BMZ, I was intrigued by the problem of the large data generated in holistic systems on 
which it is hard and time-taking to determine the correlations between subsystems and entities, and formulate machine 
learning problems. Hence, I explored hybrid ways to represent the data and relationships of subsystems and eventually came
up with Swan AI. My research at Swan AI focused on answering the question: **is there a way that Language Models can learn
the relationships between entities, identify similar links on the go and make predictions?**

I further talk about some thought experiments I conducted with LLMs to test their ability to learn links, identify and
predict similar links by creating fictional characters in the "Arc" world.
With no surprise to anyone, GPT-4o miserably failed.
While I didn't have a benchmark to showcase, the experiment was based on the same concepts as the ARC-AGI 
problem: learning the relationships in new data, and reason based on the relationships.

My research with BMZ, Swan AI and afterwards led me to the conclusion that agency in a dynamic database and
training pipelines is necessary to represent learnt links so the data objects may be fluid, but the relationships themselves
are "memorised." I further emphasize the importance of frameworks (such as LeanAgent, which was shortly released afterwards)
which have some factors of hypotheses cycles, dynamic databases, and continual learning. The more recent works on 
Test-Time Training (TTT) also support the importance of hypotheses cycles. I conclude by arguing the need for more work 
on data representation.

----------

<div style="font-size: 13px; font-weight: lighter; font-style: italic;">
Note: The data used in these projects is sensitive, and I have taken the utmost care to protect all private information.
In case anything missed my attention, please let me know by emailing at diksharaigarh57@gmail.com.
</div>

----------

# The Problem at BMZ
### Designing a Decision-Making System for Country Policy Decisions & Negotiations

In the summer of 2024, I accepted a contract to work on a dashboard which automates data science for a GovTech product. I thought I would be building a <em>multi-agentic workflow</em> which performs EDA, a beautiful dashboard with toggles for each of the features which visualizes the impact on the target and helps the government <em>decide on factors like budget, implementation area, impact of rainfall (or the Ukraine war)</em> and help make better decisions while <em>protecting their projects from risks</em>.

In hindsight, I think I was inspired by this Chess problem I had been working on in 2023: what is the <em>maximum number of blunder moves a machine can make while still winning</em> the game so that the human opponent doesn’t suspect it’s a machine (because of sheer perfection) and pass the turing test? 
<br>A little fun fact: it is hard to make a machine win only 55% of the time! 

Continuing ahead, I was expecting a fairly straight-forward multi-agentic workflow, much like the recent demos from PremAI, and I thought this is cool! After the onboarding with the <em>Data Scientists & Policy Officers at BMZ</em>, it began to sink in that the problem is nearly not as simple as that because the <em>complex-hierarchy data sucks.</em>

Allow me to paint a picture to convey what I mean by a “complex” hierarchy:

200 Pages in a single Report.<br>
8 Reports in a single Project.<br>
60 Projects in a single Program.<br>
60 Programs in a single Theme.<br>
8 Themes in a single Country.<br>
60 Countries that you have partnerships with!<br>

And this hierarchy does <em>not always have sequential relations</em>. Now why was any of it a problem? Before I dive into the details, we need to take a look into the problem from three different perspectives.

**First: The Country Policy Officers at the German Federal Ministry**

These are our <em>key users</em> facing the problem of navigating this aforementioned complex hierarchy to answer critical questions for the <em>BMZ leadership, the parliament and the people</em>. They need to prepare for 
1. commissioning new projects, 
2. providing recommendations for annual negotiations with partner countries and 
3. continually work to improve the state of projects, 
4. mitigate risks, 
5. examine outcomes, 
6. analyze changes for budget and duration
and help make a ton of data-driven decisions!

Now the problem begins with <em>not having a central data lake</em> for the reports and <em>no structured database</em> for these reports. They just do it with sheer patience and hardwork. The answer to any of these questions requires them to <em>analyze the relationships between entities at multiple levels</em> by looking at a <em>complex, multidimensional space</em> where none of the relationships are apparent. 

It also requires <em>a lot of expertise and training</em> to get comfortable with this data and analysis work. I myself took 3-4 weeks just to understand what this problem might require, and I kept asking clarifying questions for the hierarchy till the product handover.

<b>Second: The Stakeholders at the German Federal Ministry</b>

The stakeholders were the <em>Senior Policy Officers and Senior Data Scientists</em> at the DataLab at the BMZ. They wanted us to design a system which can present <em>AI-generated insights from the reports which are not explicitly written</em>. These reports consisted of complex <em>multi-page flowcharts, tables and mostly text</em> but they didn’t follow the same structure and <em>varied according to country, implementing organizations and yea</em>r. They asked us to do <em>something innovative</em>. 

To clarify here, I joined this project after it had already been at the Digital Product School for three phases of development. When I joined the fourth phase, it was with the expectation that they’ll receive something more than simple Retrieval-Augmented Generation and receive a dashboard where they can see <em>comparative analysis of KPI growth across the levels of the hierarchy across years.</em>

To give more context about the Digital Product School: cross-functional, five-membered teams consisting of a product manager, an AI Engineer, software engineers and an interaction designer are presented with a wide problem space on which they have to pinpoint the user problems by conducting user interviews, rapid prototyping and iterating from feedback to deliver a final product. The problem space for BMZ was: <em>“Wouldn’t it be great if Country Policy Officers could drive forward their projects by always having the right conclusions from a sea of reports?”</em>

When the product was handed over to my team, the user could upload a project report to the portal with a form which was auto-filled from the fixed fields retrieved from the report to obtain summaries of five sections along with a table. This process took five minutes. Looking at the problem space, a lot more work was required to match stakeholder expectations. On top of that, this was the first project that the Digital Product School had in partnership with the Government, so it needed to be a success.

<b>Third: The Team at the Digital Product School</b>

Expectations are wild with AI systems, especially with the keyword “agentic”. The expectations were high from the team, the stakeholders and the mentors. I have had to develop multiple prototypes just to communicate what the agents can and cannot do, so we could make better decisions. 

The stakes were high. Imagine your work necessarily <em>impacting the lives of people of ~60 countries</em>. The responsibilities are huge! The system needs to be reliable, efficient and always cater to minute details. I remember once showing the results from the system I designed to a friend and they laughed, assuming the AI definitely hallucinated, since <em>how does the [redacted] war impact the [redacted] factor in the faraway [redacted] country?</em> I checked the reports thoroughly afterwards, and indeed it <em>would’ve caused the [redacted] impact on the country even when it wasn’t directly mentioned</em> in reports of projects belonging to the country that year.

Those were the sort of <em>hidden insights and projected budget changes</em> that our stakeholders wanted, but it didn’t come before <em>failing in 53 ways</em>. And even then, I can see two more years of work needed for this project. But I’m getting ahead of myself. The major problem was -

For assessing the next steps for Project ABC
1. I need to look at the <b>KPI growth across years</b> for every project in every program in every country in every theme for any year which <b>had situational similarity</b> to any of the critical factors for the current status of Project ABC. 
2. I need to look at <b>every other entity at every level of the hierarchy</b>, and make decisions for Project ABC depending on <b>relative importance and the feasibility</b> of my own country/leadership/political atmosphere and the like.

Bringing back the Chess analogy, <em>what is the maximum number of losses I can take while ensuring maximum win?</em>

This has to be <em>done dynamically</em> <em>for every project from every program of every country, every time</em>. It’s essentially the same problem (although the win for the chess scenario was maximizing the must-be-human belief of the opponent) but it’s real and unstructured data, and instead of two players, if we really dive deep into it, it will become <em>a 60-player game</em>. The world somehow works that way. 

This is when the problem of reasoning began really bothering me.


# My 54 Modifications on Naïve RAG for BMZ


My biggest learning at DPS has been to keep things simple, although I do tend to slip sometimes. I find that an effective balance between exploration and exploitation is to ship fast and let things break (for some cases); you get strong signals for the next better approach while still fulfilling some user requirements.

Until now, I’ve tried to explain the nuances, implications and urgency of this problem from the user’s perspective. Now it’s time to dive into the technical details of the problem. It’s important to mention here that while this gig was a more research-focused one, unlike my previous experience with SAP through the Digital Product School, the expectation is the same as a Product Team working in an agile way: shipping 2-3 features per week.  
So while I couldn’t solely focus on research and designing the best possible system by exploring multiple ways as I had to constantly maintain the backend, I delivered features as soon as I got incremental results from the research.

**Planned User Journey on the Platform**

For the technical specifications to make sense, it’s important to first look at some user stories and an average user’s interactions with the platform.

The User: Country Policy Officer of South Africa (let’s say)

Their Purpose: Find important information related to an ongoing project XYZ in partnership with Germany to answer critical questions and draw proposals.  
Information includes:

* \[From one report\] Impact Matrix of the project, with the KPI performance for each of the goals at the project and program levels.  
* \[From one report\] Associated risks for each of the goals at the project and program levels, urgency categorization and suggested mitigation measures.  
* \[From one report\] Recommendations for Political Dialogue and Sector Dialogue for Project, and Improvement of Program.  
* \[From one report\] Important topics for steering cooperation in the Aktionsfeld.  
* \[From one report\] Lessons Learnt from Project Implementation  
* \[From one report\] Basic Information about the report, including its association with all the levels of the hierarchy.  
* \[From multiple reports\] Overview of Impact Matrix across years for the same project.  
* \[From multiple reports\] Overview of Risk Mitigation across years for the same project.  
* \[From multiple reports\] Overview of Progress across different projects belonging to the same program, throughout the years.  
* \[From multiple reports\] Anomalies across reports at the same level, which are not explained or mentioned explicitly.  
* \[From multiple reports\] Risks identified in a country for one project or program which can affect other projects or programs.  
* \[From multiple reports\] Risks identified in a similar program for another country which can carry over to the host country.  
* \[From multiple reports\] Chances and causes for potential delay and budget changes.

The User Journey on the Platform:


| Steps | User Action                                                                                                                                                                | Technical Feature                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      | Problems Addressed                                                                                                                                                                                                        | Information Gained                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
|-------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1\.   | Logins onto Portfolio Navigator                                                                                                                                            | Authentication for multiple users.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     | Earlier, users received reports on the mail without a central data lake to access all reports.                                                                                                                            | \-                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| 2\.   | Views the Country page. Selects their country.                                                                                                                             | Frontend features: search, visualisation of maps etc.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  | Due to the lack of platform, the hierarchy wasn’t reflected and it wasn’t easy to navigate in the hierarchy.                                                                                                              | Quick navigation between levels of hierarchy. Knowledge about how different levels connect to each other.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| 3\.   | Opens the specific country page which displays a list of all programs and independent projects, along with their duration, risk status, progress status and a description. | The latest fixed fields data should be fetched from the database, including the changes in duration and budget from existing reports.                                                                                                                                                                                                                                                                                                                                                                                                                  | Difficulty in finding the latest updated information about the programs or projects. (They used ctrl \+ f).                                                                                                               | Changes in duration and budget. Quick view at what the program or project is about, the implementing agency and the like.                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| 4\.   | Opens a specific Program or Project page. The overview tab shows the latest fixed fields data, progress over the impact matrix and risk assessment.                        | The tables, flowcharts and text from multiple 30-120 pages reports should be fetched. This content needs to be parsed for all the details about impact matrix and risks. The risks and progress need to be arranged according to the year to provide an overview. The risks and progress should be from programs as well as projects. The risks and progress should be from programs or projects with situational similarity as well. Suggestions to mitigate lists and actionable steps. Any anomalies in the reports belonging to the same umbrella. | No need to manually sort through multiple reports for specific information. No over-reliability on implementing agencies to always provide correct information. Can easily find needles-in-the-haystack level of details. | Overview of Impact Matrix across years for the same project. Overview of Risk Mitigation across years for the same project. Overview of Progress across different projects belonging to the same program, throughout the years. Anomalies across reports at the same level, which are not explained or mentioned explicitly. Risks identified in a country for one project or program which can affect other projects or programs. Risks identified in a similar program for another country which can carry over to the host country. Chances and causes for potential delay and budget changes. |
| 5\.   | Looks at a report for the program from previous years. The yearly report tab shows the                                                                                     | Specific sections from the previously uploaded report about recommendations for policy dialogue and learnt lessons from implementation need to be fetched.                                                                                                                                                                                                                                                                                                                                                                                             | No need to manually search for this in the report.                                                                                                                                                                        | Recommendations for Political Dialogue and Sector Dialogue for Project, and Improvement of Program. Important topics for steering cooperation in the Aktionsfeld. Lessons Learnt from Project Implementation                                                                                                                                                                                                                                                                                                                                                                                      |
| 6\.   | Uploads a new report within the same umbrella.                                                                                                                             | Auto-filled the upload form by fetching the basic information from the report. Check whether there are any anomalies in the new report compared to previous ones. Extract risks and impact matrix. Update the budget and duration changes, if any. Update the latest levels of KPIs from the report.                                                                                                                                                                                                                                                   | The most updated and correct information will always be available and any discrepancies can quickly be confirmed with the implementing agencies.                                                                          | Impact Matrix of the project, with the KPI performance for each of the goals at the project and program levels. Associated risks for each of the goals at the project and program levels, urgency categorization and suggested mitigation measures. Basic Information about the report, including its association with all the levels of the hierarchy.                                                                                                                                                                                                                                           |

*Note: This is in terms of relevance to the AI side of the product, except when to provide a full cycle for the product. The Full-Stack app itself solved the critical problem of navigating between the layers of the hierarchy.*

**The AI-Based Features for the Product**

The platform requires the processing of reports, a data lake for common access to the reports, a database for extracted sections relevant to the user needs and efficient parsing which can connect multiple sections from multiple reports at once, and bring all this information to the user in the overall analysis. Summarising this, these were the AI-Based features developed:

1. Search capability in natural language on one document to extract content for the yearly monitoring reports and proposals.  
2. Search capability for multiple documents at once for the changing values of the same KPIs and entities.  
3. Extraction of the complex tables, flowcharts and text from documents along with entity relations and inferred KPIs.  
4. Determination of learning lessons and scope of improvements for the programs.  
5. Recommendations for political dialogues for the project implementation and for improvement of programs.  
6. Risk analysis for factors which might lead to delays and non-completion of programs.  
7. Detection of Anomalies in multiple reports belonging to the same umbrella.  
8. Search-based similarity and comparison analysis of growth of projects with overlapping factors.  
9. Analysis of KPIs growth and effect from projects to programs levels throughout the years and associated risks, causes, impact, activities and applications.

With these features, I implemented an efficient RAG pipeline with multiple features which responds in a maximum of 15 seconds, improving over the previous performance of 5 minutes for a single-report RAG.

**The Technical Challenges to Tackle**

The field moves so fast that some of these problems can be solved a lot better now than June 2024, however the core problem remains the ability of the system to find and take into consideration the relevant sections from multiple reports spread across a complex hierarchy and generate the final sections for the overviews. What makes this problem more complex over standard RAG use-cases is 

(i) the critical government use-case where mistakes can be disastrous,   
(ii) while I’ve previously designed RAG-based systems for codebases and technical documentation which requires an Abstract Syntax Tree (AST) or a well-designed property graph, this problem has complex entity relationships which need to be tracked across a five-level hierarchy and maintained over years,   
(iii) there’s very little consistency in the structure of these reports which makes it a problem to always dynamically extract all the information correctly even from one report at a time.

Agent-based parsing with multi-hop reasoning and retrieval solves some of the issues. However, even with Agent-guided search and retrieval, the functionality of the application is limited with more technical challenges. More challenges arise due to:

**I. On the Generation Side: Long Context is not enough** 

To get exact performance for reasoning-based search/retrieval/parsing/generation, the system prompt needs to be detailed and cover minute details for where the information can be found, what it might look like and what to do with it. 

Before going ahead with more Agentic terminology, let me pause here and clarify what I mean by agents.

Some time ago, someone asked a community of ML Engineers and Researchers what they understand by “Agent” and everyone had widely varying answers. My personal answer is that *an Agent should have agency*. What happened with Character.ai is a very irresponsible use of “Agents”. To give context here, a kid was talking to an AI-generated character in a system without a guardrail to report suicidal talk or cease the conversation and he died. This particular “agent” did not have any *agency to act*. For instance:

- I can call my dog a bird and tell him he can fly to the moon and back.   
- This will not make him grow wings.   
- I can supply him with gear to mimic a bird’s behaviour (function-calling in agents).  
- Turns out he’s sad because birds cannot fly to the moon and back either.  
    
  While this is an analogy, it still showcases that human error in deciding all functions associated with an “agent” can lead to unpleasant to terrible results. It would have been more accurate to call this system of  (system-prompt \+ function-calling) a style guide or machine. A system prompt, on its own, sadly does not have any agency to act. On the other hand, people are designing agencies for niche tasks which hypothesise and decide on an action (like [LeanAgent: Lifelong Learning for Formal Theorem Proving](https://arxiv.org/abs/2410.06209)).

Even though we were limited by the requirement of keeping everything on Azure which meant we could only use the OpenAI models, I’ve tested the system with the long context provided by Gemini, and it easily breaks. Long context makes it very difficult for the Large Language Model to keep track of all the instructions, as well as the many nodes (\~2000) required to answer a single question from multiple reports at once. 

I have tried LongContextReorder ([Lost in the Middle: How Language Models Use Long Contexts](https://arxiv.org/abs/2307.03172)) to handle the problem of rearranging context such that the most relevant data is in the beginning or the end of the entire context, but there are two more issues with it:  
(i) The entire set of \~2000 nodes is relevant and *needed* for the query,  
(ii) This is only useful when your use-case deals with a ranking problem among the nodes.  
(iii) There are minute details buried in the long context which might be very important and might be ignored by the LLM.  
For this particular use-case, it is only after strict, graph-based ranking that a set of \~2000 nodes have been selected.

For more complex pipelines, like chaining responses of a reasoning-retrieval-reasoning-parsing-generation process to perform the next reasoning-retrieval \-reasoning-parsing-generation process with a different reasoning guideline and purpose, the response of the previous process adds to the context of the next process. 

What results is absolute chaos which this single function cannot always effectively handle.  
As the number of reports into consideration increase, the limitations of AI have to be handled by making better product choices and UI.

**II. On the Retrieval Side: It’s slow, for starters**

My favourite and most challenging problem for this product is the *Data Representation*. How do you efficiently represent the data, which is (i) already in a complex hierarchy with non-sequential relations, (ii) consists of complex multi-page tables, flowcharts and unstructured data, (iii) has hidden entity relationships across the hierarchy which need to be tracked throughout years, (iv) has little structural similarity across reports?

The Naïve and the simplest solution is to first test and discard all variations of the Naïve RAG. Just for reassurance, try long context models to get inevitably bad results.   
The next step is the variation in the parsing pipelines. While ColPali ([ColPali: Efficient Document Retrieval with Vision Language Models](https://arxiv.org/abs/2407.01449)) and its variations can handle this much more effectively now, the option at the time of development was to use LLM \+ OCR parsing with output in markdown format for the most accuracy.   
The downside of using any variation of LLM \+ OCR is that it cannot effectively handle multi-page tables and flowcharts, and unfortunately for us, that is where all the information about KPIs is documented in the reports. Extracting the tables and flowcharts correctly is a must. 

The next step is the variation in the form of data representation, and the multiple approaches with Vector Databases, Metadata Augmentation, Knowledge Graphs, Property Graphs, GraphRAG, Agentic Standardising, Agentic Parsing, Agentic Planning, Agentic RAG, Multi-Document Agents etc.. The list does not end easily.

The final step on this side of things is the retrieval itself. Traditional search over any of the above structures becomes weak when a correct set of \~2000 nodes is required. The k of top-k nodes here is a set of about 100-2000 nodes where the set needs to be correct. On the other hand, LLM-guided searches like multi-document agents were not useful at all for this type of analysis where specific entities, their relationships and their status from multiple reports need to be extracted. Prompts alone are never enough. The key to improving performance for any LLM-based system lies in its data representation.

As a quick TL;DR before I dive into my account of approaches, my final solution was \-

(i) agentic multi-hop reasoning and retrieval,  
(ii) agentic parsing for the reports,  
(ii) agentic standardising of the reports,  
(iii) hierarchical representation in a vector database with custom user-verified metadata,  
(iv) chaining responses to guide retrieval and generation, around the problems,  
(v) pipeline to obtain planning and reasoning data to train SLMs in the future,  
(vi) (after handover) LLM-guided Monte Carlo Tree Search to improve over everything above.



<div class="header-container">
  <h3 id="holistic-systems" class="custom-main-heading"> 
    The Problem with Holistic, Interrelated Systems
  </h3>
</div>

60-player chess. Fly with that analogy.


<div class="header-container">
  <h3 id="llms-formulate-ml" class="custom-main-heading"> 
    Can Language Models Formulate ML Problems?
  </h3>
</div>


<div class="header-container">
  <h3 id="swan-ai-hybrid" class="custom-main-heading"> 
    Developing Swan AI & the Six Graphical Representations for Complex Systems
  </h3>
</div>


<div class="header-container">
  <h3 id="thought-exp-frostbite" class="custom-main-heading"> 
    Thought Experiment: <span class="description">Can LLMs Understand & Predict Similar Links in the "Arc" World?</span>
  </h3>
</div>


<div class="header-container">
  <h3 id="conclusion" class="custom-main-heading"> 
    The Need for Hypotheses Generation Cycles, Similar Link Prediction & Agency for Dynamic Databases
  </h3>
</div>

### My 54 Modifications on Naive RAG for BMZ

Until now, I was focusing on the problem from a user's perspective. From here on, I recollect the problem as it was 
presented to me when I started working on the project.

Technical Challenges:

1. Extraction of long JSON responses, with at least 12 json objects to extract the fixed data for auto-filling forms.
2. 


### References

[1] Zhao, Zirui, et al. 'Large Language Models as Commonsense Knowledge for Large-Scale Task Planning'. arXiv [Cs.RO], 2023, [http://arxiv.org/abs/2305.14078](http://arxiv.org/abs/2305.14078). arXiv.

[2] Mirzadeh, Iman, et al. 'GSM-Symbolic: Understanding the Limitations of Mathematical Reasoning in Large Language Models'. arXiv [Cs.LG], 2024, [http://arxiv.org/abs/2410.05229](http://arxiv.org/abs/2410.05229). arXiv.

[3] Kumarappan, Adarsh, et al. 'LeanAgent: Lifelong Learning for Formal Theorem Proving'. arXiv [Cs.LG], 2024, [http://arxiv.org/abs/2410.06209](http://arxiv.org/abs/2410.06209). arXiv.

[4] Aniva, Leni, et al. 'Pantograph: A Machine-to-Machine Interaction Interface for Advanced Theorem Proving, High Level Reasoning, and Data Extraction in Lean 4'. arXiv [Cs.LO], 2024, [http://arxiv.org/abs/2410.16429](http://arxiv.org/abs/2410.16429). arXiv.

[5] Gu, Yuling, et al. 'Digital Socrates: Evaluating LLMs through Explanation Critiques'. arXiv [Cs.CL], 2024, [http://arxiv.org/abs/2311.09613](http://arxiv.org/abs/2311.09613). arXiv.

[6] Zhou, Yangqiaoyu, et al. 'Hypothesis Generation with Large Language Models'. arXiv [Cs.AI], 2024, [http://arxiv.org/abs/2404.04326](http://arxiv.org/abs/2404.04326). arXiv.

[7] Zhang, Shiyang, et al. 'Intelligence at the Edge of Chaos'. arXiv [Cs.AI], 2024, [http://arxiv.org/abs/2410.02536](http://arxiv.org/abs/2410.02536). arXiv.

[8] Gao, Yunfan, et al. 'Retrieval-Augmented Generation for Large Language Models: A Survey'. arXiv [Cs.CL], 2024, [http://arxiv.org/abs/2312.10997](http://arxiv.org/abs/2312.10997). arXiv.

[9] Dohmatob, Elvis, et al. 'A Tale of Tails: Model Collapse as a Change of Scaling Laws'. arXiv [Cs.LG], 2024, [http://arxiv.org/abs/2402.07043](http://arxiv.org/abs/2402.07043). arXiv.

[10] Chollet, François. 'On the Measure of Intelligence'. arXiv [Cs.AI], 2019, [http://arxiv.org/abs/1911.01547](http://arxiv.org/abs/1911.01547). arXiv.

[11] Levy, Omer, et al. 'Zero-Shot Relation Extraction via Reading Comprehension'. arXiv [Cs.CL], 2017, [http://arxiv.org/abs/1706.04115](http://arxiv.org/abs/1706.04115). arXiv.

[12] Ma, Xiao, et al. 'Beyond ChatBots: ExploreLLM for Structured Thoughts and Personalized Model Responses'. arXiv [Cs.HC], 2023, [http://arxiv.org/abs/2312.00763](http://arxiv.org/abs/2312.00763). arXiv.

[13] Levy, Mosh, et al. 'Same Task, More Tokens: The Impact of Input Length on the Reasoning Performance of Large Language Models'. arXiv [Cs.CL], 2024, [http://arxiv.org/abs/2402.14848](http://arxiv.org/abs/2402.14848). arXiv.

[14] Pfau, Jacob, et al. 'Let’s Think Dot by Dot: Hidden Computation in Transformer Language Models'. arXiv [Cs.CL], 2024, [http://arxiv.org/abs/2404.15758](http://arxiv.org/abs/2404.15758). arXiv.

[15] Chan, Jun Shern, et al. 'MLE-Bench: Evaluating Machine Learning Agents on Machine Learning Engineering'. arXiv [Cs.CL], 2024, [http://arxiv.org/abs/2410.07095](http://arxiv.org/abs/2410.07095). arXiv.

[16] Tang, Jiabin, et al. 'GraphGPT: Graph Instruction Tuning for Large Language Models'. arXiv [Cs.CL], 2023, [http://arxiv.org/abs/2310.13023](http://arxiv.org/abs/2310.13023). arXiv.

[17] He, Zhongmou, et al. 'LinkGPT: Teaching Large Language Models To Predict Missing Links'. arXiv [Cs.LG], 2024, [http://arxiv.org/abs/2406.04640](http://arxiv.org/abs/2406.04640). arXiv.

[18] Shomer, Harry, et al. 'LPFormer: An Adaptive Graph Transformer for Link Prediction.' Proceedings of the 30th ACM SIGKDD Conference on Knowledge Discovery and Data Mining, ACM, 2024, pp. 2686–98. Crossref, [https://doi.org/10.1145/3637528.3672025](https://doi.org/10.1145/3637528.3672025).

### Contacts

Stakeholders at the German Federal Ministry of Economic Cooperation and Development:

* **[Lea Smidt](https://www.linkedin.com/in/lea-smidt-4ba804ab/)**, Senior Policy Officer at Data Lab, Federal Ministry 
of Economic Cooperation and Development (BMZ). Mail: [lea.Smidt@bmz.bund.de](mailto:lea.Smidt@bmz.bund.de)

* **[Tanja Hagemann](https://www.linkedin.com/in/tanjahagemann/)**, Senior Data Scientist at Federal Ministry of 
Economic Cooperation and Development (BMZ). Mail: [tanja.Hagemann@bmz.bund.de](mailto:tanja.Hagemann@bmz.bund.de)

* **[Ludwig Bald](https://www.linkedin.com/in/ludwigbald/)**, Data Scientist & Senior Policy Officer at Federal 
Ministry of Economic Cooperation and Development (BMZ). Mail: [ludwig.Bald@bmz.bund.de](mailto:ludwig.Bald@bmz.bund.de)

The Core Team at the Digital Product School by UnternehmerTUM:

* **[Marcus Paeschke](https://www.linkedin.com/in/marcus-paeschke-66305a55/)**, Team Mentor and Head of Interaction 
Design at the Digital Product School. Mail: [marcus.paeschke@unternehmertum.de](mailto:marcus.paeschke@unternehmertum.de)

* **[Tobias Kalkowsky](https://www.linkedin.com/in/tobias-kalkowsky/)**, Team Mentor and Agile Coach at the Digital 
Product School. Mail: [tobias.kalkowsky@unternehmertum.de](mailto:tobias.kalkowsky@unternehmertum.de)

* **[Dr. Afsaneh Asaei](https://www.linkedin.com/in/dr-afsaneh-asaei/)**, Head of Artificial Intelligence at the Digital
Product School. Mail: [asaei@unternehmertum.de](mailto:asaei@unternehmertum.de)

* **[Michael Stockerl](https://www.linkedin.com/in/michael-stockerl-8584a347/)**, Director of the Digital Product School.
Mail: [stockerl@unternehmertum.de](mailto:stockerl@unternehmertum.de)

* **[Lorenz Hutterer](https://www.linkedin.com/in/lorenz-hutterer-2a1a021a5/)**, Manager Innovation and AI, Head of 
Operations and Business Development at UnternehmerTUM. Mail: [lorenz@dpschool.io](mailto:lorenz@dpschool.io)

Members from the Team for the Digital Product School:

* **[Bruno Teixeira Botelho](https://www.linkedin.com/in/bruno-teixeira-botelho/)**, Product Manager. 
Mail: [bruno.teixeira@dpschool.io](mailto:bruno.teixeira@dpschool.io).

* **[Diksha Shrivastava](https://www.linkedin.com/in/diksha-shrivastava13/)**, AI Research Engineer. 
Mail: [diksharaigarh57@gmail.com](mailto:diksharaigarh57@gmail.com)

Trusted Friend & Advisor through Swan AI development:

* **[Mann Acharya](https://www.linkedin.com/in/mann-acharya/)**, AI Engineer & Full-Stack Developer.
Mail: [mann.compi@gmail.com](mailto:mann.compi@gmail.com)

