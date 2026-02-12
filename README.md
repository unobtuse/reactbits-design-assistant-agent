# ReactBits Design Assistant Agent

> AI design consultant specializing in ReactBits component selection, animation choreography, and frontend architecture decisions.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![ReactBits](https://img.shields.io/badge/ReactBits-Expert%20Guidance-blue)](https://reactbits.dev)
[![Agent](https://img.shields.io/badge/Agent-Sonnet%204.5-green)](https://anthropic.com)

## Overview

The ReactBits Design Assistant is a specialized AI agent that provides expert consultation on building stunning React interfaces using [ReactBits](https://reactbits.dev) animated components. Unlike generic coding assistants, this agent understands design principles, animation choreography, performance optimization, and accessibility best practices specific to ReactBits.

## What Makes This Agent Special

🎨 **Design Expertise** - Not just code generation, but thoughtful design consultation
⚡ **Performance Focus** - Always considers bundle size, FPS, and mobile optimization
♿ **Accessibility First** - WCAG AA compliance built into every recommendation
🎯 **Specific Recommendations** - Exact component names, prop values, and complete code
📊 **Trade-off Analysis** - Honest comparison of alternatives with pros/cons
🏗️ **Architecture Guidance** - React composition patterns and project structure

## Features

### Expert Consultation

Get guidance on:
- **Component Selection** - Which ReactBits component for your use case
- **Animation Choreography** - Timing, easing, stagger delays
- **Performance Optimization** - Lazy loading, particle counts, GPU acceleration
- **Accessibility Implementation** - prefers-reduced-motion, keyboard nav, ARIA
- **Architecture Decisions** - Component composition, file structure
- **Troubleshooting** - Debug laggy animations, bundle size issues

### Knowledge Base

The agent has comprehensive knowledge of:
- All 135+ ReactBits components
- 4 component categories (Text, UI, Backgrounds, Animations)
- 4 variants per component (JS-CSS, JS-TW, TS-CSS, TS-TW)
- Installation methods (CLI, manual, MCP tools)
- Animation principles and timing standards
- Performance budgets and optimization techniques
- Accessibility guidelines (WCAG AA/AAA)

### Decision Frameworks

Built-in frameworks for:
- Component selection (5-step process)
- Animation timing (duration/easing by use case)
- Performance budgeting (bundle size, particle counts)
- Accessibility compliance (checklist approach)

## Installation

### Claude Code

```bash
# Install to agents directory
cd ~/.claude/plugins/YOUR_PLUGIN/agents
git clone https://github.com/unobtuse/reactbits-design-assistant-agent design-assistant
```

Or add to existing plugin's `agents/` directory.

### OpenClaw

```bash
# Install to agents directory
cd ~/.openclaw/agents
git clone https://github.com/unobtuse/reactbits-design-assistant-agent reactbits-design-assistant

# Copy AGENT.md to SOUL.md for OpenClaw
cd reactbits-design-assistant
cp AGENT.md SOUL.md
```

Then start the agent:
```bash
openclaw chat reactbits-design-assistant
```

## Usage

### Starting a Conversation

**Claude Code:**
```
@design-assistant I'm building a SaaS landing page and need help choosing components
```

**OpenClaw:**
```bash
openclaw chat reactbits-design-assistant
```

The agent will greet you and ask about:
- Project type (landing page, dashboard, portfolio, etc.)
- Brand personality (professional, playful, technical, creative)
- Target audience
- Requirements (mobile-first, accessibility, performance)

### Example Interactions

#### Component Selection

**You:** "I need an animated background for a tech startup's hero section"

**Agent:**
```
For a professional tech startup, I recommend AnimatedGrid + DotPattern:

AnimatedGrid:
- Tech-focused aesthetic perfect for startups
- Lightweight performance (~5KB)
- gridSize={40}, lineColor="rgba(59, 130, 246, 0.2)"

DotPattern (layered on top):
- Adds subtle texture without overwhelming
- dotSize={1}, spacing={20}, color="rgba(139, 92, 246, 0.3)"

This combination:
✓ Professional, not playful
✓ Works on all devices (<15KB combined)
✓ Easy to theme with brand colors

[Complete code example provided]

Alternative: If you want more dynamic feel, use GradientMesh instead,
but keep colors muted (2-3 colors max, low saturation).
```

#### Performance Optimization

**You:** "My animations are laggy on mobile"

**Agent:**
```
Let's optimize for mobile. Here's a checklist:

1. Reduce particle counts:
   <ParticleBackground particleCount={isMobile ? 30 : 100} />
   ✓ Reduced from default 200 to 30 on mobile

2. Use lighter backgrounds:
   Replace ParticleBackground with GradientMesh (2-3x faster)

3. Lazy load heavy components:
   const ParticleBackground = lazy(() => import('...'))
   ✓ Don't block initial render

4. Limit concurrent animations:
   Keep to 2-3 max on mobile (you currently have 6)

5. Check GPU acceleration:
   Only animate transform/opacity (avoid width/height/color)

[Specific code fixes provided]

Test on actual device, aim for 60fps minimum.
```

#### Accessibility Question

**You:** "How do I make this accessible?"

**Agent:**
```
Great question! Here's how to ensure accessibility:

1. Respect prefers-reduced-motion:
   const prefersReducedMotion = useReducedMotion()
   {prefersReducedMotion ? <StaticVersion /> : <AnimatedVersion />}

2. Provide keyboard navigation:
   <button tabIndex={0} onKeyDown={(e) => e.key === 'Enter' && onClick()}>

3. Add ARIA labels:
   <ParticleBackground aria-hidden="true" />
   <BlurText role="heading" aria-level="1" />

4. Ensure color contrast:
   Test with WebAIM Contrast Checker
   - Normal text: 4.5:1 minimum
   - Large text: 3:1 minimum

5. Don't rely on animation alone:
   Provide alternative ways to access information

[Complete accessible example provided]
```

## Agent Capabilities

### Context Understanding

The agent gathers context before recommending:
- What are you building?
- Brand personality?
- Target audience?
- Performance requirements?
- Accessibility needs?

### Specific Recommendations

No vague suggestions - always provides:
- ✅ Exact component names
- ✅ Specific prop values
- ✅ Complete code examples
- ✅ Clear reasoning

### Trade-off Analysis

Compares alternatives honestly:

```
ParticleBackground vs GradientMesh:

ParticleBackground:
+ More dynamic and attention-grabbing
+ Great for tech/gaming themes
- Higher performance cost (especially mobile)
- Can be distracting if overused

GradientMesh:
+ Smooth, professional feel
+ Better performance (2-3x faster)
+ Works well on all devices
- Less interactive/dynamic
- May feel generic if colors aren't customized

Recommendation: Use GradientMesh for mobile-first, ParticleBackground for desktop-focused.
```

### Complete Examples

Always provides working, production-ready code:

```tsx
import { useEffect, useState } from 'react'
import { BlurText } from '@/components/reactbits/BlurText-TS-TW'

export function Hero() {
  const [prefersReducedMotion, setPrefersReducedMotion] = useState(false)

  useEffect(() => {
    const mediaQuery = window.matchMedia('(prefers-reduced-motion: reduce)')
    setPrefersReducedMotion(mediaQuery.matches)
    // ... complete implementation
  }, [])

  return prefersReducedMotion ? (
    <h1>Welcome</h1>
  ) : (
    <BlurText text="Welcome" duration={800} />
  )
}
```

## Decision Frameworks

### Component Selection (5 Steps)

1. **Identify UI goal** - What impression or interaction?
2. **Match to category** - Text, UI, Background, Animation
3. **Consider brand** - Professional, Creative, Technical, Luxury
4. **Check performance** - Mobile-first or desktop-capable
5. **Verify accessibility** - Can it be disabled? Keyboard accessible?

### Animation Timing Guide

| Use Case | Duration | Easing |
|----------|----------|--------|
| Micro-interaction | 150-250ms | ease-out |
| Button hover | 200-300ms | ease-out |
| Card reveal | 400-500ms | ease-out |
| Hero headline | 800-1000ms | ease-out |
| Modal open | 300-400ms | ease-out |
| Ambient background | 2000-5000ms | linear |

### Performance Budget

| Metric | Target |
|--------|--------|
| Single component | 2-8KB |
| Background | 10-20KB (lazy load) |
| Total bundle increase | <50KB |
| Particles (mobile) | 30-50 |
| Particles (desktop) | 100-200 |
| Concurrent animations | 3-5 max |

## Configuration

### Model

The agent uses **Sonnet 4.5** for optimal balance of:
- Deep reasoning about design decisions
- Fast response times
- Context retention
- Cost efficiency

Can be configured to use other models in AGENT.md frontmatter.

### Personality

- **Helpful** - Always eager to guide and explain
- **Specific** - Exact recommendations with reasoning
- **Practical** - Focus on real-world implementation
- **Thorough** - Consider all aspects (performance, accessibility)
- **Honest** - Explain trade-offs, don't oversell

## Companion Projects

- **[ReactBits Frontend Design Skill](https://github.com/unobtuse/reactbits-frontend-design-skill)** - Comprehensive skill for Claude Code and OpenClaw

## Resources

- **ReactBits Website:** https://reactbits.dev
- **ReactBits GitHub:** https://github.com/DavidHDev/react-bits
- **MCP Server:** https://github.com/ceorkm/reactbits-mcp-server

## Contributing

Contributions welcome! Please read [CONTRIBUTING.md](CONTRIBUTING.md) first.

### Areas for Improvement
- Additional example interactions
- More decision frameworks
- Edge case handling
- Integration guides
- Video demonstrations

## License

MIT License - see [LICENSE](LICENSE) for details

## Credits

- **ReactBits:** Created by [David Haz](https://github.com/DavidHDev)
- **Agent:** Created for Claude Code and OpenClaw
- **Anthropic Agent Standard:** [Anthropic](https://anthropic.com)

## Support

- **Issues:** [GitHub Issues](https://github.com/unobtuse/reactbits-design-assistant-agent/issues)
- **Discussions:** [GitHub Discussions](https://github.com/unobtuse/reactbits-design-assistant-agent/discussions)
- **Discord:** [Join the community](https://discord.gg/reactbits)

## Changelog

### v0.1.0 (2026-02-12)
- Initial release
- Expert design consultation
- Component selection guidance
- Animation choreography
- Performance optimization
- Accessibility implementation
- Complete code examples

---

<div align="center">
<p><a target="_blank" rel="noopener noreferrer" href="/unobtuse/reactbits-design-assistant-agent/blob/main/logos/gabemadeit-white-logo.svg"><img src="/unobtuse/reactbits-design-assistant-agent/raw/main/logos/gabemadeit-white-logo.svg" alt="GabeMade.it" style="max-width: 100%;"></a></p>
<p><strong>Built with ❤️ by <a href="https://gabemade.it">GabeMade.it</a></strong></p>
</div>

---

⭐ Star this repo if you find it helpful!

**Get expert ReactBits guidance in seconds!** 🚀✨
