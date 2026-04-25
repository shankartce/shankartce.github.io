Title: Publishing Foundry Agents to Microsoft Teams and Copilot: What Developers Need to Know
Date: 2026-04-25
Category: Azure Course AI-103T00-A
Tags: Microsoft 365, Azure AI, Microsoft Foundry, Work IQ, AI Agents
Slug: integrate-agent-with-microsoft-365

## TL;DR

Microsoft’s **Integrate your agent with Microsoft 365** module teaches how to publish a Foundry agent into **Microsoft Teams** and **Microsoft 365 Copilot**, use **Work IQ** to ground the agent in workplace data, and test/troubleshoot the integrated experience. The module is intermediate-level, spans **9 units**, and is aimed at developers, AI engineers, and solution architects who already know the basics of Microsoft Foundry. 
## Why this matters

Building an AI agent inside a cloud console is one thing. Getting that agent into the places people actually work is where the value shows up. Microsoft’s module is focused on exactly that: publishing Foundry agents to **Teams** and **Microsoft 365 Copilot**, then grounding them in **Work IQ** so they can use workplace context instead of guessing. The training also includes testing and troubleshooting integrated agents, which is what turns a demo into a usable enterprise capability. 

That is the real shift here. Once an agent lives inside Microsoft 365, it is no longer just a chatbot. It becomes part of the employee workflow: answering questions in Teams, supporting Copilot scenarios, and pulling from work context across the Microsoft ecosystem. Microsoft’s Foundry agent platform is built for this kind of deployment, and the docs position Foundry Agent Service as a managed platform for building, deploying, and scaling agents with hosting, scaling, identity, observability, and enterprise security handled for you. 

## Background: what the module is teaching

The Microsoft Learn module is clearly targeted at practitioners. It is marked **Intermediate** and lists **AI Engineer**, **Developer**, and **Solution Architect** as the intended audience. The prerequisites include familiarity with Azure, experience building Foundry agents, and a **Microsoft 365 subscription with access to Teams**. The learning objectives are also very concrete: explain publishing options, publish from the Foundry portal to Teams and Microsoft 365 Copilot, use Work IQ to access Microsoft 365 data, and test and troubleshoot the integrated agent. 

That tells you the module is not just about theory. It is about shipping an agent into the Microsoft 365 surface area in a controlled way. Microsoft also says you can approach Microsoft 365 agent extensibility in more than one way: a low-code path with Copilot Studio, a pro-code path with the Microsoft 365 Agents Toolkit, or integration of an existing Foundry agent into Microsoft 365. The module sits in that pro-code / Foundry integration lane.

## Core concept 1: Microsoft 365 is the delivery surface

A lot of AI projects over-focus on the model and under-focus on distribution. Microsoft’s integration story is helpful because it makes the delivery surface explicit: **Teams** and **Microsoft 365 Copilot**. The publish flow in Foundry is designed around those channels, including an option to publish directly from the Foundry portal or download and customize a manifest for manual sideloading in Teams. Microsoft also states that publishing creates or uses an **Azure Bot Service** resource and requires the `Microsoft.BotService` provider to be registered in the subscription.

That matters because the last mile is where adoption happens. An agent that employees can reach where they already collaborate is much easier to use than an isolated web app. In practice, Teams is a particularly strong entry point because it collapses the “open another tool” tax that kills adoption for many enterprise AI pilots. That is an inference, but it follows directly from Microsoft’s emphasis on publishing into Teams and Microsoft 365 Copilot instead of leaving the agent in a standalone portal. 

## Core concept 2: Foundry gives you two main publishing paths

Microsoft’s publish guide lays out two practical routes. You can **publish directly from Foundry** to Microsoft 365 and Teams, or you can **download and customize** the agent manifest and then sideload it in Teams. For direct publish, you select a version, provide metadata such as name, version, description, and developer info, and choose who can use the agent. For organization-wide publishing, a Microsoft 365 admin must review and approve the request in the admin center. 

That publishing metadata matters more than it looks like at first glance. Microsoft warns not to include secrets or sensitive information in metadata fields because they are visible to users. It also says the publish flow supports updating display properties later, and that versioning can auto-increment if not manually changed. Those are small details, but they are exactly the sort of productization details that separate an internal prototype from a responsibly distributed enterprise app. 

## Core concept 3: Work IQ is the knowledge layer for Microsoft 365 context

The headline feature in this module is **Work IQ**. Microsoft says you can use Work IQ to access Microsoft 365 data in your agents, and the related documentation describes Work IQ as the intelligence layer that grounds Microsoft 365 Copilot and agents in real-time shared context across the organization. Work IQ is built on **Data, Memory, and Inference**, and Microsoft says it connects signals from files, emails, meetings, chats, and business systems to help agents deliver insights, recommendations, and actions aligned to the reality of the business. 

That is the real difference between a generic assistant and a workplace assistant. A generic assistant may know how to summarize. A Work IQ–grounded agent can reason with live organizational context. Microsoft also notes that Work IQ MCP servers are secure, scalable, and compliant by design, with centralized governance, scoped permissions, policy enforcement, runtime observability, and continuous evaluation. It is also explicit that using Work IQ MCP servers requires a **Microsoft 365 Copilot license**. 

