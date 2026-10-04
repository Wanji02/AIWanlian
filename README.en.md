# AI万链

**Language:** [中文](README.md) · English

**A local AI companion for everyday life at home.**

AI万链 is a product concept and working prototype for people who want a familiar companion after a busy day. One local AI hub maintains the assistant's persona, conversation state, long-term memory, and delegated tasks. Phones and home devices provide ways to talk, observe, and act. The aim is a comfortable experience that continues across devices.

**Initiated and led by Star Zhang (张万基)** · AI product and interaction design · MSc in Computer Science and Technology

## Why this product

After work, a person may want to talk about their day, settle in, and hand over small plans or reminders. AI万链 explores how a consistent, configurable companion can support those moments while connecting conversation with useful actions at home.

The public characters are **Xiaoyue (小月)** and **Xiaoxing (小星)**. The current prototype and physical-device tests focus on Xiaoyue.

## What has been built and tested

| Experience | Current prototype |
| --- | --- |
| One conversation across devices | Phone text and voice, plus a physical speaker, connect to the same hub and stored conversation. |
| Memory and personalization | Important information can be saved, retrieved, and corrected; address and conversation style can be configured. |
| Hands-free conversation | Saying “Xiaoyue” starts a voice turn. A follow-up window of about 15 seconds begins after the speaker finishes its reply. |
| Dynamic, natural speech | New replies are synthesized and played incrementally at 24 kHz. Voice quality, pauses, and sentence endings were refined through listening comparisons. |
| Visual question answering | A user request can trigger a frame from a separate camera for local visual understanding and an audible answer. |
| A task with a physical result | A spoken request can set a physical alarm clock; the clock rings at the set time and stops when its dial is pressed. |

The current prototype connects **four device categories: phone, speaker, camera, and physical alarm clock**. In a camera test, the assistant correctly identified a cup held in view. In alarm tests, the clock rang and stopped as expected.

## My product work

I initiated the project and led the user scenario, priorities, interaction design, device selection, and hands-on acceptance testing. I used AI-assisted programming to help integrate the prototype.

Three decisions shaped the experience:

1. **Start the follow-up timer when audio actually ends.** The user should have the full window to answer after hearing Xiaoyue, rather than lose time while speech is still playing.
2. **Treat voice naturalness as a repeatable product problem.** I compared fresh replies across scenarios and devices, then separated issues in voice generation, pacing, and playback before selecting the accepted voice experience.
3. **Require a real device result for an alarm.** Talking about a reminder is different from setting one, and a verbal “done” is different from a clock that actually rings.

## How the prototype works

`Phone / speaker / camera → local AI hub ↔ conversation and memory → response or structured device task → speaker / physical alarm`

The hub uses Python, FastAPI, SQLite, local Qwen models for dialogue, vision, speech recognition and speech generation, llama.cpp, and ESP32-S3 device integration. Speech can begin playing while the remaining audio is generated. The full text reply and its review currently complete before speech synthesis begins.

The product is being developed in stages. The next directions include more responsive conversation, appropriately timed check-ins, lighting and home-device coordination, planning and delegated document work, and, over time, compatible robots. These are product goals rather than completed prototype features.

## Demo and project material

A physical-device demo video is being prepared and will be linked here. The [Chinese project overview](README.md) includes the architecture diagram and links to product decisions, validation, and roadmap documents.

This repository presents the product and its verified prototype. Core implementation and Xiaoyue's voice assets remain private. See [NOTICE](NOTICE.md) for this repository's use terms and [ACKNOWLEDGEMENTS](ACKNOWLEDGEMENTS.md) for upstream technologies.

Updated October 4, 2026.
