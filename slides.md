---
theme: ./
transition: fade
layout: cover
class: text-left
# backgroud: '/ATLAS/ATLAS-Logo.png'
authors:  # First author should be the presenter
  - Andrija Sagić: ["'Milutin Bojic' Library", "Europeana"]
meeting: "MLC 25 - Su"
preTitle: "Local AI Agent on Serbian"
---

<img id="mlc" src="/ml-konferencija-logo-light.svg"> </img>

<style scoped>
#mlc {
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
reasoning_agent = Agent(
    name="Reasoning Agent",
    model=Ollama(id="qwen3:latest"),
    reasoning=True,
    tools=[ReasoningTools(add_instructions=True)],
    instructions=[
        "Always use tables to display data."
        "Answer always on Serbian language."
        ],
    storage=SqliteStorage(
        table_name="reasoning_agent",
        db_file=agent_storage,
        auto_upgrade_schema=True,
        ),
    add_datetime_to_instructions=True,
    add_history_to_messages=True,
    num_history_responses=5,
    markdown=True,
)
```
```python
arxiv_agent = Agent(
    name="Arxiv Agent",
    model=Ollama(id="qwen3:latest"),
    tools=[ArxivTools()],
    instructions=[
        "Always use tables to display data and cite arxiv sources."
        "Odgovori uvek na srpskom jeziku."
        ],
    storage=SqliteStorage(table_name="arxiv_agent", db_file=agent_storage),
    add_datetime_to_instructions=True,
    add_history_to_messages=True,
    num_history_responses=5,
    markdown=True,
```
````


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

One of the possible solutions is <span v-mark.underline.blue>fine tuning</span> to improve LLM support for Serbian.

<div v-click>

* Datasets ?
* Models
* Methods
* Hardware

</div>
<div v-click class="m4">

### Testing

</div>
<div v-click>
Testing the Gemma3-4b model with synthetic instruct dataset (Q/A) on Serbian, resulted with this model:
</div>
<div v-click>
<a href="https://huggingface.co/Sagicc/gemma-3-4b-it-sr" target="_blank">huggingface.co/Sagicc/gemma-3-4b-it-sr</a>
</div>

<div v-click class="m4">

### Problems

</div>
<div v-click>

* lose Agent use option
* short answers

</div>

---
layout: pageBar
---

# Next

Further development

<div v-click>

<img src="/2phis.svg" width=150px>

</div>

<div v-click class="m4">

### SLM Lab

* Improve support for Serbian
* Create a datasets
* Lower token generation for Reasoning but with better results
* Experiment with new discoveries  

</div>

---
layout: center
class: "text-center"
---

# Thank you

[mail](mailto:andrija.sagic@gmail.com) 

<!-- / [GitHub Repo](https://github.com/2phis) -->
