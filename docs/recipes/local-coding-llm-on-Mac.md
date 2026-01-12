# Local LLM Coding Support on Mac OS

!!! info "External Information"

    * [Running DeepSeek Locally on Mac](https://thesweetbits.com/running-deepseek-locally-on-mac-system-requirements-setup-guide/)
    * Integrating Ollama with the `Sublime Text` editor: [OllamaSublime](https://github.com/dapepe/OllamaSublime)


<!--more-->

## Exo by Exolabs

This seems interesting for clusters of Macs to run large models. Not tried
yet since the first use case is basic LLM coding support on the local machines but
kept in mind for the next batch of M5 Macs...

* <https://exolabs.net/>

## Ollama

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


