# Slack Message Classifier

An AI-powered tool that reads recent messages in a Slack channel, decides what each one needs (Question, Action Item, Urgent, or FYI), and automatically reacts with the right emoji — turning a busy channel into something already triaged and prioritized.

## What it does

1. Connects securely to a real Slack workspace
2. Reads recent messages from a channel
3. Sends each one to Claude, which decides how to classify it and explains why
4. Automatically adds a real emoji reaction based on that decision — no manual sorting needed

## Why this matters

This is the same core pattern as my [Gmail Triage Agent](https://github.com/yashhh004/gmail-triage-agent), applied to a completely different tool. Building it a second time, on a different API, was intentional — it proves the underlying approach (read data → have Claude decide → take a real action) generalizes, rather than being a one-off trick tied to Gmail specifically.

## Built with
- Claude API (Anthropic) — for classification and reasoning
- Slack API (Bot token, Web API) — for reading messages and adding reactions
- Python (Google Colab)

## A few things I paid attention to
- Started with read-only permissions (`channels:history`, `channels:read`), only added `reactions:write` once I actually needed to take real action
- Handled empty/system messages (like "user joined the channel") gracefully rather than crashing
- Kept bot tokens out of the code — placeholders only

## Example output
