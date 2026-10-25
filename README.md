Jack Davison Powell

I build self-hosted AI systems on hardware I put together myself.

Most of what I know came from making second-hand datacenter parts do things they were never meant to do. My current setup is three inference machines with over 200 GB of RAM and 64 GB of HBM across repurposed NVIDIA datacenter GPUs, plus smaller cards for transcription, speech, embeddings, and retrieval. Everything below runs in my house, and everything below has broken at least once.

Problems I have solved

Voice assistant took 13.5 seconds to start talking. Everyone’s instinct, including mine, was a smaller model. The real cause was the KV cache being thrown away between turns. Fixing prefix reuse brought time-to-first-token to 0.4 seconds on the same model and the same cards.

Too much GPU memory for one X99 board. Consumer X99 firmware will not map that much HBM. I rewrote the BIOS by hand to raise the low MMIO bar and enable above-4G decoding so all the cards post and are usable.

Pascal cards were slow at prompt processing. Rebuilt llama.cpp specifically for the P100’s architecture and tuned the build for it. Roughly 50% faster prefill with no model change. Now writing custom CUDA kernels for the Volta and Pascal cards the mainstream engines have moved on from.

One 35B model would not fit on one card. Split it across two P100s and found the hidden default that was quietly spilling the cache to system RAM and killing throughput.

The AI agents were re-reading entire conversations every turn. Built a meter that measures how much context each brain re-reads, plus an hourly guard that catches regressions, because this is the single biggest hidden cost in a long-running agent.

The server kept “crashing.” It was not crashing. The out-of-memory killer was shooting the model process. Tuned RAM protection so the box degrades instead of dying.

GPUs disappeared. NVIDIA’s multi-process service was hiding every card but one, and killing a client could silently drop a model to CPU. Diagnosed it, documented it, built around it.

Laptop display flickered and starved under load. Traced it to the panel negotiating two DisplayPort lanes instead of four and forced four-lane HBR3. Also proved the “uncompressed” claim in the spec sheet was wrong.

Needed to reach my network when both my VPN and my fallback box were down. Built a third route through a jump host on a different network, so there is always a way in.

An AI assistant that can call you. Wired the voice stack into real phone and FaceTime calls, including auto-answer and a fast no-tools call brain that gets to the first word in about a second. Found and fixed audio chopping caused by capture drops on the bridge machine.

A satellite microphone in another room that heals itself. Raspberry Pi satellite with a wake word, which detects when its own mic has died and recovers without anyone touching it.

Game ran at 80 fps. Profiled a Godot project I am building and shipped it at 145 fps over a weekend of optimization passes.

A homelab run like production. Proxmox, LXC containers, Tailscale, network-wide DNS, machines that reach each other by name, and backups that have actually been restored from.

A web app with real users. Rollback-safe deploys, a prefill bottleneck traced to its root cause, and a security fix contributed back upstream.

Expertise

Local inference. llama.cpp, CUDA, quantization, pytorch, KV-cache behavior, splitting models across GPUs, getting modern models to run on Volta and Pascal hardware.

Voice and real-time systems. Wake word, streaming ASR, streaming TTS, latency budgets measured in hundreds of milliseconds.

Hardware and firmware. Multi-GPU workstation builds, BIOS modification, power and thermal limits, diagnosing instability on overclocked systems.

Linux infrastructure. Debian, Fedora, Proxmox, systemd, Docker, Tailscale, SSH, backups and restores.

Languages and tools. Python, Bash, JavaScript, MediaPipe, OpenCV, Godot.

Currently

Studying at Georgia Southern. Building toward AI engineering and autonomous systems, specifically the local, self-hosted end of it, where the interesting constraints are latency, VRAM, and what a machine can do when the internet is out.

📍 Atlanta, GA · ✉️ jackdavisonpowell@gmail.com
