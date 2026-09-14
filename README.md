# 📦 Cursor Release Manager & SLSA Notary

A Cursor IDE rule designed to protect your software supply chain. It forces the AI assistant to cryptographically anchor `CHANGELOG.md`, Release Notes, and SBOMs to the TON Blockchain.

## Why this exists?
Supply chain attacks (like the XZ Utils backdoor) rely on silent modifications to release binaries and changelogs. By using this rule, every time your AI generates release notes or bumps dependencies in `package.json` / `Cargo.toml`, it automatically generates a cryptographic proof of the state of the release.

## 🚀 Prerequisites
Ensure you have the [ProofCore MCP Server](https://mcp.proofcore.org) installed in Cursor:
```json
{
  "mcpServers": {
    "proofcore": {"url": "https://mcp.proofcore.org"}
  }
}
```

## 📦 Installation
Copy the `proofcore-release-manager.mdc` file into your `.cursor/rules/` folder.

## 🤖 How it works
Ask Cursor: *"Generate release notes for the latest commits."*
The AI will draft the notes and immediately anchor the SHA-256 digest on-chain, appending a verification badge to your `CHANGELOG.md`. Zero vendor lock-in, 100% offline verifiable.
