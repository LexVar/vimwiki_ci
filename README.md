
# Vimwiki HTML pipeline

[![Pipeline](https://github.com/LexVar/vimwiki_deploy/actions/workflows/pipeline.yml/badge.svg)](https://github.com/LexVar/vimwiki_deploy/actions/workflows/pipeline.yml)

Github actions pipeline to build and deploy a static HTML page generated from my personal vimwiki notes.

This pipeline is triggered when I make a commit to my notes repo, which then deploys the latest version to my raspberry Pi running a self-hosted github runner.

## Docker build image

The repo includes an alpine based image ready to convert vimwiki markdown files to HTML.

### Usage

1. Pull and run the [image](https://hub.docker.com/repository/docker/lexvar/vimwiki-build): 
   
		docker pull docker.io/lexvar/vimwiki-build:1.0

2. Copy your vimwiki markdown directory to /root/vimwiki
3. Inside the directory run:
    
        vim +VimwikiAll2HTML +q index.md

The output html files will be inside the `/root/vimwiki/site_html` directory.
## Tools

- [vimwiki_markdown](https://github.com/WnP/vimwiki_markdown)