For a practitioner, the pattern is obvious: keep the agent’s general reasoning in Foundry, and use Work IQ to supply the context that makes answers relevant to the company instead of merely plausible. That is what enterprise users actually need.

## Core concept 4: the Microsoft 365 Agents Toolkit is the advanced pro-code path

Microsoft’s Microsoft 365 extensibility docs say that developers can use **Visual Studio** or **Visual Studio Code** with the **Microsoft 365 Agents Toolkit** to build custom engine agents, and that this toolkit provides templates, debugging, and streamlined deployment workflows. The same docs say you can integrate an existing Foundry agent with Microsoft 365, and that the approaches differ by complexity, skill set, and scenario fit. 

That is a useful architectural choice to know about. If you want the fastest path, publishing directly from Foundry is attractive. If you need more control over the integration layer, the Agents Toolkit becomes the better fit. Microsoft even documents both routes in the same ecosystem: direct publish from Foundry, or connect an existing Foundry agent to Microsoft 365 through a proxy app built with the Agents Toolkit.

## A practical architecture pattern

A clean mental model for this integration looks like this:

```text id="c7x8hy"
User in Teams or Copilot
  → Microsoft 365 surface
  → Foundry agent
  → Work IQ context / Microsoft 365 data
  → Agent reasoning + tool use
  → Response back into Teams or Copilot
```

That flow matches the module’s scope: publish the Foundry agent to Microsoft 365, use Work IQ to access Microsoft 365 data, and test the integrated experience. It also aligns with Microsoft’s broader Foundry agent model, where an agent is an AI application that uses a large language model to reason and take actions across multiple steps, rather than just generating text. 

In practical terms, the agent is doing three jobs at once: interpreting the user request, pulling in work context, and deciding whether it needs to answer, act, or escalate. That is why the integration layer matters so much.

## Practical use cases

One strong use case is an **employee helpdesk agent**. In Teams, the agent can answer policy questions, explain internal processes, or help employees find the right resources. With Work IQ, those answers can be grounded in files, messages, meetings, and business systems rather than in a disconnected knowledge base. Microsoft’s docs explicitly position Work IQ around organizational context across Microsoft 365 and business systems. 

Another strong use case is a **Copilot companion for internal operations**. A finance, procurement, or IT operations agent can live inside Microsoft 365 Copilot and provide context-aware support that is aware of the employee’s work environment. This is especially valuable because Microsoft’s module is specifically about publishing to Microsoft 365 Copilot and Teams, not only to a separate app. 

A third case is a **workflow-assist agent** for busy professionals. Think of a manager assistant that summarizes meeting context, points to relevant files, and drafts follow-up steps. Work IQ’s Data, Memory, and Inference model is designed to support exactly that kind of contextual, ongoing assistance. 

## Testing and troubleshooting are part of the product

Microsoft explicitly includes **test and troubleshoot agents integrated with Microsoft 365** as a learning objective. The publish guidance also recommends testing thoroughly in the Foundry portal before publishing and ensuring the active version is the one consumers should interact with. If you publish to an organization, admin approval and tenant app policies also become part of the rollout path. 

That is a valuable reminder: M365 integration is not just a packaging step, it is a release-management step. You are shipping into an environment with identity, policy, and admin controls. Microsoft’s docs make that clear by requiring Azure Bot Service provisioning, optional manifest customization, and admin-center approval for broader distribution. 

## Challenges and trade-offs

The biggest trade-off is governance versus speed. Direct publish from Foundry is convenient, but organization-wide deployment still flows through Microsoft 365 admin approval and tenant policy controls. That is the correct enterprise posture, but it also means teams need to plan for release coordination early. 

Another trade-off is context quality. Work IQ is powerful, but it only helps if the underlying organizational data is relevant and permissioned correctly. Microsoft emphasizes grounded context, scoped permissions, policy enforcement, and observability for Work IQ MCP servers, which is a strong hint that the platform expects you to think carefully about data access and trust boundaries.

There is also an architectural choice between the fast path and the customizable path. Direct publishing from Foundry reduces setup overhead, while the Agents Toolkit gives you more control over debugging, deployment, and multi-environment work. The right choice depends on whether your priority is quick adoption or deeper customization. Microsoft explicitly presents both options. 

## Future outlook

The direction is pretty clear: Microsoft is making agents feel native to the work environment, not just attached to it. Foundry handles the agent runtime, Microsoft 365 handles the user surface, and Work IQ supplies the contextual intelligence in between. Microsoft’s broader agents ecosystem also points toward more governance, more standardized tool access, and more lifecycle control through systems like Agent 365. 

My read is that the future of enterprise AI in Microsoft land is not “one super chatbot.” It is a set of integrated agents embedded in the tools people already use, with clear governance and shared context. This module is one of the clearest examples of that direction. That is an inference, but it is strongly supported by the way Microsoft structures the learning path and the surrounding docs. 

## Conclusion

If you are building AI agents for real users, Microsoft 365 is where many of them will spend their day. This module shows how to bring a Foundry agent into that world, ground it with Work IQ, and publish it in a way that respects enterprise controls, versioning, and testing. The key idea is simple: the agent becomes much more valuable when it can meet people where they already work.

The practical takeaway is this: **build the agent in Foundry, ground it with Work IQ, publish it into Teams or Copilot, and test it like production software**. That is how an AI demo becomes a workplace tool.
