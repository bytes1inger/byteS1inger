<div align="center">

# Gideon Warui

**Platform Engineer** &nbsp;·&nbsp; Nairobi, Kenya

Production infrastructure at national scale, kept reliable,<br>
with the AI platform layer built on top of it.

<br>

<p><a href="https://gideonwarui.com"><img src="https://img.shields.io/badge/gideonwarui.com-0F172A?style=flat-square&logo=githubpages&logoColor=white" alt="Website"></a> <a href="https://www.linkedin.com/in/warui-wanjiru"><img src="https://img.shields.io/badge/LinkedIn-0F172A?style=flat-square&logoColor=white" alt="LinkedIn"></a> <a href="mailto:hello@gideonwarui.com"><img src="https://img.shields.io/badge/hello@gideonwarui.com-0F172A?style=flat-square&logo=gmail&logoColor=white" alt="Email"></a></p>

</div>

<br>

---

### Platform engineering

<p>
<img src="https://img.shields.io/badge/Kubernetes-2563EB?style=flat-square&logo=kubernetes&logoColor=white"> <img src="https://img.shields.io/badge/Terraform-2563EB?style=flat-square&logo=terraform&logoColor=white"> <img src="https://img.shields.io/badge/Argo%20CD-2563EB?style=flat-square&logo=argo&logoColor=white"> <img src="https://img.shields.io/badge/Helm-2563EB?style=flat-square&logo=helm&logoColor=white"> <img src="https://img.shields.io/badge/OpenShift-2563EB?style=flat-square&logo=redhatopenshift&logoColor=white"> <img src="https://img.shields.io/badge/AWS-2563EB?style=flat-square&logoColor=white"> <img src="https://img.shields.io/badge/Azure-2563EB?style=flat-square&logoColor=white"> <img src="https://img.shields.io/badge/GitHub%20Actions-2563EB?style=flat-square&logo=githubactions&logoColor=white"> <img src="https://img.shields.io/badge/Linux-2563EB?style=flat-square&logo=linux&logoColor=white">
</p>

I run Kubernetes in production across EKS, AKS, OpenShift and AWS Outposts. The largest
estate is roughly 1,300 Argo CD applications reconciling a 2,000-facility fleet against a
single uniform base manifest contract, provisioned in Terraform. I have built multi-account
landing zones from nothing: account vending, SSO provisioning and least-privilege
cross-account roles, all as reusable modules.

Most of what I leave behind is the unglamorous part. The modules, pipeline templates,
runbooks and disaster recovery blueprints other teams reuse instead of reinventing.
Twenty-seven architecture decision records and counting.

<br>

### Reliability

<p>
<img src="https://img.shields.io/badge/Prometheus-EA580C?style=flat-square&logo=prometheus&logoColor=white"> <img src="https://img.shields.io/badge/Grafana-EA580C?style=flat-square&logo=grafana&logoColor=white"> <img src="https://img.shields.io/badge/OpenTelemetry-EA580C?style=flat-square&logo=opentelemetry&logoColor=white"> <img src="https://img.shields.io/badge/VictoriaMetrics-EA580C?style=flat-square&logo=victoriametrics&logoColor=white"> <img src="https://img.shields.io/badge/Loki-EA580C?style=flat-square&logoColor=white"> <img src="https://img.shields.io/badge/Thanos-EA580C?style=flat-square&logoColor=white">
</p>

I took a production estate from around 90% availability to a formal 99.9% objective, cut
mean time to recovery from six hours to under one, and dropped the incident rate from two or
three a week to roughly one a quarter.

I alert on symptoms, not causes. One example: a five-hour detection gap on Tomcat
thread-pool exhaustion, where the liveness check could not tell a dead JVM from a live one
that could not serve traffic. I closed it by deploying the JMX exporter fleet-wide and
writing an alert that separates the two.

Toil is the thing I most want gone. I cut deployment turnaround from eight hours of manual
release work to ten minutes across nine projects, and replaced a manual per-facility upgrade
path with one that takes a release across 1,304 applications in a single driven run. I treat
capacity and cost as reliability concerns rather than finance ones: fleet spend from around
US$160,000 to US$95,000 a month through right-sizing and autoscaling.

<br>

### AI infrastructure

<p>
<img src="https://img.shields.io/badge/vLLM-7C3AED?style=flat-square&logo=vllm&logoColor=white"> <img src="https://img.shields.io/badge/llm--d-7C3AED?style=flat-square&logoColor=white"> <img src="https://img.shields.io/badge/LiteLLM-7C3AED?style=flat-square&logoColor=white"> <img src="https://img.shields.io/badge/MCP-7C3AED?style=flat-square&logo=anthropic&logoColor=white"> <img src="https://img.shields.io/badge/Anthropic-7C3AED?style=flat-square&logo=anthropic&logoColor=white"> <img src="https://img.shields.io/badge/Hugging%20Face-7C3AED?style=flat-square&logo=huggingface&logoColor=white"> <img src="https://img.shields.io/badge/Langfuse-7C3AED?style=flat-square&logoColor=white">
</p>

I serve open-weight models, Qwen and GLM, on Kubernetes with vLLM, using llm-d for
cache-aware routing over the Kubernetes Gateway API Inference Extension and LiteLLM as the
model gateway, with virtual keys and per-key budgets across self-hosted and commercial
providers.

I build agents that plan and act through tool use, and the Model Context Protocol servers
they reach through: scoped read-only access, semantic schema description, OAuth and scoped
tokens for connector authentication, with retrieval and agent memory behind them.

I measure AI like anything else in production. Token cost per request, latency percentiles,
failure and fallback rates, and answer quality scored live in production against an
objective rather than only before release. In regulated estates I strip identifiers before
anything reaches a model endpoint or a log store, and that constraint is usually what
decides which workloads can use a hosted provider and which have to be self-hosted.

<br>

---

### Writing

I write up production incidents and infrastructure work at
**[gideonwarui.com](https://gideonwarui.com)**. Around 45 posts so far. A few that people
seem to find useful:

- Azure Blob Private Link looked configured but wasn't: three misconfigs that left public access
- A shadow Azure Function wiped every gold table at 2am
- Natural language to SQL with Claude Haiku: schema grounding, validation, and a read-only DuckDB
- Querying the Kubernetes Metrics API from a pod: RBAC, Python client, and Grafana without Prometheus

<br>

---

### Where this work happens

- **Palladium** &nbsp;·&nbsp; the national health platform, roughly 2,000 facilities, and its clinical AI inference tier
- **Old Mutual** &nbsp;·&nbsp; Nexus, an AI workflow orchestration platform, and the self-hosted inference tier beneath it
- **DNDi** &nbsp;·&nbsp; Model Context Protocol servers and agents on Azure

<br>

---

<div align="center">

<p><img src="https://img.shields.io/badge/Python-334155?style=flat-square&logo=python&logoColor=white"> <img src="https://img.shields.io/badge/Go-334155?style=flat-square&logo=go&logoColor=white"> <img src="https://img.shields.io/badge/SQL-334155?style=flat-square&logo=postgresql&logoColor=white"> <img src="https://img.shields.io/badge/Bash-334155?style=flat-square&logo=gnubash&logoColor=white"></p>

</div>
