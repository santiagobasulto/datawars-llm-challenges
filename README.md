# DataWars LLM Candidate Challenge

This repo contains the challenge for DataWars candidates interested in joining our LLM-focused team. The challenge's main objectives is to demonstrate your abilities building LLM-based applications including RAG, Prompting and Fine Tuning. You can use any LLM that you'd like, but we can provide OpenAI API Keys for it if you need them.

The entire challenge is baesed on the YouTube transcripts that you can find in the zip file `transcripts.zip`, that contains the downloaded scripts of two of [Corey Schafer's](https://www.youtube.com/@coreyms) YouTube playlists:

* [Pandas Tutorials](https://www.youtube.com/playlist?list=PL-osiE80TeTsWmV9i9c58mdDCSskIFdDS) (ID `PL-osiE80TeTsWmV9i9c58mdDCSskIFdDS`)
* [Matplotlib Tutorials](https://www.youtube.com/playlist?list=PL-osiE80TeTvipOqomVEeZ1HRrcEvtZB_) (ID `PL-osiE80TeTvipOqomVEeZ1HRrcEvtZB_`).

Below you'll find the challenges and the points associated to each one of them. Good luck!

## Challenges

These challenges shouldn't take you a lot of time. As a matter of fact you'll have a pretty strict timeline to deliver them. Make sure you understand what's the required output of your challenge. Sometimes it'll be real code, sometimes it'll be just a document describing how you'd resolve it. Let's get started!

### 1. RAG Chunking (5 points)

Suppose you want to build an LLM agent that can help DataWars users that are learning pandas. Whenever a user asks a question, we'll reference one of Corey's answers from the playlists. Our task will be to build a RAG-powered LLM agent that uses Corey's video transcripts to answer questions for users and point them to the right location in the video. For example, If the user asks *"How can I group a DataFrames in Pandas?"*, we want to answer the question using the video [Python Pandas Tutorial (Part 8): Grouping and Aggregating](https://www.youtube.com/watch?v=txMdrV1Ut64&t=888s) at time 14:50.

For this, we'll use our well known and beloved Vector Store database and just query by similarty. But we have a problem! We need to create chunks of the entire scripts to make sure we don't have huge costs for processing large volumes of tokens.

So, your first challenge is to decide the chunking strategy/algorithm we'll use to build our Vector database.

Write a python script that can be parametrized and will chunk a video. For example: `python chunks.py --transcript transcirpt.json --video-metadata metadata.json`. You have full liberty of how this script works or what it receives. The output should be another JSON file that contains the chunks information in WHATEVER format you prefer. For example, this is valid:

```json
[{
  "chunk_id": "fb8c2",
  "text": "...",
}, {
  "chunk_id": "38fb1",
  "text": "...",
}, ]
```

But you could add ANY information that you think it's relevant.

You can use ANY frameworks or tools that you prefer: LlamaIndex, Ragas, etc. It's up to you. The **main objective of this challenge** is to understand what strategy of chunking you'd be using. Are you just spliting by chunk length? Are you using similartiy? What do you choose as min/max chunk size and why? Etc.

#### Output of the challenge

* Working script that chunks the video transcripts. Some sample JSON files of chunks that you'll generate
* A document (can be just the README in the repo) outlining the strategy you chose for chunking, the tools, the challenges you faced, etc.

### 2. Evaluation metrics (3 points)

Now it's time to evaluate if your chunking strategies are good and up to par. In this case, we won't require you to write any code, although if you do it you'll have a lot of extra points.

Create a document (it can be a markdown file in the repo) outlining the way you'd evaluate the "performance" of your chunking: in terms of relevancy, correctness, costs, etc

If you want to implement some real code, that'd be amazing and would give you a lot of extra points, but it's not required.

Note: some people will combine Challenge 1 (chunking) and Challenge 2 (evaluation) and that'd be the ideal process, although it's not required.

### 3. Create the agent (2 points)

Now it's time to define the prompts and create the agent that will assist the student. To do so, cretate a document outlining the steps you'd take to create such agent, and include the precise Prompts you'd use. You don't need to build the final agent, as we don't want you to waste time setting up a Vector search database. Although if you have a working agent it'd also give you a lot of extra points.

In this case we want to evaluate your understanding of RAG applications and your prompting abilities.

## Final words

Make sure you read carefully all the instructions. The ideal way to turn this assignment in is to use a single Github repository with clear instructions (for us) of how you have structured and how to run it. We will evaluate how tidy and organized you are as well.

Best of luck!
