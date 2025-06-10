---
layout: post
title: "OSCP prep: buffer overflow methodology"
date: 2025-06-05
tags: [oscp, study, pentesting]
excerpt: "Buffer overflows finally clicked after weeks of practice. The key was developing a systematic approach rather than just following tutorials."
---

Buffer overflows finally clicked after weeks of practice. The key was developing a systematic approach rather than just following tutorials.

My current methodology:

1. **Crash the application with a pattern** - Use unique pattern to identify exact crash point
2. **Control EIP with precise offset** - Calculate exact bytes needed to overwrite return address
3. **Find bad characters through enumeration** - Test which characters break the exploit
4. **Locate reliable JMP ESP address** - Find stable jump point in memory
5. **Generate and test shellcode** - Create payload and verify execution

The muscle memory is building. What used to take hours now takes 30 minutes on practice machines.

### Key Insights from Practice

The breakthrough came when I stopped memorizing commands and started understanding the *why* behind each step. When you understand what's happening in memory, the methodology becomes logical rather than just procedural.

**Most common mistakes I was making:**
- Not accounting for bad characters in JMP ESP addresses
- Forgetting to subtract decoder size from available buffer space
- Using unreliable memory addresses that change between reboots

**What actually matters:**
- Consistent, reproducible methodology
- Clean environment between attempts
- Proper documentation of each step

OSCP exam prep is accelerating. The pattern recognition is getting faster, and I'm building confidence that the fundamentals are solid. 