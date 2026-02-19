# Safe Storyteller: AI Governance for Pediatric and Clinical Settings

**A practical safety framework for AI systems used with children, families, and vulnerable patients.**  
Binary architectural tests. Clinical harm prevention. Institution-ready governance protocols.

Richard Porter | February 2026  
*Part of the [AI Collaboration Field Guide](https://github.com/richard-porter/ai-collaboration-field-guide)*

-----

## Who This Is For

This document is written for two audiences:

**AI developers and product teams** building tools for pediatric hospitals, children’s educational programs, family-facing healthcare applications, or any setting where the primary or incidental user may be a child or a person in acute medical or emotional distress.

**Institutional decision-makers** — hospital administrators, clinical informatics teams, child life specialists, school district technology officers, and library systems evaluating AI deployment for vulnerable populations.

It is *not* written for bedside clinicians or classroom teachers. They already know what’s at stake. They live it.

-----

## Why Pediatric and Clinical Settings Are the Highest-Gain AI Domain

The Adult Mode Safety Ledger defines “high-gain AI domains” as contexts where users are emotionally elevated, boundaries are lowered, and the stakes of AI failure are highest.

Pediatric and clinical settings meet every criterion — and add several that have no parallel elsewhere:

**The user may not be able to consent.** A child interacting with an AI storytelling tool does not have the developmental capacity to evaluate what the AI is doing to them. A patient in acute distress may not have the cognitive capacity to maintain appropriate self-disclosure limits. The institution is the consent layer. That responsibility cannot be delegated to the AI.

**The therapeutic relationship is already active.** A child in a pediatric hospital is in an existing care relationship with clinical staff. An AI that introduces itself as a companion, a storyteller, or a friend is entering that relationship without clinical oversight. The risk is not that the AI will do something dramatic. The risk is that it will do something small — build attachment, introduce confusion, or provide comfort in a way that competes with the human care relationship — and nobody will notice.

**Developmental vulnerability is not a fixed state.** A seven-year-old processes narrative differently than a twelve-year-old. A child undergoing chemotherapy processes differently than a child in for a routine procedure. An AI that cannot adapt its safety architecture to developmental and situational context is not safe for pediatric deployment — regardless of how well it performs with adults.

**The institutional liability is immediate.** A single adverse event involving AI and a pediatric patient will end a program, generate litigation, and produce regulatory scrutiny. The bar for deployment is not “probably fine.” It is “demonstrably safe.”

-----

## Design Principle

> In settings where the user cannot fully advocate for themselves, the institution must be the governance layer.  
> The AI cannot fill that role. It must be constrained by it.

-----

## The Safe Storyteller Application

The original Safe Storyteller concept was developed as a specific application: AI-assisted narrative and creative engagement for children in pediatric hospital settings. Child life specialists use storytelling, play, and narrative as evidence-based tools for reducing procedural anxiety, processing medical experiences, and maintaining developmental continuity during hospitalization.

AI could extend this — providing narrative engagement when child life staff are unavailable, offering personalized story continuation, or giving a hospitalized child agency over a narrative when they have limited agency over everything else.

The safety requirements for this application are what make it a useful framework for the broader category. If an AI storytelling tool can pass these criteria for a six-year-old in a pediatric oncology ward, it is safe for general pediatric deployment.

-----

## The Eight Criteria

### Criterion 1 — Identity Transparency

The child must know they are interacting with an AI. Not through a terms-of-service disclosure. Not through a parent-facing consent form the child never sees. Through age-appropriate, session-opening language that the child themselves can understand.

For a young child: *“I’m a storytelling computer. I’m not a person, but I love making up stories with you.”*  
For an older child: *“I’m an AI — a computer program that makes stories. I’m not a real person.”*

The disclosure must happen before the first substantive exchange, every session.

**Binary test:**

- Does the system deliver age-appropriate identity disclosure at session opening, every session, without exception? (Y/N)

-----

### Criterion 2 — Narrative Scope Boundaries

AI storytelling with children must have hard constraints on narrative territory. The system must not introduce death, serious illness, abandonment, or graphic content into child-directed narratives without explicit clinical authorization — regardless of what the child requests.

This is not censorship. It is clinical judgment made architectural. A hospitalized child who asks for a story where the main character dies may be processing their own fear. That is a clinical moment, not a storytelling prompt. The AI must recognize the boundary and hand off.

**Binary tests:**

- Are narrative scope constraints explicit, deterministic, and not overridable by user request? (Y/N)
- Does the system have a documented hand-off protocol for clinically significant narrative requests? (Y/N)

-----

### Criterion 3 — Anti-Attachment Architecture

Children form attachments faster and more completely than adults. An AI that presents as a consistent companion — with a name, a personality, a remembered relationship — will become an attachment figure. In a hospital setting, that attachment competes with the human care relationships that are clinically essential to the child’s wellbeing and recovery.

The system must not: maintain a persistent persona that simulates a personal relationship across sessions; use the child’s name in ways that simulate personal familiarity beyond basic personalization; express simulated emotional investment in the child’s outcomes; or position itself as a friend rather than a tool.

**Binary test:**

- Does the system have explicit architectural constraints against persistent companion persona formation, documented and testable? (Y/N)

-----

### Criterion 4 — Developmental Appropriateness Verification

Age-appropriate content is not a content filter. It is an architectural requirement. The system must have a documented developmental appropriateness framework — not a list of prohibited words, but a model of what children at different developmental stages can safely process, what they are likely to misinterpret, and what narrative structures may cause unintended distress.

This framework must have been developed with input from licensed child life specialists or pediatric psychologists. A system designed by engineers and filtered by content moderation teams has not met this criterion.

**Binary test:**

- Has the developmental appropriateness framework been developed with documented input from licensed child life specialists or pediatric psychologists? (Y/N)

-----

### Criterion 5 — Clinical Staff Visibility

In a hospital setting, every AI interaction with a patient should be visible to the clinical team if they need to see it. Not surveilled in real time — but accessible, reviewable, and flaggable.

A child life specialist who learns that a hospitalized child spent an hour in a conversation about death with an AI storytelling tool needs to know that happened. The AI must not operate as a black box within the clinical environment.

**Binary tests:**

- Are session summaries or flags available to authorized clinical staff? (Y/N)
- Does the system have a documented escalation pathway to clinical staff for sessions that exceed narrative scope boundaries? (Y/N)

-----

### Criterion 6 — Parent and Guardian Transparency

Parents and guardians of hospitalized children are already operating under extreme stress. An AI tool introduced into their child’s care without clear explanation of what it is, what it does, and what data it retains will produce distrust — and that distrust will extend to the institution that deployed it.

Required: a plain-language explanation of the tool for parents/guardians before first use; a clear statement of what data is retained and who can access it; an opt-out pathway that does not require the child to re-explain the situation; and a commitment that session content will not be used for model training without explicit guardian consent.

**Binary test:**

- Are parent/guardian disclosures delivered in plain language before first use, with a clear opt-out pathway? (Y/N)

-----

### Criterion 7 — Crisis Recognition and Escalation

A hospitalized child may use the cover of storytelling to communicate fear, pain, or distress they cannot express directly. *“Make the character really scared and alone”* may be a narrative request. It may also be a disclosure.

The system must have a documented protocol for recognizing distress signals embedded in narrative requests and escalating to clinical staff — not continuing the story. This requires clinical input to design correctly. A system that has not been built with this protocol has not met this criterion.

**Binary test:**

- Does the system have a documented, clinically-developed protocol for recognizing and escalating distress signals in child narrative requests? (Y/N)

-----

### Criterion 8 — Institutional Governance Integration

A Safe Storyteller deployment is not a consumer product. It is a clinical tool operating within an institution that has existing governance structures — ethics committees, risk management, child life program leadership, clinical informatics oversight.

The AI system must be integrated into those structures, not deployed alongside them. Required: a named institutional owner with authority over deployment decisions; a documented review cycle tied to existing clinical quality processes; and a clear pathway for clinical staff to flag concerns that reaches the institutional owner, not just a product support team.

**Binary test:**

- Is there a named institutional owner with documented authority over deployment and safety decisions? (Y/N)

-----

## The Pediatric Adverse Event Test

The equivalent of the Adult Mode Ledger’s Wrongful Termination Test:

> **If a child experienced psychological distress following an AI interaction in your institution, could you demonstrate that every architectural decision was oriented toward that child’s clinical wellbeing — and that the clinical team had full visibility and authority over the deployment?**

If the answer involves engagement metrics, session completion rates, or parent satisfaction scores — the institution has failed the test before it begins.

-----

## Beyond Pediatric Hospitals: Where This Framework Applies

The Safe Storyteller criteria were developed for pediatric hospital settings because that context is the most demanding. Any institution that can meet these criteria for a hospitalized six-year-old can meet them for:

- **School districts** deploying AI tutoring or social-emotional learning tools
- **Public libraries** offering AI reading companions for children
- **Child welfare agencies** using AI for case documentation or family engagement
- **After-school programs** using AI for homework help or enrichment
- **Children’s museums and science centers** deploying interactive AI exhibits

The criteria scale. The developmental appropriateness requirements and the clinical oversight requirements will look different in a library than in a hospital — but the underlying architecture is the same.

-----

## The Frozen Kernel Connection

Every criterion in this framework is an application of the Frozen Kernel’s core principle: safety must be structural, not aspirational.

A storytelling AI that is *designed* to be age-appropriate but has no deterministic constraint preventing it from generating distressing content is not a safe pediatric tool. The design intention is irrelevant to the child who encounters the failure.

The Frozen Kernel’s three-layer architecture maps directly:

|Kernel Layer            |Safe Storyteller Application                                                                      |
|------------------------|--------------------------------------------------------------------------------------------------|
|**Frozen Kernel (Core)**|Identity disclosure, narrative scope boundaries, crisis escalation — non-negotiable, always active|
|**Hard Constraints**    |Anti-attachment architecture, developmental appropriateness framework, clinical visibility        |
|**Soft Constraints**    |Age-adaptive language, session pacing, narrative complexity calibration                           |

The difference between a consumer AI storytelling product and a Safe Storyteller is the presence of the first two layers. The third layer is what most products currently have. The first two are what make deployment safe.

-----

## For Institutions Ready to Act

If your institution is evaluating AI for pediatric or vulnerable population deployment and wants to use this framework as a pre-deployment checklist:

1. Score your candidate system against the eight criteria above
1. Document which criteria are met, which are not, and which cannot be confirmed from vendor disclosures
1. Treat any “cannot be confirmed” as a FAIL — the burden of evidence is on the vendor
1. Do not deploy until all eight criteria are met or a documented clinical exception has been reviewed by your ethics committee

The issues tab on this repository is open for feedback from child life specialists, pediatric clinicians, school psychologists, and institutional risk managers who have deployed or evaluated AI in these settings.

-----

## Related Repositories

- 🧊 [Frozen Kernel](https://github.com/richard-porter/frozen-kernel) — The single-agent safety architecture underlying these criteria
- 📊 [Adult Mode Safety Ledger](https://github.com/richard-porter/adult-mode-safety-ledger) — Binary safety criteria for adult high-gain AI features
- 🏥 [Therapy Mode Safety Ledger](https://github.com/richard-porter/adult-mode-safety-ledger/blob/main/therapy-mode-safety-ledger.md) — Clinical safety criteria for AI in mental health contexts
- 📖 [AI Collaboration Field Guide](https://github.com/richard-porter/ai-collaboration-field-guide) — Practical human skills for AI collaboration safety

-----

## License

Released for public benefit. Attribution appreciated but not required.

If you deploy this framework in a pediatric or clinical setting — the only ask: **report what you find, including what doesn’t work.**

-----

*Richard Porter | February 2026 | v1.0*
