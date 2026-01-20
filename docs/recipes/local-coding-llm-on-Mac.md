# Local LLM Coding Support on Mac OS

!!! info "External Information"

    * [Running DeepSeek Locally on Mac](https://thesweetbits.com/running-deepseek-locally-on-mac-system-requirements-setup-guide/)
    * Integrating Ollama with the `Sublime Text` editor: [OllamaSublime](https://github.com/dapepe/OllamaSublime)
    * [llm-completion](https://github.com/pickledish/llm-completion/) for SublimeText


<!--more-->

## LLM Environments

### LM Studio

LM Studio seems like a polished choice for a combined chat & local server environment.

* [LM Studio](https://lmstudio.ai/)

A tested setup is to download LM Studio and then some model, e.g. `devstral-small-2-2512`
for coding support or an `Apertus` flavour for translations etc.

LM Studio installs a menu bar widget to start/stop a local server for the currently
selected model.

#### Auto-completion for SublimeText

A main reason for getting the local LLM code support was the auto-completion function
known from SublimeText + LSP-Copilot + Copilot account. Here a simple solution is
provided through [llm-completion](https://github.com/pickledish/llm-completion/):

```
cd Library/Application\ Support/Sublime\ Text/Packages
git clone https://github.com/pickledish/llm-completion.git "LLM Completion"
```

First test of sublime package settings, using LM Studio as described above:

```
{
    "inline_completion_enabled": true,
    "llm_settings": {
        "model": "devstral-small-2-2512",
        "url": "http://localhost:1234/v1/chat/completions",
        "temperature": 0.2
    }
}
```
... and we'll see from here - to be continued.


### Exo by Exolabs

This seems interesting for clusters of Macs to run large models. Not tried
yet since the first use case is basic LLM coding support on the local machines but
kept in mind for the next batch of M5 Macs...

* <https://exolabs.net/>

### Ollama

* [Download](https://ollama.com/download) or
* `brew install ollama && `brew services start ollama`
* `ollama pull deepseek-r1:8b`

For SublimeText integration see above link to `OllamaSublime`. Basically you need to

* have Package Control installed
* ~~install "Ollama" package via Package Control~~ (not working currently)
* clone the repo from GitHub into your `Packages` folder
    - find through `Preferences` -> `Browse Packages…`
    - usually `/Users/$User/Library/Application\ Support/Sublime\ Text/Packages`
    - Sublie expects the package to be called `Ollama`, not `OllamaSublime`
 (see issue [#2](https://github.com/dapepe/OllamaSublime/issues))
    - e.g.
```bash
cd /Users/$User/Library/Application\ Support/Sublime\ Text/Packages
git clone https://github.com/dapepe/OllamaSublime.git Ollama
```

## Mac Things

New Macs (M4 and beyond) with Thunderbolt 5 now support memeory sharing (RDMA)
over Thunderbolt which then can be used for low latency communication and distributed
zero-configuration memory sharig - ideal to enable larger language models. This
requires at least Mac OS 26.2 and a Thunderbolt 5 connection and has to be activated
by rebooting in recovery mode, opening the terminal and

```
rdma_ctl enable
shutdown -r now
```

The distributed memory can be utilized e.g. through [exo](https://github.com/exo-explore/exo).

