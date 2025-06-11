---
layout: post
title: "Hello World - Welcome to My Journey"
date: 2025-01-15
categories: [intro, personal]
tags: [cybersecurity, learning, community]
---

<div class="ascii-header">
<pre>
██   ██ ███████ ██      ██       ██████  
██   ██ ██      ██      ██      ██    ██ 
███████ █████   ██      ██      ██    ██ 
██   ██ ██      ██      ██      ██    ██ 
██   ██ ███████ ███████ ███████  ██████  
</pre>
</div>

## > whoami
Hi there! Im spoon, and this is my first time writing publicly about security. Im a recent graduate with a degree in Cybersecurity, but Ive always felt that sharing as you learn is a powerful tool, so Ive finally decided to catalogue my journey in deepening my practical security skills!

I am starting this blog to document what I learn, keep myself accountable, and to hopefully make some connections with other likeminded people.

## > background-check
I didnt start out in cybersecurity... in fact, Ive bricked my fair share of laptops and home computers trying to download Minecraft mods or sketchy music files online.

And believe it or not, thats not what got me into computers either. For the longest time, computers were just a means to an end, whether that meant hanging with friends or disappearing into multi-hour YouTube spirals.

What truly opened my eyes to the endless puzzles and brainteasers of cyber was a professor I had in junior year of college. (Yes, late to the party...I know.)

I started college as a mechanical engineering major. My lifelong love of cars and motorsport had totally skewed my perception of what that major actually involved. After bombing the first few tests and discovering I had zero love for thermodynamics, I knew it was time to move on.

Thats when I remembered a class I had taken in high school mostly to slack off... Computer Science.

As I mentioned before, I didnt have a particular love for computers or programming especially not JavaScript. So the switch was kind of uncharacteristic. If Im honest, I was probably influenced more by YouTube videos of CS grads in supercars than anything else.

But I stuck with it. I worked my way through the usual gauntlet of intro CS courses: Data Structures, Algorithms, Compilers, Web Design, Cloud Computing. I struggled. A lot. But in early junior year, I took a class on Operating System Design. Through some intense in-class discussions, I was convinced to take Malware Analysis the following semester to build on the system-level programming I had just picked up.

At that point, the seeds of curiosity were starting to take root.

Coming into Malware Analysis, I was already hooked from what little Id heard but I didnt expect it to change everything for me. We started with basic DOS-based malware and worked our way up to SQL Slammer and WebC2GreenCat. I lost countless hours in the lab, pouring over page after page of assembly, my mind swimming with questions as I tried to reverse-engineer the authors intent and methodology.

That class didnt just introduce me to malware, it introduced me to the idea that cybersecurity could be an endless, evolving puzzle. I was all in.

Naturally, when I heard this professor was teaching another class next semester, Software Vulnerabilities, I was first on the waitlist. Getting the chance to develop and execute the very exploits I had spent the previous semester studying was exhilarating.

This class flipped the script instead of reverse engineering someone elses malware, I was now the one writing the payloads, crafting the buffer overflows, and walking through the same thought processes attackers might use. It wasnt about the destruction or the chaos but rather it was the understanding how the vulnerabilities are born, how I could exploit them and why these vulnerabilities get into production environments.

Each assignment drove me further and further into the rabbit hole until I couldnt picture myself doing anything else with my life.

If Malware Analysis laid the foundations for my interests, this class cemented them deep into my being.

After graduation I got the chance to put these theoretical skills to real use as a Research Intern at a university. Here is where I got my first real taste of a research environment: real stakes, real deadlines, and (most indimidatingly of all) real collaboration with professionals far more experienced than me.

I was fortunate enough to be asked to join a research group focusing on secure system design and data transmission. Suddenly, I wasnt just completing assignments or working alone, but I was part of a team building and designing a proof-of-concept system from scratch. And to my surprise, I was asked to lead the team of undergraduates, answering directly to the Professor in charge and working alongside professionals at a National Lab.

That meant managing a team, balancing skill sets, communicating progress, and coordinating efforts to keep the project on track. All the while Im learning SCADA systems, IoT protocols, CAN bus vulnerabilities, and prototyping embedded systems. It was incredibly overwhelming at first, but as I grew to know my team and those supporting us I finally felt like I was building something that mattered.

Our system was a proof-of-concept device for managing electric fleet vehicles, designed to communicate CAN bus data to a central fleet supervisor and schedule firmware updates when connected to charging infrastructure. This project ran in parallel to work my colleagues were doing at the National Lab where they published a whitepaper on electric vehicle charging infrastructure, which while outside of the scope of our project, heavily informed our system design.

The most eye-opening part? We didnt just design a secure protocol, we exposed real dangerous flaws in a potential system like ours. We were able to demonstrate successful exploits on a real vehicle system, including full acceleration and brake disablement. All triggered remotely through insecure hardware channels in production CAN bus firmware. This was a first experience with theoretical exploits having a tangible real-world impact right in front of my eyes.

That experience at the University didnt just help me grow technically, but allowed me to become more confident. It showed me I could hold my own in a room full of sharp people, communicate meaningfully, and even guide the vision of the project in a positive direction.

## > status-check
Since wrapping up my time at the University, Ive settled into a role as a Systems Analyst which, in this case, means wearing a lot of hats. On any given day, Im handling RHEL administration, Nessus scans, Splunk dashboards, Deep Security policies, Drupal site maintenance, and database management. Its a broad surface area, but one thats constantly teaching me new angles of system security and enterprise operations.

One of the more exciting projects Ive taken on recently is designing a secure dropbox-style server, a system for safely transmitting sensitive documents outside the network while staying compliant with our organizations operational security requirements. Most of my day-to-day is centered on automation and systems management, but everything I learn on the sysadmin side feeds directly into my long-term cybersecurity goals.

Right now, Im studying for the CySA+ and a handful of other job-related certs, while continuing to expand my practical skills through CTFs, labs, writeups, and way too many hours of security podcasts. Im doing everything I can to level up and prepare for the eventual jump from IT into a full-time security role.

## > blog-status
I started this blog as a way to stay accountable, track my progress, and build in public as I sharpen my skills. My goal is to post here roughly every other week, sharing what Im working on from Active Directory homelabs to diving back into malware reversing (and maybe even experimenting with writing a few samples of my own).

This blog wont be a polished tutorial site. Its a logbook, a learning space, and hopefully a place to connect with others who are figuring things out just like I am. Whether youre just getting started or years into your career, I hope youll find something interesting here or maybe share something back.

Lets figure this out together.

Until next time, stay curious, and dont trust unserialized inputs.

~ spoon signing out.
