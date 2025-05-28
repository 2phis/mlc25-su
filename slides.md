---
theme: ./
layout: cover
class: text-left
# backgroud: '/ATLAS/ATLAS-Logo.png'
authors:  # First author should be the presenter
  - Andrija Sagić: ["'Milutin Bojic' Library", "Europeana"]
meeting: "MLC 25 - Su"
preTitle: "Local AI Agent on Serbian"
aspectRatio: 16/9
---

<!-- <br>
<p style="color:#0FA3B1;">Don't explicitly put title on cover page 🥳 </p>
<p style="color:#0FA3B1;">Put your own logo somewhere </p> -->

<img id="ATLAS" src="/ml-konferencija-logo-light.svg"> </img>

<style scoped>
#ATLAS {
  width: 180px;
  position: absolute;
  right: 3%;
  bottom: 4%;
  /* background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 15%, #146b8c 50%); */
}
</style>

---
layout: pageBar
---

# AI Agents on a laptop?

Local deployment, 100% offline

<div class="grid grid-cols-2 items-center justify-center">
  <h3> Advantages </h3>
  <h3> Dis Advantages </h3>
  <hr><hr>
  <p>Complete control</p>
  <p>High Resources</p>
  <p>Private Data</p>
  <p>Tech Backround</p>
  <p>No Internet Need</p>
  <p>LLM Models Choice</p>
  <p>100% Free</p>
  <p>Limited Support</p>
</div>

---
layout: pageBar
---

# AI Agents Open Source

Some of Open Source AI Agent that support local deployment


<table>
  <tr>
    <td> <img src="/smolagents.png"  alt="1" width=160px></td>
    <td><a href="https://github.com/huggingface/smolagents" target="_blank">github.com/huggingface/smolagents</a></td>
    <td><img src="/agno.svg" alt="3" width=100px></td>
    <td><a href="https://github.com/agno-agi/agno" target="_blank">github.com/agno-agi/agno</a></td>
  </tr>
  <tr>
        <td><img src="/logo_qwen_agent.png" alt="3" width=200px></td>
        <td><a href="https://github.com/QwenLM/Qwen-Agent" target="_blank">github.com/QwenLM/Qwen-Agent</a></td>
        <td><img src="/crew.svg" alt="3" width=140px></td>
        <td><a href="https://github.com/crewAIInc/crewAI" target="_blank">github.com/crewAIInc/crewAI</a></td>
  </tr>
  <tr>
        <td><img src="/oai.svg" alt="3" width=70px float="left"></td>
        <td><a href="https://github.com/openai/openai-agents-python" target="_blank">openai/openai-agents-python</a></td>
        <td><img src="/google.png" alt="Agent Development Kit (ADK)" width=70px float="left"></td>
        <td><a href="https://github.com/google/adk-python" target="_blank">github.com/google/adk-python</a></td>
  </tr>
  <tr>
        <td><img src="/aws.svg" alt="Agent Development Kit (ADK)" width=60px float="left"></td>
        <td><a href="https://github.com/awslabs/agent-squad" target="_blank">github.com/awslabs/agent-squad</a></td>
        <td><img src="/praisonai.png" alt="Agent Development Kit (ADK)" width=120px float="left"></td>
        <td><a href="https://github.com/MervinPraison/PraisonAI" target="_blank">github.com/MervinPraison/PraisonAI</a></td>
  </tr>
</table>

---
layout: pageBar
---

# Test Environment

Hardware and Software

<div class="grid grid-cols-2 gap-5 items-center justify-center">

<div class="col-span-1">

> - <span>GPU - NVIDIA 4060 (8G VRAM)</span>
> - <span>CPU - intel i7 13620H</span>
> - <span>RAM 32G</span>
> - <span>SSD 512G + 1T</span>

</div>
<div class="col-span-1">


<img src="/set.png"/>

</div>

</div>

---
layout: pageBar
---

# Agno 

Example of Agno AGI use

