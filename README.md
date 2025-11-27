🚀 **AI-Driven Development (30-Day Challenge)**

**Task-6**: **Connect GitHub MCP Server with Google Gemini CLI (Remote Server)**

In Task-6, you will learn how to connect the GitHub MCP Server to the Google Gemini CLI using a Hosted Remote Server “the fastest and simplest setup”.

No Docker. No local server. Just plug and play.

🔧 **Prerequisites**

Before you begin, ensure you have:

1.	✅ Google Gemini CLI Installed

2.	✅ GitHub Personal Access Token (PAT)

Create one here:

**https://github.com/settings/personal-access-tokens/new**

3.	✅ No Docker Required

(We use GitHub’s hosted MCP server.)

🔐 **Step 1 (Store Your PAT Securely)**

Never hard-code your PAT in the settings file.

Create this file:
~/.gemini/.env
 
Add inside:

**GITHUB_MCP_PAT=your_token_here**
 
✔ This keeps your token safe and outside version control.

🌐 **Step 2 (Configure GitHub MCP Server) “Remote Method”**

Open or create:

~/.gemini/settings.json
 
 Paste this:
 
**{
 
  "mcpServers": {
  
    "github": {
    
      "httpUrl": "https://api.githubcopilot.com/mcp/",
      
      "headers": {
      
        "Authorization": "Bearer $GITHUB_MCP_PAT"
      }
      
    }
  }
  
}**

What this configuration does:

•	httpUrl connects Gemini CLI to GitHub’s Hosted MCP Server.

•	Authorization automatically loads your token from. env.

🔄 **Step 3 (Restart Gemini CLI)**

Restart the CLI to apply changes:

gemini

🧪 **Step 4 (Verify Connection)**

Run:

**/mcp list**

You should see:

🟢 **github - Ready (90+ tools)**
 
If you see this → Your GitHub MCP server is successfully connected!

🧩 **Step 5 — Test the MCP Server**

Try:

**List my GitHub repositories**
 
If your repos appear → 🎉 Everything is working perfectly!

🛠️ Troubleshooting Guide

❌ Invalid or Expired Token

•	Regenerate your PAT

•	Required scopes:

	repo

	read: packages (optional, only for Docker tools)

❌ Invalid JSON Format

Test your JSON:

cat ~/.gemini/settings.json | jq .

Fix any formatting errors.

❌ Server Not Connecting

Run debug mode:

gemini --debug "hello"

Logs will show the exact issue.

🎉 **Conclusion**

You have successfully completed Task-6 by connecting the GitHub MCP Server to the Gemini CLI using a Remote Server setup.

**Next Up**:

**👉Task-7** → Learn how to actually use MCP tools inside real workflows and AI-powered projects!⚡
