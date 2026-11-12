Jack Davison Powell

I build self-hosted AI systems on second-hand datacenter hardware. Three inference machines, 200 GB of RAM, 64 GB of HBM, all in my house.

Pantheon core: A Proxmox host on a dell r210 rackmount server, running PFsense firewall from the router with a custom 2.5gb NIC, going out into a rackmount Cisco switch for VLAN segments, my proxmox box runs containers that are the core of my main AI systems, split evenly across threads so each compute node stays AI only for maximum performance.

Volta Node: 1x Nvidia Tesla V100 32gb, 64gb of ram, running qwen3.8 flash next at 70t/s writing and 1000t/s reading.

Pascal Node: 2x Nvidia Tesla P100 16gb, 64gb of ram, running 2 more copies of qwen3.8 flash next, 2 slots of 25t/s and 400t/s reading. 1660 super for voice transcription and qwen3 0.5B fine tuned.

Maximus Node: 1x Nvidia GeForce RTX 5070 12gb, 64gb of ram, running qwen3.8 flash next at 70t/s and 1800t/s reading

I have a pool of compute across all all 3 nodes just like a real cloud datacenter, built into a queue system where you can use many independent sessions at once, retaining speed and usability in the process. I built my very own own kernels for the GPU's, and my very own disciplined agentic harness that competes with big tech companies. Many people wonder why I dont just use claude, and the answer is this rack is 100% unlimited, 100% private, and 100% custom systems from scratch. Other people my age arent able to compete with my experience in building AI systems because normal consumer cards are x more expensive per gigabyte of VRAM and the whole limit is VRAM % bandwidth, which old datacenter cards with HBM2 still competes modern cards even though they are a fraction of the price. I have been building computers since I was 11 years old, and I used my experience to build the most cost efficient way to use agentic AI to my advantage.

Problems I have solved
Voice assistant took 13.5 s to answer. Cause was KV-cache reuse, not model size. Now 0.4 s on the same cards.
X99 board would not map that much GPU memory. Rewrote the BIOS to raise the MMIO bar and enable above-4G decoding.
Pascal cards were slow at prompt processing. Rebuilt llama.cpp for the P100. 50% faster prefill. Now writing custom CUDA kernels for Volta and Pascal.
35B model would not fit on one card. Split it across two P100s and found the default that was silently spilling cache to system RAM.
Agents re-read whole conversations every turn. Built a meter and a guard for it. Biggest hidden cost in a long-running agent.
Server “crashed” nightly. It was the OOM killer. Tuned memory protection so the box degrades instead of dying.
An assistant that can call you. Voice stack wired into real phone and FaceTime calls, first word in about a second.
Pascal kept dying during idle hours late at night, then wouldn't boot, diagnosed a bad RAM stick and C-state instability. Now all of my servers are extremely reliable. 

Expertise


Local inference: llama.cpp, CUDA, quantization, multi-GPU splits, old datacenter GPUs.
Voice and real-time: wake word, streaming ASR and TTS, sub-second latency budgets.
Hardware and firmware: multi-GPU builds, BIOS modding, power and thermal limits.
Infrastructure: Debian, Fedora, Proxmox, systemd, Docker, Tailscale.
Languages: Python, Bash, JavaScript.

Currently

Georgia Southern. Building toward AI engineering and autonomous systems, on the self-hosted end where the constraints are latency, VRAM, and no internet.

📍 Atlanta, GA · ✉️ jackdavisonpowell@gmail.com
