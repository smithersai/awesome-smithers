# Contributing

Thanks for helping keep Awesome Smithers useful.

## What Belongs Here

Add projects that are:

- Publicly accessible.
- Directly built on Smithers or `smithers-orchestrator`.
- Useful as a product, workflow pack, example, integration, benchmark, or learning resource.
- Documented well enough that a reader can understand what Smithers is doing in the project.

## What Does Not Belong

Please avoid:

- Unrelated projects that happen to contain the word "Smithers".
- Private repos or links that require special access.
- Forks with no Smithers-specific changes.
- Generated or placeholder repos with no runnable workflow or explanation.
- Marketing-only links with no source, docs, or technical detail.

## Entry Format

Use this format:

```markdown
- [Project Name](https://github.com/org/repo) - One concise sentence explaining what it does and how it uses Smithers.
```

Put the entry in the most specific section. If a project has Smithers workflows but Smithers is not the main product, use **Embedded Workflows**.

## Evidence

In the PR description, include the public evidence you used to verify the entry. Good evidence includes a README section, docs page, `package.json` dependency, `.smithers/workflows` path, workflow source file, or Smithers Workflow Directory listing.

If the project is only name-adjacent or agent-orchestration-adjacent, leave it out until there is public evidence that it uses Smithers.

## Review Checklist

Before opening a PR:

- Check the link works.
- Confirm the repo or docs mention Smithers, `smithers-orchestrator`, or a public `.smithers` workflow.
- Include the verification link or path in the PR description.
- Keep descriptions factual and concise.
- Avoid hype words unless they are part of the project's own name.
- Keep entries alphabetized within each section when practical.
