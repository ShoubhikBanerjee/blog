---
title: "Practical Advice for Building AI Agents: Lessons from the GAIA Benchmark Challenge"
description: "A comprehensive exploration of building AI agents through the GAIA benchmark
challenge, comparing reasoning vs non-reasoning models, tool selection strategies, and practical
 insights for agent architecture design."
date: 2025-10-28T00:51:46.460656+05:30
tags: ["AI Agents", "GAIA Benchmark", "Machine Learning", "LangGraph", "GPT-4o", "GPT-5", "Gemini", "Tool Usage", "Prompt Engineering", "Benchmarking", "Observability", "ReACT Architecture"]
categories: ["Artificial Intelligence", "Machine Learning", "Agent Development"]
image: "https://cdn-uploads.huggingface.co/production/uploads/62d1687ee748e12e04e042e8/ScCZb2zq4EGhUOJZnofYz.png"
math: false
license: "NA"
hidden: false
comments: true
draft: false
author: "Shoubhik Banerjee"
---

# 🚀 Practical Advice for Building AI Agents: Lessons from the GAIA Benchmark Challenge

![GAIA Benchmark Challenge](https://cdn-uploads.huggingface.co/production/uploads/62d1687ee748e12e04e042e8/ScCZb2zq4EGhUOJZnofYz.png)
*Distribution of cognitive abilities required in the GAIA benchmark*

Hello! This is my first blog post on Hugging Face. My name is Charlie, and I'll be using this
space to share my experience solving the GAIA benchmark challenge from Hugging Face's Agents
course—what I learned along the way, and a few insights that I think are useful for AI agent design in general.

The main goal of this article is to walk through the technical decisions I had to make: the
concepts I revisited, the trade-offs I encountered, and the new ideas I had to explore. My
objective wasn't to achieve a perfect solution, but rather to put into practice some of the
theoretical knowledge I had accumulated and see how it held up in a real challenge.

I'll focus more on the **why** than the **how**. While I'll explain my process in as much detail
 as needed, this is not intended to be a LangGraph tutorial. Instead, think of it as a "lessons
learned for building better agents" post—zooming out from the implementation details to
highlight the reasoning behind them.

---

## ⚡ The Biggest Lessons

Adding this as a quick summary of the findings:

1. **Choosing the most powerful model does not always lead to the best results**
2. **Reasoning models can be a game changer at certain use cases, but sometimes non-reasoning
ones show better results in simple tasks**
3. **Your tools definition and behaviors can boost or kill the overall performance of your
agent**
4. **Every model has its own style to solve tasks, knowing this can help you on using the most
out of each model**

---

## 📊 About the Challenge

Some of you might have probably done the [Hugging Face's Agents
Course](https://huggingface.co/learn/cookbook/agents), but if you don't, I encourage you to give
 it a try. This course presents a final challenge consisting on creating an AI agent that could
solve questions present in the GAIA benchmark. For fairness to the challenge, I'm not going to
disclose the full code or the prompt used in this post.

To solve the challenge I had to understand what I was facing, so I started reading the GAIA
benchmark paper: [GAIA: A benchmark for General AI
Assistants](https://arxiv.org/abs/2311.12983). I'm not going to deep dive in it, but I'll remark
 the most relevant points for this problem:

- **GAIA presents auto-contained questions** that require a certain level of understanding,
reasoning and in some cases capabilities to read files, search information, perform calculations
 or to write code to be solved
- **Questions presented are easy in general**, they can be easily answered by a human and
provide a clear ground-truth against AI
- **It is focused on the final answer**, it does not evaluate how the agent got there, but
whether the answer is right or wrong

Good! This actually gives us valuable insights to proceed: the kind of cognitive abilities our
AI agent should have, and the extended capabilities given by tools.

With that in mind, I decided to frame my process around five main phases:

1. Selecting the best foundation model for the task 2. Designing a simple agent architecture
3. Choosing the right tools to face the challenge 4. Implementing the solution
5. Evaluating results and identifying improvements

With this roadmap in place, the first question I had to answer was: which foundation model
should I rely on to tackle GAIA? That choice would shape everything else that followed.

--- 
## 🧠 Selecting the Foundation Model

Selecting the right foundation model for a problem is far from trivial. For this challenge, I
considered a few guiding criteria:

- **Performance on the required cognitive tasks**
- **Cost**
- **Inference speed**

Other aspects such as security, privacy, or infrastructure constraints could also play a role in
 real-world deployments, but for the scope of this experiment I set them aside. To approach
GAIA, we need a broad basis to compare models' cognitive capabilities. The core skills required are:

- Reasoning
- Multimodality
- Code generation
- Tool usage

A natural first step is to look at established benchmarks, since they provide a general snapshot
 of model capabilities. But it's important to keep perspective: benchmarks measure performance
in controlled settings and don't guarantee superiority in real-world tasks.

**Here comes the little twist:**

As I stated at the beginning of this post, my objective here was not nailing the challenge, but
to put in practice some ideas, hence, I'm going to compare two types of foundation models:
[reasoning-oriented models](https://openai.com/o1/) vs non-reasoning models. Why? Well. I really
 want to put in perspective how much using one technique versus another turns out in a real scenario.

Below a table with a summary of the benchmarks I used to compare the models' capabilities:

| Benchmark | GPT-5 | Gemini 2.5 Pro | Grok 4 | Claude Opus 4.1 | Llama 4 Maverick | GPT-4o |
Gemini-2.5-flash |
|-----------|-------|----------------|--------|------------------|-------------------|--------|-
------------------|
| ARC AGI | 9.9 | 4.9 | **15.9** | 8.6 | 0 | 0 | 16 |
| MATH | 93.4 | 85.8 | 90.6 | 78.2 | 25.2 | - | - |
| MMMU | **84.2** | 82 | - | 77.1 | 73.4 | 70.7 | 79.7 |
| SWE-bench | **74.9** | 67.2 | - | 74.5 | 21.1 | 21.62 | 28.73 |
| MMLU | 87 | 86 | 87 | **89.5** | 80.5 | 77.9 | - |
| TAU-bench | 81.1 | - | - | **82.4** | 71 | - | - |
| Input price (1M tokens) | 1.25 | 1.25 | 3 | 15 | 0.19-0.49 | - | 0.30 |
| Output price (1M tokens) | 10 | 10 | 15 | 75 | 0.19-0.49 | - | 2.50 |
| Context window | 400k | 1M | 256k | 200k | 10M | - | - |

Let's analyze the three models that top at least one of the considered benchmarks:

### 🔥 GPT-5

This is a reasoning-oriented model created by OpenAI and launched recently compared to other
models in the list. GPT-5 introduced some changes in the implementation according to [OpenAI's
developer documentation](https://platform.openai.com/docs/). But the most important one is that
unlike GPT-4o (for instance) it is a reasoning model by default, more on the line of o1 and o3.
We can see it excels on multimodality (MMMU) and code generation (SWE-bench), and despite not
being the best in ARC AGI it is pretty good on all the benchmarks, considering also tool-usage
(TAU-bench). Strong candidate.

### ⚡ Grok 4

This one absolutely beats ARC AGI as the best model at reasoning in the market, additionally
being pretty solid at MATH and language understanding (MMLU). However, there is a consideration.
 The input pricing is not too far from GPT-5's but it is actually more expensive. However,
there's not much information on the performance on the other benchmarks.

### 🤖 Claude Opus 4.1

Anthropic's most advanced model at the time of writing. It leads in language understanding
(MMLU) and tool usage (TAU-bench), and comes very close to GPT-5 in code generation (SWE-bench),
 making it a strong technical candidate. The main drawback is cost—particularly on output
tokens, which are 7.5× more expensive than GPT-5 and 5× more expensive than Grok 4.

Before I said I would use a reasoning-oriented model vs a non-reasoning one. So for the
comparison, **I'll go for GPT-5 and GPT-4o.** Still, as you'll see in the next sections, there's
 an interesting twist coming ;)

Also, as we expect to process audio files in the challenge, I decided to opt for gpt-4o-audio-preview.

--- 
## 🏗️ Setting Up the Agent Architectur

So, after the selection of the cognitive engine for our agent, I need to choose the overall
architecture. Anthropic launched a blog post discussing about some patterns to [build effective
agent workflows](https://www.anthropic.com/research/building-effective-agents) I recommend you
to read. When solving problems with AI agents in mind, we need to consider many aspects such as
the expected tasks to solve, whether a single agent can solve the problem or a multi-agent
approach could present better performance.

For the sake of simplicity, I decided to go for a simple ReACT-like architecture using only one
agent. If you want to learn more about how it works you can read the original [Yao's
paper](https://arxiv.org/abs/2210.03629).

To implement in code the agent I went for LangGraph due to its simplicity and power. Thus, I
generated the graph structure for the agent, considering two nodes: the agent itself and the tools.

![Agent Architecture](https://cdn-uploads.huggingface.co/production/uploads/62d1687ee748e12e04e042e8/SARD6lfTyPR-UqDOHnE9S.png)
*Simple ReACT-like agent architecture using LangGraph*

--- 
## 🛠️ Prompt Engineerin

In general, I did not an extensive craft of my system prompt for this first attempt, though it
is highly recommended for you to solve the challenge. I just tried with a simple prompt stating
the nature of the tasks, the expected behavior of the agent, the format for the answers and the
tools at hand. It is important to iterate over different prompts and measure the impact using
tools such as Langfuse or MLflow to select the best one.

### 🔧 The Tools Used

An important component for agentic AI architectures are the tools you implement. In this case,
just as I did with the model election, I listed the actions that the agent should have as
capabilities to answer the questions in the benchmark.

As we can see, web browsing is one of the most common abilities required to solve the questions,
 followed by coding. Also, we know that we need to read files to support multimodality in our
agent. However, after a glance in the questions contained in the benchmark, we see more
capabilities are going to be needed, such as YouTube video processing.

There are diverse options to add web-browsing capabilities to the agent, we can directly
implement calls to Bing or the Google APIs for example, but in this case, I chose **Tavily** as
my service for web-browsing, the main reason behind this is the simplicity of integration.

```python
@tool def web_search(query : str) -> str:
    """Provides web search to retrieve information outside of LLMs knowledge """
    response = tavily_client.search(query, include_answer=True) return response["answer"]
```

Some questions require youtube video processing to answer visual questions. This tool is a
little more tricky, as it could be approached from different ways, and cannot be "browsed" by
Tavily, which means we require an additional component.

At the end, after evaluating carefully, I decided to go for the simpler option as I could have a
 baseline to identify potential improvements later.

```python
@tool def youtube_search(link : str) -> str:
    """Search for youtube videos. Input must be only the youtube video URL """
    transcript = "" loader = YoutubeLoaderDL.from_youtube_url(
        link, add_video_info=True )
    documents = loader.load() video_metadata = documents[0].metadata
    video_id = video_metadata["source"] ytt_api = YouTubeTranscriptApi()
    try:
        fetched_transcript = ytt_api.fetch(video_id) for snippet in fetched_transcript:
            transcript = transcript + " " + snippet.text except TranscriptsDisabled:
        transcript = "No description of video content available" return transcript
```

### 💻 Code Writing and Execution Tool

One of the most important abilities for our agent is the one of writing code and executing it
safely. Actually, there is a complete guide here in Hugging Face about safe code execution for
AI agents that you can visit here for additional details: [Secure code
execution](https://huggingface.co/learn/cookbook/en/agent_code_execution).

I decided to go for **E2B** as the sandbox for code execution. Also, there is relevant to note
that GAIA questions would need code execution in two manners:

- A question that provides explicitly a Python file to execute
- A question that could be answered by writing code, so the LLM produces this by itself

```python
@tool def python_code_write_and_execute(query : str) -> str:
    """Let's the LLM to write and execute code if needed for a task """
    messages = [ SystemMessage(prompt_coding),
        HumanMessage(query) ]
    response = assistant_model.invoke(messages) code = response.content
    code = extract_python(code) try:
        if code:
            with Sandbox() as sandbox:
                execution = sandbox.run_code(code) print(execution)
                result = execution.logs.stdout[0] return result
    except Exception as e:
        print(e) return "There was an error while trying to execute code"
```

### 🎨 Adding Compatibility with Multiple Modalities

Finally, the agent must be compatible with different modalities. In general, GAIA paper
establishes that the agent must be able to process Python code files, PDF, excel, audio, images
and video. At the beginning of the article I stated the use of gpt-4o-audio as a model to accept the audio inputs.

For those wondering about how the state for my agent is defined, let me explain a bit. My
assistant had three things to keep track of: the messages list, and to support multimodality I
decided to add a filename and the extension of the uploaded files.

```python
class AssistantState(TypedDict):
    messages: Annotated[list[AnyMessage], add_messages]
    filename : str file_extension : str
```

### 📊 Evaluation and Comparison in Langfuse of Our Two Models

I reserved many of the different findings of the mini-project to this section. So I could
explain them with detail and elaborate conclusions from here. At the beginning of the post it
was defined the use of two LLMs to compare: GPT-5 and GPT-4o.

There is an option for the configuration in LangGraph when running a graph called
**recursion_limit** which controls the depth of the recursion allowed for the graph to execute,
for this experiment, the value for that parameter was 10. If this limit is reached, then the
graph fails and prevents an infinite execution. Well, this was exactly the problem in my case.
It seems the reasoning capabilities of GPT-5 led the graph to execute multiple times, further
than my recursion_limit. Never reaching an output.

![Graph Execution Failure](https://cdn-uploads.huggingface.co/production/uploads/62d1687ee748e12e04e042e8/brNXk073IHX6XF94CCo-L.png)
*Graph execution failure due to recursion limit*

From here, I decided to lower the **reasoning_effort** to "minimal" which according to some of
the documentation also could make the model to work more like a non-reasoning one, and even
though this let the graph finish almost all the tasks, it was also more expensive (around 2x per
 question), had a worse latency (around 3.5x times) and in many cases, produced more steps than
the needed to solve a question.

![Performance Comparison](https://cdn-uploads.huggingface.co/production/uploads/62d1687ee748e12e04e042e8/a8KoGiOE6q-ZGWGX3ehZv.png)
*Performance comparison between GPT-4o and GPT-5*

This is truly insightful, as for some cases we might be tempted to use the best model out there,
 or we can think that a given task required a level of reasoning that actually is not needed.
For the case of GAIA, the questions are very straightforward and require good instruction
following capabilities and very light reasoning than other types of tasks. Hence, a
non-reasoning model could be a better fit here.

Following that comment, I decided to try with non-reasoning models: **GPT-4o** and **Gemini 2.5 Flash**.

In the table below general dimensions for comparison can be seen. For reference, the challenge
evaluates the agents with 20 different questions.

| Category | GPT-4o | Gemini 2.5 Flash |
|----------|---------|-------------------|
| Total latency (s) | 103.28 | 414.79 |
| p95 latency (s) | 70.18 | 153.5 |
| Price for all tasks (USD) | 0.079 | 0.19 |
| Avg price per task (USD) | 0.0043 | 0.0095 |
| Total tokens used | 27,611 | 106,019 |
| Avg tokens per task | 1,380 | 5,300 |
| Completed answers (%) | 90 | 80 |
| Accuracy (right answers) (%) | 20 | 40 |
| Effectivity - Right answers over total responses (%) | 22 | 50 |
| Most called tool | web_search | python_code_execution |

As we can see, GPT-4o seems to be the fastest and cheaper model. We can also see that Gemini 2.5
 Flash got twice more right answers than GPT-4o and in overall is more effective. Given the rest
 of comparison categories is it worth the trade-off? Let's see.

#### 🔍 Comparing How Each Agent Decided to Proceed on the Same Questions

Part of the things I wanted to understand on this challenge was how different models would
behave to the same input, prompt and tools given, to understand better how each approached a
problem, just like humans do.

**Question: The attached Excel file contains the sales of menu items for a local fast-food
chain. What were the total sales that the chain made from food (not including drinks)?**

- **GPT-4o**: This model read the file and decided to redact all its content as plain text. And
choose to solve all by itself **without calling tools**. The model did the math but it failed
the answer (even though it was close).

- **Gemini 2.5 Flash**: Gemini decided to make a tool call to solve this:
**python_code_executer**. In general, Gemini decided to write Python code to read the Excel
file, convert it into a pandas dataframe and execute the operations needed to answer. This
approached led to the right answer to this question, using more time and tokens to solve it than
 GPT-4o. Gemini wins here.

This insight is truly important and unveiling, as it is a good example that when working with
agents the model is not the only thing we should care about. Tools are equally important. We
need to audit them, test them and ensure the behavior is the one we expect.

### 💡 Final Conclusions

Many important lessons have been discussed during the whole post, for this section, let me make
a quick summary on this and future directions that I could follow to improve my agent's performance.

- **Selecting the right model for the task can be challenging.** You can start by comparing
benchmarks and other characteristics that are important trade-offs for your use case, but
remember that these will be only general guides, the only way to make sure you're choosing the
right one is by testing on your use case and comparing results.

- **Each model has a tendency to solve problems in a unique way**, if you know these nuances it
might be easier to choose each in a case where it is better suited.

- **Creating or integrating the right tools is as important as your model selection**, and in
many cases you could use a less powerful model and make it shine with the right tools.

- **You must evaluate your agent performance considering what's important to you**: cost,
latency, correctness, etc. For your domain you should select or build mini-benchmarks to
evaluate how well your agent is doing.

- **Never underestimate the power of observability tools.** In this case I used Langfuse, and
some weird behaviors would not have been spotted without its observability capabilities.

- **Evaluating your tools might become as important as evaluating the final performance of your
agent.**

**Directions to improve**

Finally, about some things that I could try in the future after this 15-hours adventure are the following:

1. Iterate more over the system prompt, adapting it to the recommendations from each lab and
measuring the impact using an observability tool.
2. Compare the performance on web search and code execution tools between my open implementation
 and the official tools given by OpenAI and Gemini Platforms, to understand whether the results
can be better if sticking to the official integrations.

Thanks for reading so far! It was really great to solve the challenge, register my observations
and writing this post for you. I hope you can find something interesting here and we can keep
talking. If you have experience in building agents and have faced these or other challenges and
want to discuss feel free to leave a comment.

Have a great day!

--- 
## 🙌 Credits

*Originally posted at: https://huggingface.co/blog/hetline/lessons-learned-on-gaia-agents*

--- 
## 🏁 Conclusion

This exploration of the GAIA benchmark challenge provides valuable insights into the practical
considerations of building AI agents. The key takeaways demonstrate that success in agent
development goes beyond simply choosing the most powerful model—it requires thoughtful
consideration of the specific use case, careful tool selection and implementation, and thorough
evaluation of different approaches.

The comparison between reasoning-oriented and non-reasoning models reveals that complexity isn't
 always better, especially for straightforward tasks where simpler models can achieve better
results with lower latency and cost. The importance of observability tools like Langfuse cannot
be overstated, as they provide crucial insights into agent behavior that would otherwise go unnoticed.

Most importantly, this work highlights that building effective AI agents is a holistic endeavor
where model selection, tool design, prompt engineering, and evaluation methodology all play
equally critical roles in determining success.

--- 
_#AIAGENTS #GAIA #HUGGINGFACE #MACHINELEARNING #LANGGRAPH #PROMPT_ENGINEERING #BENCHMARKING
#OBSERVABILITY_

