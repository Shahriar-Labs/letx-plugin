# letX

[letX](https://letx.app) is a collaborative LaTeX editor. This plugin connects your AI assistant to
your letX account, so you can work on LaTeX documents from the conversation: find a template,
start a project, read and edit its files, and compile it to PDF, with the LaTeX errors reported by
file and line so they can be fixed.

## What it includes

- **The letX MCP server** at `https://api.letx.app/mcp`. You sign in with your letX account
  (OAuth 2.1) and approve what the assistant may do: read letX's templates, read and edit your
  projects, and compile them. You can disconnect it at any time in letX under
  **Settings, Connected apps**.
- **Two skills:**
  - `compile-and-fix`: compile LaTeX from the conversation or a letX project, and fix the errors
    it reports until the document builds.
  - `start-from-template`: find a template in letX's library and start a project from it.

## Tools

| Tool | What it does | Changes anything? |
| --- | --- | --- |
| `search_templates` | Search letX's LaTeX template library | No |
| `get_template` | Details of one template: description, author, license, page link | No |
| `search`, `fetch` | The same template search and details, in the shape deep research expects | No |
| `list_projects` | Your letX projects, with their ids | No |
| `list_project_files` | The documents and uploaded files in one project | No |
| `read_project_file` | The text of one document in a project | No |
| `create_project` | A new project from LaTeX files | Creates a project |
| `create_project_from_template` | A new project from a template | Creates a project |
| `update_project_file` | Create or replace one document; the previous version stays in the project's history | Replaces a file |
| `compile_latex` | Compile LaTeX from the conversation in your "AI Scratchpad" project | Replaces that project's files of the same name |
| `compile_project` | Compile one of your projects | Starts a build |
| `set_project_compiler` | Set a project's TeX engine: pdflatex, xelatex or lualatex | Changes one setting |

## What it sends and receives

The plugin runs no code on your machine and connects to nothing but the letX MCP server above.
When the assistant calls a tool, letX receives that call's arguments (for example the file it
writes or the project it compiles) and returns the result: project names and ids, file lists, the
text of the files it reads, template details, compile results with the errors from the log, and a
link that opens the PDF for an hour. letX does not receive your conversation. The details are in
the [privacy policy](https://letx.app/privacy/#connected-ai-apps).

## Requirements

A letX account. Using letX from an AI app is part of letX's paid plans, and in Claude a free account
can try it for 7 days from its first connection. Plans are described at https://letx.app/pricing/.

## Support

https://letx.app/help/ or support@letx.app. Documentation and example prompts:
https://letx.app/mcp/

## License

MIT. See [LICENSE](LICENSE).
