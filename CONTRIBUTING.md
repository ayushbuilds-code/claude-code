# Contributing to Claude Code

Thank you for your interest in contributing to Claude Code! We welcome contributions, whether you are filing bug reports, proposing enhancements, improving documentation, or building examples.

## Code of Conduct

We are committed to providing a welcoming, inclusive, and harassment-free environment for everyone. Please be respectful, considerate, and collaborative in all interactions across issues, pull requests, and discussions.

## Ways to Contribute

There are many ways to get involved:

- **Report bugs**: Let us know if you find unexpected behavior or errors.
- **Suggest features**: Share ideas for CLI improvements, new flags, workflows, or integrations.
- **Improve documentation**: Fix typos, clarify guides, or add missing examples.
- **Contribute examples**: Share settings, hooks, MDM configurations, or gateway patterns under `examples/`.
- **Develop or improve mods**: Work on built-in plugin mods under `mods/`.

---

## Repository Structure

- **`mods/`**: Source code for built-in mods (such as `diff`, `privacy`, `sec-default`, `telemetry`, and `agents-md`). Each mod is a complete plugin that interacts with Claude Code's engine events.
- **`examples/`**: Configuration templates and sample implementations, including hooks, gateway configurations, and mobile device management (MDM) settings.
- **`plugins/`**: Documentation and references for Claude Code plugins. Official plugins are maintained in [anthropics/claude-plugins-official](https://github.com/anthropics/claude-plugins-official).
- **`scripts/`**: Automation scripts for issue triage, maintenance, and lifecycle management.
- **`.devcontainer/`**: Container configurations for running and testing Claude Code in an isolated DevContainer environment.

---

## Reporting Issues

Before opening a new issue, please search the [existing issues](https://github.com/anthropics/claude-code/issues) to see if your topic is already being tracked.

When opening an issue, choose the appropriate issue template:

- **[Bug Report](https://github.com/anthropics/claude-code/issues/new?template=bug_report.yml)**: Include system details (OS, node/Claude Code version), reproduction steps, expected vs. actual behavior, and relevant logs.
- **[Documentation Issue](https://github.com/anthropics/claude-code/issues/new?template=documentation.yml)**: Specify the page, section, and suggested corrections.
- **[Feature Request](https://github.com/anthropics/claude-code/issues/new?template=feature_request.yml)**: Describe the problem you are solving, your proposed solution, and sample workflows.
- **[Model Behavior](https://github.com/anthropics/claude-code/issues/new?template=model_behavior.yml)**: For unexpected tool calls, prompt regressions, or model output issues.

> [!TIP]
> You can also report issues directly from within Claude Code using the `/bug` command.

---

## Development and Testing

### Mod Development & Type Checking

Built-in mods are written in TypeScript and typechecked against the engine contracts in `mods/types/`:

```bash
# Typecheck all mods and tests
npx tsc -p mods/tsconfig.json --noEmit
```

To run a mod locally from source:

```bash
claude --plugin-dir mods/<mod-name>
```

To execute a mod's unit tests:

```bash
claude plugin test mods/<mod-name>
```

For more details on composing mods and writing tests, see [`mods/README.md`](mods/README.md).

### DevContainer Environment

If you prefer containerized development, configuration files are available in `.devcontainer/`:

- Follow instructions in `.devcontainer/devcontainer.json` to open the repository inside VS Code DevContainers or GitHub Codespaces.
- On Windows systems with Docker or Podman, helper scripts are provided under `Script/run_devcontainer_claude_code.ps1`.

---

## Submitting Pull Requests

1. **Fork and branch**:
   - Fork the repository and create a descriptive branch for your work:
     ```bash
     git checkout -b feature/my-enhancement
     # or
     git checkout -b fix/issue-description
     ```
2. **Make focused changes**:
   - Keep pull requests small and focused on a single change or fix.
   - Follow existing code style and formatting standards.
3. **Validate**:
   - Ensure type checks pass (`npx tsc -p mods/tsconfig.json --noEmit`).
   - Run relevant tests and verify your changes.
4. **Write clear commit messages**:
   - Use descriptive commit messages following standard conventional commit guidelines (e.g., `docs: add contributing guide`, `fix(diff): handle empty git diffs`).
5. **Open the PR**:
   - Submit the PR against the `main` branch.
   - Reference any related issues in the PR description (e.g., `Closes #12345` or `Relates to #12345`).
   - Describe what changed and provide steps to verify or test the pull request.

---

## Security Vulnerabilities

If you discover a security vulnerability, please **do not** open a public issue or pull request. Refer to our [Security Policy](SECURITY.md) and report security findings through our [HackerOne submission form](https://hackerone.com/4f1f16ba-10d3-4d09-9ecc-c721aad90f24/embedded_submissions/new).
