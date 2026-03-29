# volund-agents

First-party specialist agent profiles maintained by the Volund team. These agents are published to the Forge and can be installed by tenant administrators for all users, or selected by users when creating custom agents.

## Structure

Each agent lives in its own directory under `agents/`:

```
agents/
  my-agent/
    agent.yaml        # AgentProfile CRD manifest
    README.md          # What this agent does, skills it uses
```

## Agent Profiles

An agent profile defines a specialist that the orchestrator can delegate tasks to. Each profile specifies:

- **System prompt** — The agent's persona, instructions, and constraints
- **Skills** — Which tools/skills this agent has access to
- **Model config** — LLM provider, model, temperature, token limits

All first-party agents are `profileType: specialist`. The default orchestrator is built into the platform and not managed here.

## Visibility Model

Agents published from this repo are installed as **system agents** (`visibility: system`), making them available to all users in a tenant. Individual users can also create **custom agents** (`visibility: user`) through the UI that are private to them.

## Adding a New Agent

1. Create a directory under `agents/` with your agent name
2. Add an `agent.yaml` following the AgentProfile CRD schema
3. Add a `README.md` explaining the agent's purpose and capabilities
4. Open a PR — CI will validate the manifest
5. On merge, the agent is automatically published to the Forge

## License

Apache 2.0
