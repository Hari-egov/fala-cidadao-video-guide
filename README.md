# Fala Cidadão — training video guide

A one-page guide to the training videos for **Fala Cidadão**, the citizen complaint management system
rolled out in Mozambique on the DIGIT platform by eGov Foundation.

**Open the page: https://hari-egov.github.io/fala-cidadao-video-guide/** — no account needed.

- Portuguese page text: add `?lang=pt` to the address.
- Jump straight to one video: add its code, for example `#E05`.

## What is on the page

45 short videos, about two hours in total. English narration, subtitles in English and Portuguese.
The video files are on Google Drive and play inside the page.

| Group | Videos | Who it is for |
|---|---|---|
| Daily use: citizen, reception, screening, supervisor, case manager, oversight and dashboard (M00–M09) | 10 | Field staff |
| Setting up the system in the Configurator (C01–C11) | 11 | Administrators |
| How the system works inside (E01–E13) | 13 | Support team (L3) |
| Keeping the servers running (O01–O12; one video is internal) | 11 | Operations (L4) |

The same videos as files, with both subtitle tracks:
https://drive.google.com/drive/folders/15JwJfgKHSBNZhjkhYwT32CFuL8ZXR9GU

## Prerequisites

What we had before starting, all free except the Claude plan:

| Need | What it is for | What we used |
|---|---|---|
| A test copy of the system | Recording on test accounts and test data; never the live system | A local copy and a training server |
| A laptop | Everything runs on it | Ubuntu 20.04 |
| Claude Code | Writes the scripts, runs the steps, checks the videos | Claude Code 2.1 |
| Node.js with Playwright and Chromium | The browser robot that records the screens | Node.js 20, playwright-core 1.59, Chromium |
| Python with edge-tts | The computer voice, one voice per language | Python 3.8, edge-tts 7.3 |
| ffmpeg | Puts picture, voice, subtitles and title cards together | ffmpeg 4.2 |
| Git and a GitHub account | Publishing this page on GitHub Pages | Git 2.25 |
| A Google account | The Drive folder with the videos and subtitle tracks | Google Drive |
| One reviewer | Someone who knows the product, to read each script and watch each video | |

## How the videos were made

Every video starts as a text script: the facts, what is on screen and what the voice says, second by second.

1. A browser robot (Playwright) records the real product on a **test copy** with test accounts and test data.
2. A computer voice (edge-tts) reads the script, one voice per language.
3. ffmpeg puts picture, voice, subtitles and title cards together into one video.
4. The video is published: Drive folder, this page, the training plan.

When a screen changes, the script is edited and only that video is rebuilt. Nothing was recorded on a live system,
and all the tools are free.

## How this page is built

`index.html` is the whole site. It is generated from a list of the videos (titles, lengths, Drive links) by a small
script in the tooling folder, which is not yet in a repository. To update the page: regenerate `index.html`, commit
and push; GitHub Pages rebuilds it in about a minute.

## Reuse

The tools are being packaged so that other rollouts and products can make their own set the same way.
Open an issue in this repository if you want to use them.
