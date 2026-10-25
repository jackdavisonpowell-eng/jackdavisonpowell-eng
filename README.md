Jack Davison Powell

I build self-hosted AI systems on second-hand datacenter hardware. Three inference machines, 200 GB of RAM, 64 GB of HBM, all in my house.

Problems I have solved
Voice assistant took 13.5 s to answer. Cause was KV-cache reuse, not model size. Now 0.4 s on the same cards.
X99 board would not map that much GPU memory. Rewrote the BIOS by hand to raise the MMIO bar and enable above-4G decoding.
Pascal cards were slow at prompt processing. Rebuilt llama.cpp for the P100. 50% faster prefill. Now writing custom CUDA kernels for Volta and Pascal.
35B model would not fit on one card. Split it across two P100s and found the default that was silently spilling cache to system RAM.
Agents re-read whole conversations every turn. Built a meter and a guard for it. Biggest hidden cost in a long-running agent.
Server “crashed” nightly. It was the OOM killer. Tuned memory protection so the box degrades instead of dying.
An assistant that can call you. Voice stack wired into real phone and FaceTime calls, first word in about a second.
Expertise

Local inference: llama.cpp, CUDA, quantization, multi-GPU splits, old datacenter GPUs.
Voice and real-time: wake word, streaming ASR and TTS, sub-second latency budgets.
Hardware and firmware: multi-GPU builds, BIOS modding, power and thermal limits.
Infrastructure: Debian, Fedora, Proxmox, systemd, Docker, Tailscale.
Languages: Python, Bash, JavaScript.

Currently

Georgia Southern. Building toward AI engineering and autonomous systems, on the self-hosted end where the constraints are latency, VRAM, and no internet.

📍 Atlanta, GA · ✉️ jackdavisonpowell@gmail.com
