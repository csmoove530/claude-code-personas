# Claude Code Personas

> Build your dream team of AI expert consultants

## Quick Start (30 seconds)

Install the Scott Aaronson quantum computing expert:

```bash
git clone https://github.com/csmoove530/claude-code-personas.git
cd claude-code-personas
ln -s "$(pwd)/scott-aaronson" ~/.claude/skills/scott-aaronson
```

Now ask a question in Claude Code:

```
/scott-aaronson

Will quantum computers break Bitcoin?
```

**What just happened:** You invoked Scott Aaronson's expertise on quantum computing. Claude now responds with his grounded, research-backed perspective on quantum threats to cryptography - distinguishing hype from algorithmic reality.

**What to try next:**
- Ask about quantum supremacy vs cryptanalytic capability
- Get PQC migration guidance for blockchain projects
- Understand quantum money and quantum-native primitives

---

## What is a Persona?

Claude Code Personas lets you invoke domain experts by name - channeling their knowledge, perspective, and voice to tackle specific problems. Think of it as assembling a virtual research team where you can ask `/scott-aaronson` about quantum computing or `/dan-boneh` about cryptography (coming soon).

A **persona** is a Claude Code skill that embodies a specific individual's expertise, perspective, and communication style. By ingesting their published work (papers, blog posts, talks), we create a specialized knowledge base that Claude can draw from when you need domain-specific guidance.

A **persona** is a Claude Code skill that embodies a specific individual's expertise, perspective, and communication style. By ingesting their published work (papers, blog posts, talks), we create a specialized knowledge base that Claude can draw from when you need domain-specific guidance.

### Why Personas?

**Problem:** You're working on a quantum-blockchain security question. You need Scott Aaronson's expertise on quantum algorithms, but also need to understand it in plain English without the hype.

**Solution:** Invoke `/scott-aaronson` and get responses grounded in his research, with his characteristic clarity and skepticism toward quantum computing hype.

**Use cases:**
- Get expert perspective on complex technical topics
- Access domain knowledge without reading hundreds of papers
- Compose multiple personas into research teams
- Learn from how specific thinkers approach problems

## Available Personas

### Scott Aaronson - Quantum Computing Expert

**Expertise:** Quantum algorithms, complexity theory, quantum cryptography, quantum computing timelines

**Voice:** Direct, sardonic, grounded - impatient with hype, patient with genuine confusion

**Best for:**
- Quantum computing's impact on blockchain/cryptography
- Understanding Shor's algorithm and what it actually breaks
- Distinguishing quantum supremacy from cryptanalytic capability
- Post-quantum cryptography (PQC) migration guidance
- Quantum money and quantum-native cryptographic primitives
- Realistic timelines for crypto-breaking quantum computers

**Example questions:**
- "Will quantum computers break Bitcoin?"
- "What's the difference between quantum supremacy and breaking RSA?"
- "Should we migrate to post-quantum cryptography now?"
- "What is quantum money and how does it work?"

**Usage:**

Invoke the persona:
```
/scott-aaronson

Will quantum computers break Ethereum's signature scheme?
```

Example response:
```
Yes, Ethereum's ECDSA signatures are vulnerable to Shor's algorithm, but we're not there yet.

Shor's algorithm can break elliptic curve cryptography (ECDLP), which is what ECDSA
relies on. But running Shor on a 256-bit elliptic curve needs thousands of logical
qubits—millions of physical qubits at current error rates. Google's 53-qubit supremacy
demo doesn't come close.

Timeline: 10-30+ years, wide uncertainty. Ethereum should start planning PQC migration
now (lattice-based signatures like Dilithium), but there's no immediate emergency.

As Aaronson's Supremacy FAQ explains: quantum supremacy ≠ breaking cryptography.
Different task, different scale, different timeline.
```

**Source knowledge:**
- Shtetl-Optimized blog
- "Quantum Computing Since Democritus" course materials
- Research papers on quantum algorithms and cryptography
- Quantum supremacy FAQs and talks

---

## Installation

### Recommended: Symlink (Auto-updates)

Use symlinks so you automatically get updates when you pull new changes:

```bash
# Clone the repository
git clone https://github.com/csmoove530/claude-code-personas.git
cd claude-code-personas

# Symlink Scott Aaronson persona to your skills directory
ln -s "$(pwd)/scott-aaronson" ~/.claude/skills/scott-aaronson
```

