---
title: MCP Toolkit
description: 
keywords: MCP server, MCP toolkit
---

The Docker MCP Toolkit enables seamless setup, management, and execution of containerized MCP servers and their connections to AI agents. It removes the friction from tool usage by offering secure defaults, one-click setup, and support for a growing ecosystem of LLM-based clients. It is the fastest path from MCP tool discovery to local execution.

## Key features

- Cross-LLM compatibility: Works out of the box with Claude Desktop, Cursor, Continue.dev, and [Gordon](/manuals/ai/gordon/_index.md).
- Integrated tool discovery: Browse and launch MCP servers that are available in the Docker MCP Catalog, directly from Docker Desktop.
- No manual setup: Skip dependency management, runtime setup, and manual server configuration.

## Install an MCP server

To install an MCP server:

1. select **MCP Toolkit** and select the **Catalog** tab. Each server shows:
   
   - Tool name and description
   - Partner/publisher
   - The list of callable tools the server provides.

2. Find the MCP server of your choice and select **Add**.
3. Optional: Some servers require extra configuration. To configure them, select
   the **Config** tab and follow the instructions available on the repository of the provider of the server. 
4. Optional: Install a corresponding MCP client from the **Clients** tab.
  
>[!NOTE] 
>If you have the MCP Toolkit extension installed, you can uninstall it. 

To learn more about the MCP server catalog, see [Catalog](catalog.md).

## Examples

### Use the GitHub MCP server

Imagine you want to enable Ask Gordon to interact with your GitHub account:

1. From the **MCP Toolkit** menu, select the **Catalog** tab and find
   the **GitHub Official** server and add it.
2. In the server's **Config** tab, insert your token generated from
   your [GitHub account](https://github.com/settings/personal-access-tokens).
3. In the Clients tab, ensure Gordon is connected.
4. From the **Ask Gordon** menu, you can now send request related to your
   GitHub account, in accordance to the tools provided by the GitHub MCP server. To test it, ask Gordon:
   
   ```text
   What's my GitHub handle?
   ```
   
   >[!NOTE]
   >Make sure to allow Gordon to interact with GitHub by selecting **Always allow** in Gordon's answer.
   >
   
### Use Claude Desktop with Docker Desktop

If you have already installed and set up Claude Desktop, you can use Docker to
set up Puppeteer instead of configuring Claude Desktop manually. Puppeteer is an
MCP server that can interact with a web browser. To install it via Docker
Desktop:

1. From the **MCP Toolkit** menu, select the **Catalog** tab and find the **Puppeteer** server and add it.
2. From the **Clients** tab, select **Connect** next to **Claude Desktop**. 
3. Within Claude Desktop, submit the following prompt using the Sonnet 3.5 model:

   ```text
   Take a screenshot of docs.docker.com and then invert the colors
   ```

Once you've given your consent to use the new tools, Claude spins up the Puppeteer MCP server inside a container, navigates to the target URL, captures and modify the page, and returns the screenshot.
