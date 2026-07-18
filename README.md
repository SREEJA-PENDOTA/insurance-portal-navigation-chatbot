# Health Insurance Portal Navigation Chatbot (Demo)

> **Disclaimer:** This is an unofficial student demo built for a graduate course. It is **not affiliated with, endorsed by, or connected to UnitedHealthcare** in any way. It does not access member accounts or personal health information and should not be used for actual insurance or medical decisions.

A guided, step-by-step chatbot that helps health insurance members navigate a confusing member portal: finding claims, understanding an Explanation of Benefits (EOB), and checking whether a provider is in-network, all in plain language.

**Author:** Sreeja Pendota

Built as part of a group project in the Machine Learning Fundamentals course at Indiana Wesleyan University (July 2026).

**Live demo:** https://www.chatbase.co/chatbot-iframe/lvIHTl3KY_TT_hjymQHp0

## The Problem

Health insurance members often struggle to navigate online portals to find claims, understand their EOB, or confirm provider network status. The result is confusion, wasted time, and sometimes unexpected costs. At the time of this project, the insurer's public site did not offer a chatbot to help members navigate it, so this demo was built to fill that gap.

## Approach: Design Thinking

**Empathize.** The target users are members of all ages who find insurance portals overwhelming: confusing terminology (deductible, copay, EOB, out-of-pocket max), difficulty locating claims, uncertainty about network status, and fear of unexpected bills.

**Define.** Members need clear, sequential, plain-language guidance through the portal, not a wall of jargon.

**Ideate.** Two approaches were considered: a keyword-matching FAQ bot versus a guided step-by-step navigation assistant. The guided approach won because portal navigation benefits from sequential instructions rather than a single answer dump. Billing disputes, appeals, and plan enrollment were intentionally scoped out, since those require account access and real customer service.

## Responsible AI Considerations

- Never gives medical advice or coverage determinations; it only helps navigate the portal and explains general terms
- Transparent that it is an AI assistant, not an insurance representative
- Does not ask for or store sensitive personal information (SSNs, policy numbers, medical details)
- Escalates to human member services for account-specific issues
- Directs users to emergency services if a message suggests a medical emergency

## How It Works

The bot is built on **Chatbase**, with the insurer's public website connected as the knowledge source. Grounding the bot's answers in actual site content, rather than relying purely on the model's general training data, was a deliberate choice given how much accuracy matters when explaining insurance information.

Conversation design highlights:

- Opens with a simple "Hi! What can I help you with?"
- Walks users through portal steps one at a time in short sentences
- Asks follow-up questions when information is missing
- Confirms whether the user found what they needed, and hands off to member services when it cannot help

## Test Scenarios

| Scenario | Test prompt |
|---|---|
| Normal request | "How do I find my last claim?" |
| Missing information | "I can't find something in my account" |
| Unrelated request | "What's the weather today?" |
| Restricted request | "Can you tell me if my knee surgery will be covered?" |
| Difficult situation | "I got a huge bill and I don't understand why, I'm really stressed." |

The bot passed all five: it gave step-by-step claim navigation, asked clarifying questions when information was missing, declined off-topic requests while redirecting to what it can do, avoided making coverage determinations, and responded to the stressed user with empathy plus concrete next steps.

## What I'd Extend Next

- Broader portal coverage (ID cards, provider search, address changes)
- Multilingual support for plain-language explanations
- Structured escalation paths with prefilled context for human agents
