# Rounds of Questions Skill (a.k.a. rich-elicitation)

A Claude AI skill for asking clarifying questions and resolving ambiguity before starting tasks. Multi-round elicitation, automatic question grouping, and intelligent stopping rules for better first-draft outputs.

## What it does

Most AI responses fail not because the model can't do the task, but because it silently picked one interpretation out of several valid ones. This skill fixes that by making Claude stop, assess what's genuinely unknown, and ask targeted questions before diving in.

It activates when a request has **multiple unanswered dimensions, each with several reasonable answers** — things like unknown audience, unclear tone, undefined scope, or competing strategic directions. If two or more of those are true at once, Claude asks before it acts.

## Problem: Why this matters

- **Bad first drafts** — AI picks defaults instead of asking your preferences
- **Wasted revision cycles** — you reject output because intent was never clarified
- **Scope creep** — tasks expand because success criteria weren't defined upfront
- **Ambiguity ignored** — AI doesn't flag when a task could go multiple directions

This skill solves all four by enforcing intelligent question-asking upfront.

## Features

- **Multi-round questioning** — if Round 1 answers unlock new unknowns, Claude follows up naturally (up to 3 rounds max)
- **Recommended options** — Claude marks its suggested choice on every question so you're never staring at a blank set of options
- **Grouped questions** — up to 3 related questions per prompt, not 6 separate interruptions
- **Smart stopping** — Claude stops asking once it has enough context; minor unknowns get a stated assumption, not another round

## When it triggers

**Activates on:**
- Writing tasks (emails, reports, blog posts, proposals, sales copy)
- Planning and strategy (roadmaps, projects, timelines)
- Design and technical decisions (architecture, tool selection, feature scope)
- Recommendations and research (analysis, comparisons, research syntheses)
- Creative work (brainstorming, ideation, content creation)
- Any open-ended request with 2+ ambiguous dimensions

**Does not trigger on:**
- Factual lookups and knowledge questions
- Math and calculations
- Clearly-scoped requests with no ambiguity
- Simple, transactional tasks with one right answer

## Installation

1. Clone or download this repo
2. Copy `SKILL.md` to your Claude skills directory: `~/.claude/skills/rich-elicitation/`
3. Restart Claude — the skill will be auto-discovered

Or if you manage skills as part of a custom Claude installation, add to your `available_skills` config.

## This tool is useful for:

- Clarifying ambiguous prompts
- Multi-turn question generation
- Reducing AI revision cycles
- Improving first-draft outputs
- Structured elicitation
- Requirement gathering
- AI prompt engineering

## How rounds work

| Round | Purpose | Max questions |
|---|---|---|
| 1 | Blocking questions — shape the entire output | 3 |
| 2 | Follow-ups unlocked by Round 1 answers | 3 |
| 3 | Final details — used sparingly | 2 |

After Round 3, Claude proceeds and states any remaining assumptions explicitly.
