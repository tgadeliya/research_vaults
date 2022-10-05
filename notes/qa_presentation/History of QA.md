
First mention of QA systems we can find in 1960th.  In multile sources I found, that [[Baseball]] is the first question answering system, where we supply answer in natural language and system tries to find answer in stored data. We take a short look at this system.

## Baseball
As I think you guess, this system focus only on BASEBALL.
At the beginning, I want to show how long ago that was. Try to imagine, that questions, were supplied to the system by punched cards
[[Image of punched cards]]
I think that small detail provide enough evidence about the history.

this program written in IPL-V language, which uses list structures to  to represent information.
[[Image og IPL-V language code]]

#### Structure
1) Input
Questions in natural language.
Restrictions:
- single clause (need to be simple for syntactic analysis)
- No logical connectives (or, and, not)
- No questions about sequential facts (How many games Red Sox won in a row?)

2) Linguistic part
	- Question read-in
	- dictionary look-up
	- syntactic analysis
	- content analysis
Example of stored data structures:
![[Screenshot 2021-12-05 at 16.06.25.png]]

3) Processing part
	- Processor  - search routine that match  each parrt of given Data structure
	- Responder - 

#### What to pay attention to
- Close-book QA system
- Restrictions to QA form due to syntactical tools analysis ограниченность
- Data should be properly organised to allow serach over them
- 2 part structure:
	- First reads answer and creates representation in some internal types 
	- Second use representation to  find appropriate answer
- Answer is not presented in natural language


This system was biuld in 1961, but as Simmons (1965) mention in his survey [[Answering English Question by Computer]]  that no fewer than 15 systems were implementeed at the time of this survey preparation.


## (Woods, 1973) [[LUNAR]] (close-domain? factoid? question)
This systems were designed to enable effective acces to information about chemical analysis of lunar rock and soil composition that was accumulating as a result of the Appollo moon mission. System were demonstrated 

TODO: Add one slide description of Carnap notion of truth condition's(1964)

This system allowed to ask questios, compute some statistics: ratios, averages, print selected subets of objects.
- Changes in database

### What to pay attention to
- Similar to BASEBALL idea
- Inspiration from Philosophy of Language 


#### QA as interface
Have you see some similarities (not technical. but in idea space) between this systems? 
As many researchers emphasize, BASEBALL and LUNAR systems use structured data to answer questions. In other words, this is interface to databases ("natural language front-end to databases").
In this fashion, multiple works in 1970 were presented: PLANES, LADDER, TEAM
TODO: Few words about every work from     Copestake and Sparck Jones (1990)

First system shows us very important property of QA. This is a way to communicate. Human-computer interface (or human - software) use this approach: it is  structured like query and answer. As  Hirschmann called them in [[Natural language question answering: the view from here]] paper, ""

#### QA in machine-human interaction
Another are of research was QA in dialogues. Everyone heard about Alan Turing Test (1950) as conversational understanding test for machine intelligence.
Examples of that systems: SHRDLU (Winograd), GUS

#### QA as tool in story comprehension
From my point of view, the bridge or maybe "path" that guided researchers to modern QA systems (by word modern I assume tredition that longing 20-30 years by now).
~переход от того что в нашей жизни вопросы очень важны и они служат для проверки понимания каких то вещей Школа университет тесты и так далее
So questions is effective way to test someone knowledge or understanding. In this part I will describe QA as mean of examining natural language understanding systems.
Notable early work is  QUALM
TODO: Some words about QUALM

What to pay attention:
- This work moved from earlier approach that separate question and data used to answer that question (unstructued (natural language) and structured database)

In 1980-th there were some works in this direction, more in psychology 
TODO: Kintsch (1998), but problems with evaluation or maybe rephrasing "problem on aggrement how to evaluate systems in research community" 

I put emphasize on this type of systems, because solution of that problem shaped QA development for years as you will shortly see. 

Here we return to understading the role of Information Retrieval in Question Answering

I think this section undestanding lying in our everyday usage of search systems and their modification 
TODO: Add screnshots of Google search showing things below.

Similarity IR and modern QA:
- User form query to find an answer
- Operate on unstructued texts

Diff:
- IR returns documents, QA returns answer
- In IR query shouldn't be formed as correct syntactic form (remember your Google search entries), but in QA we assume this correctness.

IR and QA relevance:
- IR can return passages, not the whole documents. And we can make this passages smaller and smaller, ending in sentence or phrase. So QA from this perspective is a passage retrieval. I will add, that mostly depends on domain and function. The closest to that is factoid questions when we return some person, place, date, etc.
- IR developed evaluation protocols, which can be effectively acquired by QA

## TREC
Here I think we can talk about milestone point of QA history. TREC-8 conference in 1999
instroduced Question Answering track in the Text Retrieval onference

A 2010 study estimated that "without TREC, U.S. Internet users would have spent up to 3.15 billion additional hours using web search engines between 1999 and 2009."[[](https://en.wikipedia.org/wiki/Text_Retrieval_Conference#cite_note-2010.Economic.Impact-1)