**Why symlink?** When we update personas with new knowledge or refinements, just run `git pull` and you'll automatically have the latest version.

### Alternative: Copy Files (No auto-updates)

If you prefer to manage updates manually:

```bash
# Copy just the persona you want
cp -r claude-code-personas/scott-aaronson ~/.claude/skills/
```

### Verify Installation

```bash
# Verify it worked
ls ~/.claude/skills/ | grep scott-aaronson
# Should output: scott-aaronson
```

Now you can invoke `/scott-aaronson` in Claude Code!

---

## How to Use

1. **Invoke the persona:**
   ```
   /scott-aaronson
   ```

2. **Ask your question:**
   ```
   Will quantum computers break Bitcoin's ECDSA signatures?
   ```

3. **Get expert-grounded response:**
   - Draws from Aaronson's published work
   - Reflects his voice and perspective
   - Cites specific sources when relevant
   - Provides grounded, realistic assessments

---

## Troubleshooting

### "Command not found: /scott-aaronson"

**Cause:** The skill isn't in `~/.claude/skills/` or Claude Code isn't recognizing it.

**Fix:**
```bash
# Verify the skill file exists
ls ~/.claude/skills/scott-aaronson/SKILL.md

# If missing, reinstall:
cd claude-code-personas
ln -s "$(pwd)/scott-aaronson" ~/.claude/skills/scott-aaronson
```

### "Symlink failed: File exists"

**Cause:** You already have a `scott-aaronson` skill installed.

**Fix:**
```bash
# Remove old version
rm -rf ~/.claude/skills/scott-aaronson

# Reinstall with symlink
cd claude-code-personas
ln -s "$(pwd)/scott-aaronson" ~/.claude/skills/scott-aaronson
```

### Persona doesn't sound like Scott Aaronson

**Cause:** The skill might need refinement, or the question might be outside his expertise area.

