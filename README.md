## Jack Davison Powell

I build local-first AI infrastructure — the kind that runs on hardware I own,
in a house, with no API bill and no data leaving the building.

Most of what I know came from making a pile of second-hand server parts do
things they were not really meant to do, and from reading the error message
instead of working around it.

### Things I have built

**A local voice assistant that actually runs.** Wake word, streaming ASR,
a local LLM, streaming TTS, and computer vision, on 2× Tesla P100s in a
repurposed X99 workstation and a Raspberry Pi satellite in another room.
Getting time-to-first-token from 13.5s to 0.4s was a KV-cache prefix problem,
not a bigger-model problem — most of the work on that system has been latency
and memory archaeology rather than model choice.

**A homelab I run like production.** Proxmox, LXC containers, Tailscale,
network-wide DNS, a fleet of machines that all reach each other by name.
Backups that have actually been restored from.

**A web app with real users**, and the unglamorous parts that go with it:
deploys that can be rolled back, a prefill bottleneck traced to its root cause,
and a security fix contributed back upstream.

### Public repositories

| | |
|---|---|
| [**claude-code-usage**](https://github.com/jackdavisonpowell-eng/claude-code-usage) | Find out where your Claude Code tokens actually went. Stdlib-only transcript analyzer. |
| [**loose-ends**](https://github.com/jackdavisonpowell-eng/loose-ends) | A to-do list that both you and your AI agents can write to. One markdown file, no server. |
| [**ssh-mesh**](https://github.com/jackdavisonpowell-eng/ssh-mesh) | Every machine `ssh <name>`s every other, passwordless, from one config file. Idempotent. |
| [**handmouse**](https://github.com/jackdavisonpowell-eng/handmouse) | Drive the cursor with your index finger. Pinch to click and drag. MediaPipe + OpenCV. |

Larger projects — the voice assistant and the web app — are private because
they are wired into my house and my network. Happy to walk anyone through them.

### Working with

`Python` · `Bash` · `Linux` (Debian, Fedora, Proxmox) · `CUDA` / `llama.cpp` ·
`QLoRA fine-tuning` · `MediaPipe` / `OpenCV` · `systemd` · `Docker` ·
`Tailscale` · `JavaScript`

### Currently

Studying at Georgia Southern. Building toward AI engineering and autonomous
systems — specifically the local, self-hosted end of it, where the interesting
constraints are latency, VRAM, and what a machine can do when the internet is
out.

📍 Atlanta, GA · ✉️ jackdavisonpowell@gmail.com
