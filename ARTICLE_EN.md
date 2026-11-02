# I Mapped the Agent-Control Market Into One Architecture. The Hard Part Is Not Coverage - It Is Closure.

TRINITY existed before this market study. I did not derive it from AI-safety papers, NIST frameworks, or vendor products.

I did the reverse: **I took an existing system architecture and applied it to autonomous AI-agent control.** Then I mapped real market mechanisms, standards, and research onto the resulting functional structure.

My claim is deliberately strong:

> **This public functional architecture is sufficient as a control frame for AI-agent systems.**

That claim can be challenged. That is why I am publishing the map, evidence, and a concrete counterexample protocol.

## Nine functions of one control architecture

At the public level, the architecture distinguishes nine functions:

1. **Scope / Inventory** - what objects and boundaries exist.
2. **Trace / Integrity** - what happened and whether the evidence can be trusted.
3. **Distinguish / Triage** - what condition or risk is actually present.
4. **Adversarial Validation** - whether the control survives deliberate pressure.
5. **Admission / Authority** - who or what may act, where, and under what authority.
6. **Interrupt / Hold** - how action is paused, blocked, or retained.
7. **Independent Assurance** - how the result is checked without relying only on the same control path.
8. **Contain / Shutdown / Notify** - how impact is localized and activity is stopped or escalated.
9. **Repair / Recover / Re-admit** - how a system returns to an admissible state and receives permission to continue.

These are functions, not a linear pipeline. They can operate simultaneously and can be decomposed when a coarse function looks "covered" but closure remains uncertain.

![Public AI-agent control architecture](assets/control-architecture-map.svg)

## First observation: the market already covers most functions

Across Microsoft, NIST, OWASP, AISI, Redwood-related work, Guidelight, and other approaches, the market is not empty. Most top-level functions already have real mechanisms associated with them.

I then changed the sample and repeated the mapping against AWS, Google, IBM, Cisco, OpenAI, and Okta.

Coverage changed. The top-level structure did not.

**The second sample did not require another top-level control function.**

This does not mean every product solves its assigned function completely. It means materially different technologies continue to fit the same functional frame.

## A green cell is not closure

Recent work in October 2026 makes "we have a control" an insufficient statement.

OpenAI explicitly separates monitoring coverage from intervention capability: a system can detect a concern without automatically terminating execution in every interface or integration path.

External work by METR and Redwood found bypasses and coverage gaps in an earlier version of OpenAI's monitoring system, including boundaries where monitoring did not fully cover the trajectory.

Anthropic reported attack patterns involving agent handoffs, context compaction, and agent-generated data, showing that local controls can fail across context boundaries.

Research on distributed revocation makes the distinction even sharper: receiving and storing a revocation signal does not guarantee that every executor has actually stopped authorizing the action.

That leads to the central formula:

> **Detected != Decided != Enforced != Effect stopped != State proved != Next action permitted.**

## The problem is no longer the absence of controls

The market is moving toward integrated systems. SentinelOne now markets Agentic Detection and Response as a connected layer spanning discovery, permissions, observation, and isolation. AWS, Google, IBM, Cisco, OpenAI, and Okta also combine multiple control functions in their stacks.

So I am not making the weaker claim that "the market has isolated tools and I am the first person to combine them."

The stronger claim is:

> **Integration of mechanisms does not, by itself, prove closure of control.**

A system can detect a problem, decide to intervene, send a control command, and even receive a positive receipt while an effect still continues through another executor, context, or branch.

## What I mean by Control Closure

Control is closed when we can establish not only that a control command existed, but the full required relationship around it:

- what was being controlled;
- what state was detected;
- who had authority to decide;
- whether the decision was actually enforced;
- whether the unwanted effect stopped;
- what evidence proves that state;
- which system version that evidence belongs to;
- what became permissible afterward;
- whether re-admission is required before continuation.

At this point the map stops being a vendor catalog.

It becomes a way to diagnose **where control actually breaks**.

## Three uses of the same architecture

### 1. Classifier
A new mechanism can be placed relative to known functions so we can identify what control problem it actually solves.

### 2. Diagnostic architecture
A seemingly "green" function can be decomposed until we can see whether its internal obligations, evidence, and transitions are actually closed.

### 3. Basis for an executable control layer
The same functions can be formalized as inputs, conditions, decisions, state evidence, and permission for the next transition.

That third use is the engineering direction I am most interested in now.

## I claim sufficiency - so the useful response is to break it

I am not publishing this architecture to ask whether people like it.

I am claiming that the top-level functional frame is sufficient for AI-agent control.

If that is wrong, the useful counterexample is concrete:

- a necessary control function that is absent from the map;
- a real system transition the architecture cannot express;
- or a control system that requires a fundamentally different relation between functions.

A new label for an existing mechanism is not a counterexample.

If a real missing function appears, the architecture should change. I will publish that result.

## What I am not publishing

The public layer includes functions, relationships, market mappings, and externally checkable results.

The internal TRINITY computation that derives placement, depth, re-selection, and transition authority is not part of the public artifact.

The goal is to make the result falsifiable without publishing the engine.

## What next

If you have a public counterexample, bring the mechanism and a primary technical source.

If you have a private agent stack and want to know where control breaks, that is a separate architecture review.

If you are interested in turning this architecture into an executable control layer, that is the technical partnership I am currently looking for.

I am less interested in agreement than in the point where the architecture fails.
