---
layout: post
title: "Language Models in Robotics: Teaching a Robot Arm to Play Chess"
date: 2026-05-20 23:33:00 +0200
categories: robotics llm chess
excerpt: "A robotics project that combines large language models, chess move validation, and robotic manipulation."
---

Large language models are very good at understanding language, following instructions, and using world knowledge in flexible ways.

In this project, I explored that question through a chess-playing robotic system. The idea was to let a language model reason about chess moves at a high level, then translate those moves into real pick-and-place actions for a robotic arm.

## System overview

![Environment setup]({{ '/assets/img/posts/language-models-robotics/board-set-up.png' | relative_url }})
<div class="caption">The robot chess environment used in simulation.</div>

The system combines an LLM decision layer, legality checks using python-chess, and a motion layer that maps commands to 3D robot actions.

## Move selection

![Combined scoring for a pawn move]({{ '/assets/img/posts/language-models-robotics/wp4d4.png' | relative_url }})
<div class="caption">A candidate move is chosen by combining LLM preference with affordance validation.</div>

The key idea is that the robot should never execute a move just because it sounds plausible in language. Every move must also be legal and physically executable.

## From text to action

![Pick example]({{ '/assets/img/posts/language-models-robotics/pick-example.jpg' | relative_url }})
<div class="caption">Example of the pick stage in the robot action pipeline.</div>

![Place example]({{ '/assets/img/posts/language-models-robotics/place-example.jpg' | relative_url }})
<div class="caption">Example of the place stage after command parsing and coordinate mapping.</div>

Once validated, the command is converted into low-level pick-and-place instructions for the robot arm.

## CLIPORT experiments

![CLIPORT result]({{ '/assets/img/posts/language-models-robotics/cliport-test.png' | relative_url }})
<div class="caption">Visual grounding experiments using CLIPORT for chess piece manipulation.</div>

The project also explored a vision-language pipeline using CLIPORT for visually grounded manipulation tasks.