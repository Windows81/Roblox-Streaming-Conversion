# Streaming Conversion Skill

AI skill to automatically convert non-streaming Roblox games to streaming. Evaluates the game, applies recommended settings, and cleans up streaming compatibility issues. This skill can also be run on games that already use streaming to optimize and fix bugs.

* Applies recommended Workspace streaming settings
* Model changes
  * Refactors model structure: automatically splits or groups models for optimal model size & visual quality
  * Sets ModelStreamingMode: evaluates model contents and automatically applies the correct ModelStreamingMode
  * Applies SLIM LOD for best visual quality when models are streamed out
* Script changes
  * Adds WaitForChild, nil checks, and other changes necessary to adapt scripts to streaming
  * Adds prefetches and multiple replication foci where necessary
* Runs basic validation - brief playability test to make sure players can join and move around successfully
* Writes a summary of all changes to `streaming_conversion_changes.md`



### How to Use

1. **⚠️ Back up your game**

   The conversion process can make extensive changes to your game. We highly recommend copying your game before you begin. See: [How to Copy an Experience](https://en.help.roblox.com/hc/en-us/articles/203313900-How-to-Copy-an-Experience)

2. [Set up Roblox Studio MCP](https://create.roblox.com/docs/studio/mcp)
3. Open the game you want to convert in Roblox Studio
4. In your AI client (Claude Code, Codex, Cursor, etc.) open this folder as the current project
5. Run the skill with `/rbx-convert-to-streaming`
6. Wait for conversion to complete. This can take 15 - 30+ minutes depending on the size and complexity of the game.
7. **Test your game** - the conversion process makes lots of changes, please play test after conversion to make sure everything still works correctly. If you find any issues caused by the conversion please report them on the Dev Forum so we can improve the skill!



### Model & Client Compatibility

We recommend using higher-end AI models with large context windows for this process. The conversion process can be complex and higher-end models typically produce better results.

<u>Recommended models:</u>

* Claude Opus 4.8
* GPT 5.5



This skill is compatible with any LLM or AI client you choose. If you're using a model or client not listed above and it doesn't recognize the skill automatically, try directly giving it the `SKILL.md` file in this folder.



### Skill File Locations

* **Claude:** `.claude/skills/rbx-convert-to-streaming/SKILL.md`
* **Codex, Cursor:** `.agents/skills/rbx-convert-to-streaming/SKILL.md`
* **VSCode Copilot:** `.github/prompts/rbx-convert-to-streaming.prompt.md`
* `SKILL.md` - Easy access copy of the skill for reference or use in other clients

