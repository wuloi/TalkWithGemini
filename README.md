<div align="center">
<h1 align="center">Talk With Gemini</h1>

![GitHub deployments](https://img.shields.io/github/deployments/ResearchAIGC/TalkWithGemini/Production)
![GitHub Release](https://img.shields.io/github/v/release/ResearchAIGC/TalkWithGemini)
![Docker Image Size (tag)](https://img.shields.io/docker/image-size/xiangfa/talk-with-gemini/latest)
![Docker Pulls](https://img.shields.io/docker/pulls/xiangfa/talk-with-gemini)
![GitHub License](https://img.shields.io/github/license/ResearchAIGC/TalkWithGemini)

Deploy your private Gemini application for free with one click, supporting Gemini 1.5 Pro, Gemini 1.5 Flash, Gemini Pro and Gemini Pro Vision models.

[![Web][Web-image]][web-url]
[![MacOS][MacOS-image]][download-url]
[![Windows][Windows-image]][download-url]
[![Linux][Linux-image]][download-url]

[Web App][web-url] / [Desktop App][download-url] / [Issues](https://github.com/ResearchAIGC/TalkWithGemini/issues)

[web-url]: https://gemini.u14.app/
[download-url]: https://github.com/ResearchAIGC/TalkWithGemini/releases
[Web-image]: https://img.shields.io/badge/Web-PWA-orange?logo=microsoftedge
[Windows-image]: https://img.shields.io/badge/-Windows-blue?logo=windows
[MacOS-image]: https://img.shields.io/badge/-MacOS-black?logo=apple
[Linux-image]: https://img.shields.io/badge/-Linux-333?logo=ubuntu

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2FResearchAIGC%2FTalkWithGemini&project-name=talk-with-gemini&env=GEMINI_API_KEY&env=ACCESS_PASSWORD&repository-name=talk-with-gemini)

[![Open in Gitpod](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io/#https://github.com/ResearchAIGC/TalkWithGemini)

![cover](./public/screenshots/screenshots.png)

Simple interface, supports image recognition and voice conversation

![Gemini 1.5 Flash](./public/screenshots/pc-screenshot-1.png)

Supports Gemini 1.5 and Gemini 1.5 Flash multimodal models

![Tray app](./docs/images/trayapp.png)

A cross-platform application client that supports a permanent menu bar, doubling your work efficiency

</div>

> Note: If you encounter problems during the use of the project, you can check the known problems and solutions of [FAQ](#FAQ).

## Features

- **Deploy for free with one-click** on Vercel in under 1 minute
- Provides a very small (~4MB) cross-platform client (Windows/MacOS/Linux), can stay in the menu bar to improve office efficiency
- Supports multi-modal models and can understand images, videos, audios and some text documents
- Talk mode: Let you talk directly to Gemini
- Visual recognition allows Gemini to understand the content of the picture
- Assistant market with hundreds of selected system instruction
- Full Markdown support: LaTex formulas, code highlighting, and more
- Automatically compress contextual chat records to save Tokens while supporting very long conversations
- Privacy and security, all data is saved locally in the user's browser
- Support PWA, can run as an application
- Well-designed UI, responsive design, supports dark mode
- Extremely fast first screen loading speed, supporting streaming response
- Static deployment supports deployment on any website service that supports static pages, such as Github Page, Cloudflare, Vercel, etc.
- Multi-language support: English、简体中文、繁体中文、日本語、한국어、Español、Deutsch、Français、Português、Русский and العربية

## Roadmap

- [x] Reconstruct the topic square and introduce Prompt list
- [x] Use tauri to package desktop applications
- [ ] Implementation based on functionCall plug-in
- [ ] Support conversation list

## Get Started

1. Get [Gemini API Key](https://aistudio.google.com/app/apikey)
2. Click
   [![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2FResearchAIGC%2FTalkWithGemini&project-name=talk-with-gemini&env=GEMINI_API_KEY&env=ACCESS_PASSWORD&repository-name=talk-with-gemini)
3. Start using

### Updating Code

If you want to update instantly, you can check out the [GitHub documentation](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/syncing-a-fork) to learn how to synchronize a forked project with upstream code.

You can star or watch this project or follow author to get release notifications in time.

## Access Password

This project provides limited access control. Please add an environment variable named `ACCESS_PASSWORD` on the vercel environment variables page.

After adding or modifying this environment variable, please redeploy the project for the changes to take effect.

## Custom model list

This project supports custom model lists. Please add an environment variable named `NEXT_PUBLIC_GEMINI_MODEL_LIST` in the `.env` file or environment variables page.

The default model list is represented by `all`, and multiple models are separated by `,`.

If you need to add a new model, please directly write the model name `all,new-model-name`, or use the `+` symbol plus the model name to add, that is, `all,+new-model-name`.

If you want to remove a model from the model list, use the `-` symbol followed by the model name to indicate removal, i.e. `all,-existing-model-name`. If you want to remove the default model list, you can use `-all`.

If you want to set a default model, you can use the `@` symbol plus the model name to indicate the default model, that is, `all,@default-model-name`.

## Environment Variables

### `GEMINI_API_KEY` (optional)

Your Gemini api key. If you need to `enable` the server api, this is required.

### `GEMINI_API_BASE_URL` (optional)

> Default: `https://generativelanguage.googleapis.com`

> Examples: `http://your-gemini-proxy.com`

Override Gemini api request base url. **To avoid server-side proxy url leaks, links in front-end pages will not be overwritten. **

### `GEMINI_UPLOAD_BASE_URL` (optional)

> Default: `https://generativelanguage.googleapis.com`

> Example: `http://your-gemini-upload-proxy.com`

Override Gemini file upload api base url. **To avoid server-side proxy url leaks, links in front-end pages will not be overwritten. **

### `NEXT_PUBLIC_GEMINI_MODEL_LIST` (optional)

Custom model list, default: all.

### `NEXT_PUBLIC_ASSISTANT_INDEX_URL` (optional)

> Default: `https://chat-agents.theforage.cn`

> Examples: `http://your-assistant-market-proxy.com`

Override assistant market api request base url. The api link in the front-end interface will be adjusted synchronously.

### `NEXT_PUBLIC_UPLOAD_LIMIT` (optional)

File upload size limit. There is no file size limit by default.

### `ACCESS_PASSWORD` (optional)

Access password.

### `HEAD_SCRIPTS` (optional)

Injected script code can be used for statistics or error tracking.

### `EXPORT_BASE_PATH` (optional)

Only used to set the page base path in [static deployment](#static-deployment) mode.

## Requirements

NodeJS >= 18, Docker >= 20

## Development

If you have not installed pnpm

```shell
npm install -g pnpm
```

```shell
# 1. install nodejs and yarn first
# 2. config local variables, please change `.env.example` to `.env` or `.env.local`
# 3. run
pnpm install
pnpm dev
```

## Deployment

### Docker (Recommended)

> The Docker version needs to be 20 or above, otherwise it will prompt that the image cannot be found.

> ⚠️ Note: Most of the time, the docker version will lag behind the latest version by 1 to 2 days, so the "update exists" prompt will continue to appear after deployment, which is normal.

```shell
docker pull xiangfa/talk-with-gemini:latest

docker run -d --name talk-with-gemini -p 5481:3000 xiangfa/talk-with-gemini
```

You can also specify additional environment variables:

```shell
docker run -d --name talk-with-gemini \
   -p 5481:3000 \
   -e GEMINI_API_KEY=AIzaSy... \
   -e ACCESS_PASSWORD=your-password \
   xiangfa/talk-with-gemini
```

If you need to specify other environment variables, please add `-e key=value` to the above command to specify it.

Deploy using `docker-compose.yml`:

```shell
version: '3.9'
services:
   talk-with-gemini:
      image: xiangfa/talk-with-gemini
      container_name: talk-with-gemini
      environment:
         - GEMINI_API_KEY=AIzaSy...
         - ACCESS_PASSWORD=your-password
      ports:
         - 5481:3000
```

### Static Deployment

You can also build a static page version directly, and then upload all files in the `out` directory to any website service that supports static pages, such as Github Page, Cloudflare, Vercel, etc..

```shell
pnpm build:export
```

If you deploy the project in a subdirectory and encounter resource loading failures when accessing, please add `EXPORT_BASE_PATH=/path/project` in the `.env` file or variable setting page.

## FAQ

#### ~~About the solution that vercel and netlify agents cannot upload large files~~

~~The currently known vercel and netlify both use serverless edge computing. Although the response speed is fast, they have size restrictions on uploaded files. Cloudflare Worker has relatively loose limits on large files (500MB for free users, 5GB for paid users) and can be used as an api proxy. [How to deploy the Cloudflare Worker api proxy](/docs/How-to-deploy-the-Cloudflare-Worker-api-proxy.md)~~

#### Why can’t I upload common documents such as doc, excel, and pdf?

Currently, the two models `Gemini 1.5 Pro` and `Gemini 1.5 Flash` support most images, audios, videos and some text files. For details, see [Support List](https://ai.google.dev/gemini-api/docs/prompting_with_media). For other document types, we will try to use [LangChain.js](https://js.langchain.com/v0.2/docs/introduction/) later.

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=ResearchAIGC/TalkWithGemini&type=Date)](https://star-history.com/#ResearchAIGC/TalkWithGemini&Date)

## LICENSE

[GPL-3.0-only](https://opensource.org/license/gpl-3-0)

## Original

[https://github.com/Amery2010/TalkWithGemini](https://github.com/Amery2010/TalkWithGemini)
