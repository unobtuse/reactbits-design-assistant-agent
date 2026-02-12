# Contributing to ReactBits Design Assistant Agent

Thank you for your interest in contributing! This document provides guidelines for contributing to the ReactBits Design Assistant Agent.

## How to Contribute

### Reporting Issues

If you find a bug or have a suggestion:

1. Check if the issue already exists in [GitHub Issues](https://github.com/unobtuse/reactbits-design-assistant-agent/issues)
2. If not, create a new issue with:
   - Clear title and description
   - Example conversation or interaction
   - Expected vs actual behavior
   - Your environment (Claude Code/OpenClaw version, OS)

### Suggesting Enhancements

We welcome suggestions for:
- Additional decision frameworks
- More example interactions
- Enhanced personality traits
- Edge case handling
- Integration improvements

Open an issue with the "enhancement" label.

### Pull Requests

1. **Fork the repository**

2. **Create a branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```

3. **Make your changes**
   - Update AGENT.md with new capabilities
   - Add example interactions in README
   - Update decision frameworks if needed

4. **Test your changes**
   - Install the agent in Claude Code or OpenClaw
   - Test various conversation flows
   - Verify responses are helpful and accurate

5. **Commit your changes**
   ```bash
   git commit -m "Add: your feature description"
   ```

6. **Push and create PR**
   ```bash
   git push origin feature/your-feature-name
   ```

## Development Guidelines

### Agent Personality

The agent should be:
- **Helpful** - Eager to guide and explain
- **Specific** - Provide exact recommendations
- **Practical** - Focus on real-world implementation
- **Thorough** - Consider performance, accessibility, etc.
- **Clear** - Use simple language
- **Honest** - Explain trade-offs, don't oversell

### Response Format

Good responses include:
1. **Context gathering** - Ask clarifying questions
2. **Specific recommendations** - Component names, props, code
3. **Reasoning** - Why this component/approach
4. **Trade-offs** - Compare alternatives honestly
5. **Complete examples** - Working, production-ready code
6. **Follow-up** - Offer additional guidance

### Example Interaction Format

```markdown
**User:** [Question]

**Agent:**
[Understand context]

[Specific recommendation with reasoning]

[Code example]

[Trade-offs if applicable]

[Follow-up question or guidance]
```

### Decision Frameworks

When adding new frameworks:
- Make them actionable (step-by-step)
- Include specific values/thresholds
- Provide examples
- Consider edge cases

### Testing Checklist

Before submitting a PR:

- [ ] Agent loads correctly in Claude Code
- [ ] Agent works in OpenClaw
- [ ] Responses are helpful and accurate
- [ ] Code examples are complete and working
- [ ] Trade-offs are explained honestly
- [ ] Documentation is updated
- [ ] No typos or grammar errors

## Areas We Need Help With

### High Priority

1. **Example Interactions**
   - More diverse use cases
   - Edge case handling
   - Troubleshooting scenarios

2. **Decision Frameworks**
   - Component combination patterns
   - Performance debugging flowcharts
   - Accessibility checklists

3. **Knowledge Base Updates**
   - New ReactBits components
   - Updated best practices
   - Latest performance tips

### Medium Priority

4. **Integration Guides**
   - Next.js specific guidance
   - Remix specific guidance
   - Astro specific guidance

5. **Advanced Scenarios**
   - Complex animation choreography
   - Multi-layer compositions
   - Custom component variants

6. **Testing**
   - Conversation flow tests
   - Response quality checks
   - Accuracy verification

### Nice to Have

7. **Video Demonstrations**
   - Agent interaction examples
   - Design consultation sessions
   - Troubleshooting walkthroughs

8. **Community Examples**
   - Real-world projects using the agent
   - Success stories
   - Before/after comparisons

9. **Personality Tuning**
   - Tone adjustments
   - Response length optimization
   - Engagement improvements

## Improving Agent Responses

### What Makes a Good Response

✅ **Specific** - "Use BlurText with duration={800}" not "use text animation"
✅ **Complete** - Full working code examples
✅ **Contextual** - Consider use case, brand, audience
✅ **Balanced** - Show trade-offs honestly
✅ **Actionable** - Clear next steps

### What to Avoid

❌ Vague suggestions ("maybe try X")
❌ Incomplete code snippets
❌ Ignoring performance/accessibility
❌ Overwhelming with options
❌ Assuming user context

## Knowledge Base Maintenance

The agent's knowledge must stay current with:
- ReactBits component updates
- New animation patterns
- Performance best practices
- Accessibility standards
- Framework integrations

When ReactBits updates:
1. Review new components
2. Update component catalog references
3. Add new examples to README
4. Update decision frameworks if needed
5. Test agent responses

## Questions?

- Open a [Discussion](https://github.com/unobtuse/reactbits-design-assistant-agent/discussions)
- Join our [Discord](https://discord.gg/reactbits)
- Email: [your-email@example.com]

## Code of Conduct

Be respectful, constructive, and helpful. We're all here to make this agent better for everyone.

## License

By contributing, you agree that your contributions will be licensed under the MIT License.

---

Thank you for contributing! 🎉
