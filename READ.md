Hermes Agent has a new Blank Slate setup mode.

The default Quick/Full setup modes work great for most, but if you would rather build your agent from the ground up you can now start with just a provider, model, file operations, and terminal, then manually add in anything else.


Hermes Agent is the self-improving agent framework from Nous Research. It runs on your own machine. The team announced the new mode on X. Blank Slate now joins two existing options: Quick Setup and Full Setup.

TL;DR
Blank Slate boots an agent with everything off except provider & model, File Operations, and Terminal.
Web, browser, code execution, vision, memory, delegation, cron, skills, plugins, and MCP stay disabled.
It writes an explicit platform_toolsets.cli list plus agent.disabled_toolsets to pin the surface.
Nothing you skipped loads later — not even after hermes update.
Re-enable anything with hermes tools, hermes skills opt-in --sync, or hermes setup agent.
What is Blank Slate
On a fresh install, hermes setup now offers three modes. The choice sets your starting surface area.




Quick Setup uses the Nous Portal. It needs no API keys and uses a free OAuth login. It sets up a model plus the Tool Gateway tools. The docs call it the recommended fast path.
Full Setup is the opposite. You walk through every provider, tool, and option yourself. You bring your own keys.
Blank Slate is the minimal third path. It is for building an agent from the ground up. Everything starts off except the bare minimum needed to run an agent. That minimum is three pieces: provider & model, the File Operations toolset, and the Terminal toolset.
The disabled list is explicit. Off by default: web, browser, code execution, vision, memory, delegation, cron, skills, plugins, and MCP servers. Compression, checkpoints, smart routing, and memory capture are also disabled.