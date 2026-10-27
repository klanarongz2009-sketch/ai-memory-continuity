# AI Memory Continuity

A portable Agent Skill for retrieving relevant long-term user context before personalized, ongoing, or follow-up work.

This project is independent of any one memory provider. It can guide an agent to use persistent Markdown context files and any explicitly available, user-authorized memory MCP. It does not create automatic synchronization between stores or guarantee that every host loads a skill in every new conversation.

## Intended Audience and Adoption

This independent, provider-neutral project is intended for individual users, independent developers, and teams building AI assistants or agent clients. It may be evaluated, adapted, or integrated by projects and providers—including Google, OpenAI, Anthropic, and others—subject to each host's technical capabilities, policies, and review. Naming a provider does not imply affiliation, endorsement, adoption, or compatibility. No provider is represented as having adopted this project unless that is separately verified.

The repository offers a portable skill specification and example workflow; it cannot install itself into third-party products or require any provider to support it. Adoption requires an implementation or configuration path in the relevant product.

## What it does

- Reads user-designated `USER.md` and `MEMORY.md` only when they are present and accessible in the active workspace.
- Searches connected memory tools when available, using the tool's actual schema and relevant semantic queries.
- Distinguishes current user statements from older notes, inferences, and AI-generated claims.
- Avoids claiming that a file or memory was read unless the read/search actually succeeded.
- Saves durable information only through an available authorized write path, without retaining raw transcripts or secrets.
- Explains the limits of skill loading, automatic recall, and synchronization between separate memory systems.

## Install

Copy `SKILL.md` into a supported Agent Skills directory for your client. Common project-local locations include:

- `.agents/skills/ai-memory-continuity/SKILL.md`
- `.claude/skills/ai-memory-continuity/SKILL.md`

Some clients use other skill directories. Check the documentation for the client and version you use. A project-local install applies only when that project workspace is open. Use the host's supported global/personal skills directory for broader availability.

The skill cannot force a host to load or trigger it. After installation, verify in a fresh conversation that the client actually invoked the skill and its memory tools before relying on cross-chat continuity.

## Memory files

If you use Markdown context files, keep them in the workspace that the agent can access. Use only the files you intentionally designate. Do not put passwords, API keys, tokens, or other secrets in these files. Their presence in one workspace does not imply that they are available in another workspace or chat.

## Provider neutrality

The skill does not assume that an MCP server is installed. If your client exposes a memory provider, use only its available tools and schemas. Separate providers and platform account memory remain separate unless a verified integration says otherwise.

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

## Project Status and Disclaimer

This is an independent project. It is provided "as is" and without warranties of any kind, express or implied. There is no guarantee that this project, its skill instructions, or examples will work with any particular AI model, agent client, memory provider, MCP server, or future version; remain available or maintained; preserve data; or produce accurate, complete, or uninterrupted results. Review the instructions, verify behavior, and keep independent backups before relying on this project. This project is not an official product, service, or endorsement of any AI platform or memory provider unless explicitly stated.
