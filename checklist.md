# Submission Checklist

> [!IMPORTANT]
> PLEASE READ ALL OF THIS DOCUMENT BEFORE MAKING A SUBMISSION TO SWE-BENCH
>
> Make sure you follow the instructions carefully and provide the necessary information.

## PR Description + `README.md`
Please include:
1. A description of your system (arXiv paper, technical report, blog post), or a link to it. Also add as `info / report` in `metadata.yaml`.
2. The names of the people who were involved in producing the submission and the website or LinkedIn profile of the first author.

> [!WARNING]
> For every submission **we expect a technical report or blog post describing your system**.
> The goal of our leaderboard is to accept entries that provide meaningful contributions to the advancement of AI for SWE.
> 
> Therefore, if you do not provide a technical report, or the report is not of sufficient quality, we will not accept your submission.
> Examples of good reports:
> - [Weights & Biases](https://wandb.ai/wandb/agents/reports/Creating-a-state-of-the-art-AI-programming-agent-with-OpenAI-s-o1--VmlldzoxMTAyODI2Ng)
> - [Anthropic](https://www.anthropic.com/engineering/swe-bench-sonnet)
> - [Nvidia CORTEXA](https://research.nvidia.com/labs/adlr/cortexa/)

## Checklist
Copy and paste this into the PR description of your submission.
- [ ] Is a pass@1 submission (does not attempt the same task instance more than once)
- [ ] Does not use NoCode-bench test knowledge (`PASS_TO_PASS`, `FAIL_TO_PASS`)
- [ ] Does not have web-browsing OR has taken steps to prevent lookup of NoCode-bench solutions via web-browsing


> [!NOTE]
> **Test Use**: Your system does NOT use `PASS_TO_PASS` tests or `FAIL_TO_PASS` tests.

> [!NOTE]
> **Web Browsing**: If your system has web-browsing abilities, please indicate what steps you took to make sure it could not browse to the GitHub repos (or other sources, such as mirrors) to find the actual solutions for NoCode-bench tasks. Potential steps you can take include blocking specific GitHub URLs in your system's web browser, and manually inspecting trajectories to make sure that no unallowed behavior is happening.

## `metadata.yaml`
Adjust these fields as necessary. For `model`, we use the naming convention for [LiteLLM](https://www.litellm.ai/) ([examples](https://docs.litellm.ai/docs/providers/openai#openai-chat-completion-models)).
```yaml
info:
  logo: URL/link to your organization's logo, if applicable
  name: Leaderboard Entry Name
  site: URL to page describing your submission. If your submission is open source, there must be a prominent link to the source code in the top third of this page. 
  report: ArXiv / Technical Report + Blog Report
  authors: The names of the people who were involved in producing the submission. 
tags:
  checked: false (See README.md for info on how to get your results verified)
  model: # Only list whichever ones your system uses.
  - claude-3-7-sonnet-20250219
  - claude-3.5-sonnet-20241022
  - o3-mini
  - o4-mini
  - <Model Name>
  org:
  - SWE-agent
  - OpenHands
  - Agentless
  - <Company Name>
  os_model: true/false # Is the LM your system uses open weights?
  os_system: true/false # Is the code for your system open source + runnable?
  system:
    attempts: 1 / 2+
```

* If your system uses a Language Model, you *must* specify in the `model` field.