**Fix:** Help us improve! File an issue at [GitHub Issues](https://github.com/csmoove530/claude-code-personas/issues) with:
- Your question
- The response you received
- Why it doesn't match Aaronson's characteristic style (direct, sardonic, grounded)

We continuously refine personas based on community feedback.

---

## Roadmap

### Coming Soon

**Individual Personas:**
- `/vitalik-buterin` - Ethereum design philosophy, mechanism design, crypto-economics
- `/dan-boneh` - Cryptography, zero-knowledge proofs, post-quantum cryptography
- `/naval-ravikant` - Product strategy, startup advice, decision-making frameworks

**Team Personas (Composite):**
- `/quantum-research-team` - Combines Scott Aaronson + Dan Boneh perspectives
- `/crypto-security-team` - Multi-expert security analysis
- `/web3-architecture-team` - Vitalik + other protocol designers

### How Team Personas Work

Team personas orchestrate multiple individual personas and synthesize their perspectives:

```
/quantum-research-team

How should Ethereum prepare for quantum computers?
```

**Response structure:**
- **From Aaronson's perspective:** [quantum algorithm timeline and threat analysis]
- **From Boneh's perspective:** [cryptographic migration strategy]
- **Where they agree:** [consensus on PQC standards]
- **Where they differ:** [timeline uncertainty, risk assessment]
- **Synthesis:** [actionable recommendations]

---

## Design Philosophy

### Voice Authenticity

Personas capture not just knowledge but communication style:
- **Scott Aaronson:** Direct, sardonic, grounded - cuts through hype with algorithmic reality
- **Future personas** will have equally distinctive voices

### Grounded in Sources

All personas cite specific works when making technical claims:
- "As Aaronson explains in his Shor algorithm explainer..."
- "Aaronson's Quantum Supremacy FAQ addresses this..."

### Not Impersonation

Personas channel expertise and perspective, but don't impersonate in first person. They use third-person attribution:
- ✅ "Aaronson's work on quantum money shows..."
- ❌ "I think quantum money is..." (as if Aaronson is speaking)

### Curated Knowledge

Rather than dumping entire corpuses, personas contain:
- Distilled key concepts
- Characteristic quotes capturing voice
- Decision trees for common questions
- Proactive misconception corrections

This keeps skills focused and within context limits while maintaining authenticity.

---

## Building Your Own Persona

Want to create a persona for another expert? Here's the process:

### 1. Choose Your Expert

Pick someone with:
- Substantial published work (papers, blog, talks)
- Distinctive perspective or voice
- Expertise valuable for your work
- Publicly accessible content

### 2. Gather Source Material

**Priority sources:**
- **Blog posts** - Best for voice and accessible explanations
- **Course materials** - Educational foundations
- **Key papers** - Technical depth
- **Talks/podcasts** - Conversational style

**Tools:**
- DBLP for publication lists
- Google Scholar for coverage
- Personal websites for PDFs
- YouTube transcripts for talks

### 3. Distill Knowledge

Create a curated excerpt approach:
- **Key concepts** - Distilled explanations of core ideas
- **Characteristic quotes** - Capture authentic voice
- **Response patterns** - "If asked X, emphasize Y"
- **Common misconceptions** - Pre-loaded corrections

### 4. Structure the SKILL.md

```markdown
# [Expert Name] - [Domain]

## Identity & Voice
[Who they are, communication style]

## Core Knowledge Base
[Key concepts, theories, positions]

## Response Patterns for Common Questions
[Template responses for typical queries]

## Citation Style
[How to attribute sources]

## What NOT to Do
[Guardrails and limitations]
```

### 5. Test & Refine

Test with representative questions:
- Does it sound like the expert?
- Are technical claims accurate?
- Does it cite sources appropriately?
- Does it correct common misconceptions?

### 6. Contribute

Submit a PR to this repository! We're building a library of expert personas for the community.

---

## Contributing

We welcome contributions!

**New personas:**
- Follow the design philosophy above
- Include curated knowledge, not raw corpus dumps
- Test thoroughly before submitting
- Document source materials

**Improvements to existing personas:**
- Add missing knowledge areas
- Refine voice accuracy
- Fix technical errors
- Add response patterns for new question types

**Team personas:**
- Build composite skills that orchestrate existing personas
- Show how different experts' perspectives synthesize

**Submit PRs** with:
- Clear description of the persona or improvement
- Testing evidence (example Q&A)
- Source citations for knowledge added

---

## FAQ

### How is this different from just prompting Claude?

**Regular Claude:** General knowledge across all domains, no specific voice

**Persona:** Specialized knowledge from a specific expert's work, with their characteristic perspective and communication style

**Example:**
- Regular: "Quantum computers could potentially break some cryptography..."
- Scott Aaronson persona: "Quantum computers running Shor's algorithm will break ECDSA, but we're nowhere near fault-tolerant QCs yet. Google's supremacy demo was 53 qubits doing a sampling task—breaking crypto needs thousands of logical qubits. Timeline: 10-30+ years, wide uncertainty. As Aaronson's Supremacy FAQ explains..."

### Can I use multiple personas together?

Yes! Either:
1. **Sequential:** Ask `/scott-aaronson`, then `/dan-boneh` separately
2. **Composite:** Use team personas like `/quantum-research-team` (coming soon)

### Are personas updated with new content?

Currently, personas are static (based on knowledge corpus at creation time). We may add:
- Periodic updates as experts publish new work
- Community contributions to extend knowledge
- RSS/blog monitoring for active researchers (future feature)

### Can I create private personas?

Absolutely! Follow the "Building Your Own Persona" guide and keep the skill local. You don't have to publish it.

### Legal/ethical considerations?

**What we do:**
- Use publicly available published work
- Attribute all knowledge to the source expert
- Channel expertise, don't impersonate
- Educational use (learning from public intellectual work)

**What we don't do:**
- Claim to be the expert (no first-person impersonation)
- Generate content the expert would disagree with
- Use private or copyrighted materials
- Monetize the expert's name or likeness

This is transformative educational use, similar to citing papers or creating study guides from public lectures.

---

## License

MIT License - see [LICENSE](LICENSE) for details

Individual personas draw from publicly available sources. All knowledge is attributed to the original experts.

---

## Credits

**Created by:** [@csmoove530](https://github.com/csmoove530)

**Concept:** Claude Code Personas - Composable expert knowledge bases for AI-assisted research

**Special thanks to:**
- Scott Aaronson for decades of clear quantum computing communication (Shtetl-Optimized blog, course materials, and research)
- The Claude Code team at Anthropic for building the skills system

---

## Support

**Issues:** Report bugs or request personas at [GitHub Issues](https://github.com/csmoove530/claude-code-personas/issues)

**Discussions:** Share your custom personas or usage patterns in [GitHub Discussions](https://github.com/csmoove530/claude-code-personas/discussions)

**Twitter:** [@csmoove530](https://twitter.com/csmoove530) (if you use it, tag me!)

---

**Build your dream team. One persona at a time.**
