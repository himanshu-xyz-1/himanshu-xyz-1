<h1 align="center">
  <img src="https://readme-typing-svg.demolab.com/?lines=Hi,+I'm+Himanshu+Joshi+👋;AI+Systems+%26+Applied+LLM+Engineer+⚡;Building+Autonomous+AI+Agents+🛠️;Local+LLMs+on+NVIDIA+CUDA+🚀;High-Throughput+Streaming+%26+Structured+Pipelines+🧠&font=Fira+Code&center=true&width=620&height=50&color=38bdf8&vCenter=true&size=22&pause=1000&background=00000000" alt="Himanshu Joshi" />
</h1>

<p align="center">
  <a href="https://x.com/" target="_blank">
    <img src="https://img.shields.io/badge/X-(formerly_Twitter)-000000?style=for-the-badge&logo=x&logoColor=white" alt="X" />
  </a>
  &nbsp;
  <a href="mailto:himanshu.zyx7@gmail.com">
    <img src="https://img.shields.io/badge/Email-Contact_Me-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email" />
  </a>
  &nbsp;
  <a href="https://github.com/himanshu-xyz-1">
    <img src="https://img.shields.io/badge/GitHub-Profile-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub" />
  </a>
  &nbsp;
  <img src="https://img.shields.io/badge/Focus-AI_Agents_%26_LLM_Systems-8B5CF6?style=for-the-badge" alt="Focus" />
</p>

---

### 🖥️ Autonomous Agent in Action (Live Execution Trace)

```bash
himanshu@arch-box:~$ python -m agent.run --model llama3.2:3b --tools gpu_stat,sys_diag,file_ops

[SYSTEM] Initializing CUDA backend (NVIDIA GeForce RTX 3060 12GB VRAM)... OK.
[SYSTEM] Loading Llama 3.2 (3B Q4_K_M) into local VRAM... Allocated: 2.2GB / 12GB.
[AGENT]  Autonomous ReAct Controller listening on local pipe...

>> User: "Inspect GPU thermals, diagnose active system memory, and return a validated report."
>> Agent Thinking: "User requires real-time hardware telemetry. Invoking tool: [get_gpu_status]"
>> Tool Output: { "device": "RTX 3060", "temp_c": 48, "vram_used_mb": 2240, "vram_total_mb": 12288 }

>> Agent Streaming Output (Structured Pydantic JSON):
{
  "status": "HEALTHY",
  "hardware": {
    "gpu": "NVIDIA GeForce RTX 3060",
    "temperature_celsius": 48,
    "vram_utilization_pct": 18.2
  },
  "diagnostics": "All system sensors optimal. Inference running entirely in GPU VRAM with zero CPU offload."
}
```

---

### ⚡ System Architecture: How I Build Autonomous AI Workflows

```mermaid
flowchart TD
    User([👤 User Prompt / API Request]) --> Controller[🧠 ReAct Agent Controller]
    Controller --> LocalLLM[🤖 Local LLM Engine - Llama 3.2 / Ollama]
    
    LocalLLM --> Decision{Need External Context or Tool?}
    
    Decision -- "Tool Call Required" --> Dispatcher[🛠️ Tool Dispatcher]
    Dispatcher --> SystemDiag[System & Hardware Telemetry: nvidia-smi]
    Dispatcher --> SandboxExec[Linux Command Runner & File System]
    Dispatcher --> VectorDB[Vector Search / RAG Database]
    
    SystemDiag --> Observability[Real-time Observation Context]
    SandboxExec --> Observability
    VectorDB --> Observability
    Observability --> Controller
    
    Decision -- "Direct Response" --> Streamer[⚡ Low-Latency Token Streamer: flush=True]
    Streamer --> Validator[🛡️ Pydantic Structured Schema Validator]
    Validator --> FinalOutput([🎯 Production-Ready Output])

    style Controller fill:#1e293b,stroke:#38bdf8,stroke-width:2px,color:#fff
    style LocalLLM fill:#1e293b,stroke:#8b5cf6,stroke-width:2px,color:#fff
    style Validator fill:#1e293b,stroke:#10b981,stroke-width:2px,color:#fff
    style FinalOutput fill:#0f172a,stroke:#38bdf8,stroke-width:2px,color:#fff
```

---

### 🧰 Tech Stack & Systems Engineering

