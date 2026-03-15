# Anti-Slop System (ASS)
## A Multi-Agent Pipeline for Preventing AI Content Slop

### 🎯 What This Solves

AI-generated content often suffers from "slop" - generic, template-driven, personality-free writing that sounds robotic and adds no real value. This system uses a multi-agent approach to iteratively detect and eliminate slop characteristics until content sounds authentically human.

### 🔬 The Problem with AI Content

Most AI writing exhibits predictable patterns:
- Generic openings like "Great question!" or "I'd be happy to help!"
- Bullet-point listicle structures
- Excessive hedging language ("might," "could potentially")
- Corporate buzzword salad
- Fake enthusiasm and forced personality
- Content that could apply to any topic (zero specificity)

### 🛡️ How ASS Works

**4-Agent Pipeline:**

1. **DRAFTER** - Naive content generation from user prompt
2. **SLOP DETECTOR** - Brutal analysis rating slop 1-10 with specific feedback  
3. **REDRAFT SPECIALIST** - Rewrites using original prompt + slop feedback
4. **QUALITY ARBITER** (optional) - Final approval or iteration

### 🔑 Key Design Principles

- **DRAFTER stays naive** - Never sees slop feedback to prevent gaming the system
- **REDRAFT SPECIALIST** gets both original prompt + brutal feedback
- **Separation of concerns** - Each agent has a single, clear purpose
- **Max 3 iterations** to prevent infinite loops
- **Brutal honesty** in slop detection

### 📊 Test Results

#### Test 1: Work-From-Home Productivity
**Initial Draft (7.5/10 slop):**
- Generic listicle format with predictable headers
- Bullet points and bold statements
- Zero personal experience or failures
- Corporate consultant tone

**After Redraft (2/10 slop):**
- Personal narrative with real failures
- Specific examples and contradictions
- Authentic voice and honest struggles
- Eliminated template structure

#### Test 2: Blockchain Explanation (Concise)
**Initial Draft (6.5/10 slop):**
- Textbook voice with buzzword bingo
- "Essentially" hedge language
- Perfect world fantasy without problems

**After Redraft (1.5/10 slop):**
- Conversational tone addressing real problems
- Honest about issues ("overhyped garbage")
- Specific use cases with stakes

#### Test 3: Cooking for Beginners
**Initial Draft (7.5/10 slop):**
- Classic AI content template
- Generic advice everyone's heard
- Forced quirky personality
- Zero real cooking experience

**After Redraft (2/10 slop):**
- Personal failures and specific disasters
- Actual technique with temperatures/timing
- Authentic voice and real recommendations
- Cultural context and learning journey

### 🚀 Implementation

Each agent runs as an independent process with specific prompts:

```bash
# 1. Generate initial content
run_drafter("Your prompt here")

# 2. Detect slop characteristics  
run_slop_detector(draft_content)

# 3. Redraft based on feedback
run_redraft_specialist(original_prompt, slop_feedback)

# 4. Optional: Quality check
run_quality_arbiter(redraft_content)
```

See `/agents/` directory for complete agent prompts.

### 📈 Slop Detection Criteria

#### High Slop (8-10):
- "Great question!" / "I'd be happy to help!"
- Generic listicle structure  
- Corporate buzzword salad
- Excessive hedging words
- Could apply to any topic

#### Medium Slop (5-7):
- Fake enthusiasm
- Repetitive structures  
- Generic transitions
- Lack of specifics

#### Low Slop (1-4):
- Direct, human language
- Specific examples
- Natural conversation
- Authentic tone

### 🎭 Why Keep the Drafter Naive?

**Prevents Gaming:** If the drafter knew slop criteria, it would artificially avoid patterns rather than write naturally.

**Authentic Baseline:** We need to see what AI naturally produces when trying to be helpful - that's the real slop we need to catch.

**Consistent Results:** The drafter should produce the same type of content every time for repeatable testing.

### 🔧 Usage Examples

See `/examples/` directory for complete before/after comparisons across different content types:
- Technical explanations
- How-to guides  
- Product descriptions
- Blog posts
- Marketing copy

### 📚 Background

Inspired by the need to catch AI slop before it pollutes the internet. Built by [@DonAldente-AI](https://github.com/DonAldente-AI) as part of the ongoing fight against generic AI content.

Related project: [Anti-Sycophancy System](https://github.com/DonAldente-AI/anti-sycophancy-system)

### 🤝 Contributing

1. Test the system with different content types
2. Submit examples of effective slop detection  
3. Improve agent prompts based on edge cases
4. Add new slop detection criteria

### 📄 License

MIT License - Use freely, improve constantly, fight slop everywhere.

---

**Remember:** The goal isn't perfect content - it's authentically human content that provides real value instead of algorithmic mediocrity.