````md magic-move
```python
searcher = Agent(
    model=Ollama(id=gemma3:4b-it-qat, client=OllamaClient(host=http://localhot:11434/v1)),
    name="Searcher",
    role="Searches the top URLs for a topic",
    instructions=[
        "Given a topic, first generate a list of 3 search terms related to that topic.",
        "For each search term, search the web and analyze the results.Return the 10 most relevant URLs to the topic.",
        "You are writing for the New York Times, so the quality of the sources is important.",
    ],
    tools=[DuckDuckGoTools()],
    save_response_to_file=str(urls_file),
    add_datetime_to_instructions=True,
)
```
```python
writer = Agent(
    model=Ollama(id=qwen3:latest, client=OllamaClient(host=http://localhot:11434/v1)),
    name="Writer",
    role="Writes a high-quality article",
    description=(
        "You are a senior writer for the New York Times. Given a topic and a list of URLs, "
        "your goal is to write a high-quality NYT-worthy article on the topic."
    ),
    instructions=[
        f"First read all urls in {urls_file.name} using `get_article_text`."
        "Then write a high-quality NYT-worthy article on the topic."
        "The article should be well-structured, informative, engaging and catchy.",
        "Ensure the length is at least as long as a NYT cover story -- at a minimum, 15 paragraphs.",
        "Ensure you provide a nuanced and balanced opinion, quoting facts where possible.",
        "Focus on clarity, coherence, and overall quality.",
        "Never make up facts or plagiarize. Always provide proper attribution.",
        "Remember: you are writing for the New York Times, so the quality of the article is important.",
    ],
    tools=[Newspaper4kTools(), FileTools(base_dir=urls_file.parent)],
    add_datetime_to_instructions=True,
)
```
````

---
layout: pageBar
---

# Smolagents 

Example of HF Smolagents use

---
layout: pageBar
---

# Language support

LLM support for Serbian

Officialy support

<table>  
  <tr>
        <td><img src="/Qwen_logo.svg" alt="qwen" width=60px></td>
        <td><a href="https://huggingface.co/collections/Qwen/qwen3-67dd247413f0e2e4f653967f" target="_blank">/collections/Qwen/qwen3</a></td>
  </tr>
  <tr>
        <td><img src="/google-logo.svg" alt="google" width=50px></td>
        <td><a href="https://huggingface.co/collections/google/gemma-3-release-67c6c6f89c4f76621268bb6d" target="_blank">/google/gemma-3-release</a></td>
  </tr>
  <tr>
    <td> <img src="/mistral-logo.svg"  alt="mistral" width=40px float=left></td>
    <td><a href="https://huggingface.co/mistralai/Devstral-Small-2505" target="_blank">mistralai/Devstral-Small-2505</a></td>
  </tr>
  <tr>
    <td><img src="/mistral-logo.svg" alt="3" width=40px></td>
    <td><a href="https://huggingface.co/mistralai/Mistral-Small-3.1-24B-Instruct-2503" target="_blank">mistralai/Mistral-Small-3.1-24B-Instruct-2503</a></td>
  </tr>
</table>

---
layout: pageBar
---

# Serbian Agent?

Use AI Agent on Serbian

<div class="grid grid-cols-3 items-center">
  <div v-click>

  ### LLM Engine

  <p><img src="/ollama.svg" alt="ollama" width=80px></p>

  ### Ollama

  </div>
  <div v-click>

  ### Model

  <p><img src="/Qwen_logo.svg" alt="qwen" width=80px></p>

  ### Qwen3-8b

  </div>
  <div v-click>

  ### Model

  <p><img src="/google-logo.svg" alt="google" width=80px></p>

  ### Gemma3-4b

  </div>
</div>

<div v-click>
<hr class="my-1">
<h3 style="float: inline-end">Models fits on GPU NVIDIA 4060 (8G VRAM)</h3>  
</div>
<br>
<div v-click>
  <p>Decent answers on Serbian</p>
  <p>Need improvement to use tools</p>
  <p>Hallucinations</p>
  <p>Possible to ask and get answer on Serbian</p>
</div>

---
layout: pageBar
---

# Tokenizer test

Testing a various tokenizer

<iframe
	src="https://xenova-the-tokenizer-playground.static.hf.space"
	frameborder="0"
	width="100%"
	height="650"
></iframe>

---
layout: pageBar
---

# Language support

Improve Serbian support

## Fine tune

* Datasets ?
*

---
layout: pageBar
---

# 2-D Plotly Examples

Two 2D plots for display

Try to interact with the graphs 🥰

<div grid="~ cols-2 gap-20">

<Transform :scale="0.75">
<PlotlyGraph filePath="Graph/plotly1.json" tickFontSize="18" graphWidth="800"/>
</Transform>

<Transform :scale="0.75">
<PlotlyGraph filePath="Graph/plotly1.json" tickFontSize="18" graphWidth="800"/>
</Transform>

</div>


---
layout: pageBar
---

# 3-D Plotly Examples

Two 3D plots for display

Try to interact with the graphs 🥰

<div grid="~ cols-2 gap-20">

<Transform :scale="0.65">
<PlotlyGraph filePath="Graph/plotly2.json" graphWidth="900"/>
</Transform>

<Transform :scale="0.65">
<PlotlyGraph filePath="Graph/plotly3.json" graphWidth="900"/>
</Transform>

</div>


---
layout: center
class: "text-center"
---

# Thank you

[mail](mailto:andrija.sagic@gmail.com) 

<!-- / [GitHub Repo](https://github.com/2phis) -->


---
layout: pageBar
---