<table>
  <tr>
    <td width="25%" valign="top"><b>🤖 AI & Models</b></td>
    <td width="75%">
      <code>Llama 3.2</code> • <code>Ollama</code> • <code>Hugging Face</code> • <code>Token Streaming</code> • <code>Function / Tool Calling</code> • <code>vLLM</code>
    </td>
  </tr>
  <tr>
    <td width="25%" valign="top"><b>🛠️ Agents & Backend</b></td>
    <td width="75%">
      <code>Python 3.12+</code> • <code>FastAPI</code> • <code>Pydantic Structured Outputs</code> • <code>ReAct Loops</code> • <code>AsyncIO</code>
    </td>
  </tr>
  <tr>
    <td width="25%" valign="top"><b>💾 Data & Retrieval</b></td>
    <td width="75%">
      <code>Vector Databases (Chroma / Qdrant)</code> • <code>RAG Pipelines</code> • <code>Embeddings</code> • <code>JSON Data Parsing</code>
    </td>
  </tr>
  <tr>
    <td width="25%" valign="top"><b>🐧 Infrastructure</b></td>
    <td width="75%">
      <code>Arch Linux</code> • <code>NVIDIA CUDA</code> • <code>Hyprland</code> • <code>Wayland</code> • <code>Bash Automation</code> • <code>Git</code>
    </td>
  </tr>
</table>

---

### 📂 Deep-Dive Competencies & Systems (Click to Expand)

<details>
  <summary><b>▶ 🧠 1. Autonomous Agents & Tool Calling Architecture</b></summary>
  <br>
  <ul>
    <li><b>ReAct Loops:</b> Implementing iterative reasoning where the LLM dynamically chooses when to speak and when to call external Python functions.</li>
    <li><b>Tool Dispatching:</b> Passing strongly typed callable signatures to models, intercepting arguments, and returning verified outputs to conversation history.</li>
    <li><b>Self-Healing Workflows:</b> Automatic retry loops and error correction when API calls or schemas produce unexpected outputs.</li>
  </ul>
</details>

<details>
  <summary><b>▶ ⚡ 2. Local GPU Inference & Hardware Optimization</b></summary>
  <br>
  <ul>
    <li><b>Hardware Stack:</b> Dedicated Linux workstation powered by an <b>NVIDIA GeForce RTX 3060 (12GB GDDR6 VRAM)</b> running CUDA.</li>
    <li><b>Throughput:</b> Running quantized 3B models at <b>~100+ tokens/sec</b> and 8B models at <b>~50 tokens/sec</b> with zero CPU RAM offloading.</li>
    <li><b>Buffer Management:</b> Building real-time streaming interfaces using unbuffered IO (<code>flush=True</code>) for low-latency terminal and API interactions.</li>
  </ul>
</details>

<details>
  <summary><b>▶ 🛡️ 3. Structured Data Extraction & Schema Validation</b></summary>
  <br>
  <ul>
    <li><b>Pydantic Schemas:</b> Enforcing strict type safety on LLM outputs to eliminate unstructured hallucinations in production pipelines.</li>
    <li><b>Server Diagnostic Pipelines:</b> Parsing messy, unformatted system crash dumps and server logs into clean, actionable JSON payloads.</li>
    <li><b>Stateless vs Stateful Memory:</b> Architecting conversation buffers with context pruning to prevent token overflow.</li>
  </ul>
</details>

---

### 📊 Real-Time GitHub Telemetry

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=himanshu-xyz-1&show_icons=true&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=38bdf8&icon_color=8b5cf6&text_color=94a3b8" width="48%" alt="GitHub Stats" />
  &nbsp;
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=himanshu-xyz-1&layout=compact&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=38bdf8&text_color=94a3b8" width="48%" alt="Top Languages" />
</p>

<p align="center">
  <img src="https://github-readme-streak-stats.herokuapp.com/?user=himanshu-xyz-1&theme=tokyonight&hide_border=true&background=0d1117&ring=38bdf8&fire=8b5cf6&currStreakLabel=38bdf8" width="97%" alt="GitHub Streak" />
</p>

---

### 🎯 Mission & Velocity

> *"Velocity over theory. Shipping production-grade AI agents, local LLM infrastructure, and high-performance backends daily."*

* 🔭 **Currently Building:** Autonomous Linux system diagnostic agents with function calling and multi-tool dispatching.
* 💬 **Targeting:** Founding AI Engineer / Applied AI Engineer roles at fast-moving, high-velocity startups.
* 📫 **Direct Contact:** [himanshu.zyx7@gmail.com](mailto:himanshu.zyx7@gmail.com)

