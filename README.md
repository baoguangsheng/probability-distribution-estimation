# Glimpse
**This code is for our paper "Glimpse: Enabling White-Box Methods to Use Proprietary Models for Zero-Shot LLM-Generated Text Detection"**, where we borrow some code from [Fast-DetectGPT](https://github.com/baoguangsheng/fast-detect-gpt).

[Paper](https://arxiv.org/abs/2412.11506)


## Brief Intro
<table class="tg"  style="padding-left: 30px;">
  <tr>
    <th class="tg-0pky">Method</th>
    <th class="tg-0pky">ChatGPT</th>
    <th class="tg-0pky">GPT-4</th>
    <th class="tg-0pky">Claude-3<br/>Sonnet</th>
    <th class="tg-0pky">Claude-3<br/>Opus</th>
    <th class="tg-0pky">Gemini-1.5<br/>Pro</th>
    <th class="tg-0pky">Avg.</th>
  </tr>
  <tr>
    <td class="tg-0pky">Fast-DetectGPT<br/>(Open-Source: gpt-neo-2.7b)</td>
    <td class="tg-0pky">0.9487</td>
    <td class="tg-0pky">0.8999</td>
    <td class="tg-0pky">0.9260</td>
    <td class="tg-0pky">0.9468</td>
    <td class="tg-0pky">0.8072</td>
    <td class="tg-0pky">0.9057</td>
  </tr>
  <tr>
    <td class="tg-0pky">Glimpse (Fast-DetectGPT)<br/>(Proprietary: gpt-3.5)</td>
    <td class="tg-0pky"><b>0.9766</b><br/>(<b>↑54%</b>)</td>
    <td class="tg-0pky"><b>0.9411</b><br/>(<b>↑41%</b>)</td>
    <td class="tg-0pky"><b>0.9576</b><br/>(<b>↑43%</b>)</td>
    <td class="tg-0pky"><b>0.9689</b><br/>(<b>↑42%</b>)</td>
    <td class="tg-0pky"><b>0.9244</b><br/>(<b>↑61%</b>)</td>
    <td class="tg-0pky"><b>0.9537</b><br/>(<b>↑51%</b>)</td>
  </tr>
</table>
The table shows detection accuracy (measured in AUROC) across five source LLMs, where the methods are evaluated on a diverse dataset Mix3 (a mixture of XSum, Writing, and PubMed) produced by each source model. The baseline Fast-DetectGPT uses an open-source gpt-neo-2.7b model but our Glimpse (Fast-DetectGPT) uses a proprietary gpt-3.5 model. The notion "↑" indicates the improvement relative to the remaining space, calculated by "(new - old) / (1.0 - old)".

## Environment
* Python3.12
* PyTorch2.3.1
* Setup the environment:
  ```pip install -r requirements.txt```
  
(Notes: the baseline methods are run on 1 GPU of Tesla A100 with 80G memory, while Glimpse is run on a CPU environment.)

## Workspace
Following folders are created for our experiments:
* ./exp_main -> experiments with five latest LLMs as the source model (main.sh).
* ./exp_langs -> experiments on six languages (langs.sh).

(Notes: we share the data and results for convenient reproduction.)

### Citation
If you find this work useful, you can cite it with the following BibTex entry:

    @articles{bao2024glimpse,
      title={Glimpse: Enabling White-Box Methods to Use Proprietary Models for Zero-Shot LLM-Generated Text Detection},
      author={Bao, Guangsheng and Zhao, Yanbin and He, Juncai and Zhang, Yue},
      year={2024}
    }

