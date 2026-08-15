<div align="center">

<h1>AI Problems Diagnostic Assistant</h1>

<p>
developed and maintained by
<a href="https://www.initmax.com"><img alt="initMAX" src="./.readme/logo/initmax-logo-framed.svg" height="22" valign="middle"></a>
</p>

<p><strong>An AI Assistant button on every row of Monitoring -> Problems.</strong><br>
Click it and the assistant already knows the event, its trigger, the items behind it, their latest values and the hosts they run on. No copy-pasting a problem into a chat window, and no explaining your topology first.</p>

<p>
<img src="./.readme/badge/zabbix.svg" alt="Zabbix 6.0-7.4">
<img src="./.readme/badge/version.svg" alt="version">
<img src="./.readme/badge/php.svg" alt="PHP 7.4+">
<img src="./.readme/badge/pro.svg" alt="PRO commercial">
<img src="./.readme/badge/gpg.svg" alt="GPG signed">
</p>

<p>
<a href="#what-it-does"><strong>Features</strong></a> &nbsp;·&nbsp;
<a href="#examples"><strong>Examples</strong></a> &nbsp;·&nbsp;
<a href="#install"><strong>Install</strong></a> &nbsp;·&nbsp;
<a href="#whats-included"><strong>What's included</strong></a> &nbsp;·&nbsp;
<a href="https://portal.initmax.com"><strong>Portal</strong></a> &nbsp;·&nbsp;
<a href="https://www.initmax.com/wiki/ai-problem-diagnostic-assistant/"><strong>Docs</strong></a>
</p>

<br>

<img src="./.readme/screen/01-overview.png" width="880" alt="The diagnostics dialog open over the problem list">

</div>

---

## Why the AI Problems Diagnostic Assistant

The slow part of an incident is rarely the fix. It is working out what the alert is actually telling you - which item fired it, what its value was doing, what else on that host is unhappy, and whether any of it matters.

This module puts an assistant one click away from the problem itself. It collects the event, the trigger and its expression, the items involved with their latest values and value maps, and the hosts, and hands all of it to the model with your own system role in front. You get a first read on the incident without leaving the Problems screen.

## What it does

<table>
<tr>
<td width="50%" valign="top">

**One click from the problem**
An AI Assistant column next to the problem name, on the same screen your operators already live on.

</td>
<td width="50%" valign="top">

**Starts with the context**
Event, trigger, expression, items, latest values, value maps and hosts - collected server-side and sent with the first question.

</td>
</tr>
<tr>
<td width="50%" valign="top">

**Four back ends**
OpenAI, Google Gemini, Anthropic Claude, or any OpenAI-compatible endpoint you run yourself. Every answer is labelled with the provider and model that produced it.

</td>
<td width="50%" valign="top">

**Streamed, markdown answers**
Answers render as they arrive, with a stop button, and formatted rather than as a wall of text.

</td>
</tr>
<tr>
<td width="50%" valign="top">

**Your system role**
The shipped prompt is a starting point and is editable on the settings page - set the house style once, for everyone.

</td>
<td width="50%" valign="top">

**Answers in your language**
Optionally tells the model to reply in each user's own Zabbix display language.

</td>
</tr>
</table>

## Examples

<div align="center">
<img src="./.readme/screen/02-problem-list.png" width="820" alt="The AI Assistant column in the problem list">
<br><em>The column sits beside the problem name and follows the table through its own refreshes.</em>
<br><br>
<img src="./.readme/screen/03-zabbix-60.png" width="820" alt="The same dialog on Zabbix 6.0">
<br><em>The same dialog on Zabbix 6.0 - same branding, same layout, same controls.</em>
</div>

## Configuration

Everything lives on one page - **Administration → AI general → AI Problems Diagnostic Assistant**.

Pick the service (OpenAI, Gemini, Claude, or a custom OpenAI-compatible endpoint), paste the API key, choose the model, and edit the system role if you want to. *Add language to system role* tells the model to answer in each user's own Zabbix display language.

<div align="center">
<img src="./.readme/screen/06-settings.png" width="820" alt="The AI Problems Diagnostic Assistant settings page">
</div>

## Install

The module ships as a **GPG-signed `deb` / `rpm` package** from the initMAX repository - `apt` / `dnf` installs it and keeps it updated, using the repo token from your Portal account.

### Easiest way - the guided installer on the Portal

Open the product page, pick your **OS**, and copy the ready-made command. It fills your token in once you sign in, and there is a feedback box right there too.

<p align="center"><a href="https://portal.initmax.com/catalog/zabbix-ai-problems-diagnostic-assistant#how-to-install"><strong>→ Open the installer on the Portal</strong></a></p>

Prefer a plain archive? Every release also ships as a **ZIP** for offline or manual installs.

Then enable it in **Administration → General → Modules**. Done.

## What's included

| Feature                                                            | Included |
| ------------------------------------------------------------------ | :------: |
| AI Assistant column on Monitoring -> Problems                       |    ✅    |
| Event, trigger, items, latest values and hosts sent as context      |    ✅    |
| OpenAI back end, with a model you choose                            |    ✅    |
| Google Gemini back end, with a model you choose                     |    ✅    |
| Anthropic Claude back end, with a model you choose                   |    ✅    |
| Any OpenAI-compatible endpoint of your own                          |    ✅    |
| Streamed answers, rendered as markdown, with a stop button          |    ✅    |
| Editable system role                                                |    ✅    |
| Answers in each user's own Zabbix display language                  |    ✅    |
| One package for Zabbix 6.0 - 7.4                                    |    ✅    |
| Localised into all 25 Zabbix display languages                      |    ✅    |
| High availability ready                                             |    ✅    |
| Licence                                                             | [Commercial](./LICENSE-PRO.md) |

This product has **one edition**. There is no free build: the whole module is the paid capability, so there is nothing to gate and nothing to compare against.

## Requirements

|                        |                                                                                     |
| ---------------------- | ----------------------------------------------------------------------------------- |
| **Zabbix**             | 6.0 · 6.2 · 6.4 · 7.0 · 7.2 · 7.4 - one package covers all                           |
| **PHP**                | 7.4 or newer                                                                        |
| **OS**                 | Debian/Ubuntu · RHEL/Rocky/Alma/Oracle/Amazon · SUSE                                 |
| **Edition**            | PRO only (token-gated repo)                                                          |
| **Permissions**        | Super admin to configure it; Admin or Super admin to use it on a problem              |
| **AI service**         | An OpenAI, Gemini or Claude API key, or an OpenAI-compatible endpoint you run yourself |
| **Outbound access**    | The **Zabbix frontend (PHP)** calls the configured AI endpoint and optional MCP server. The browser talks only to the local Zabbix action. |
| **Languages**          | All 25 Zabbix display languages - the module follows each user's own language setting |
| **High availability**  | Ready. The configuration lives in the Zabbix database, not on the frontend node - install it on every node of an HA cluster and any node can serve it |

### Across Zabbix versions

One package carries both module trees and installs the right one for the frontend it finds - Zabbix accepts the older manifest format only below 6.4 and the newer one only from 6.4 up. Upgrading Zabbix under an installed module switches trees on its own; the module's settings are untouched.

Monitoring -> Problems is one of the few screens Zabbix has carried unchanged across this whole range, which is why the column, the dialog and the settings page are the same on all six versions - same fields, same labels, same order, same branding.

Two frontend differences are worth knowing about, and neither costs you a capability:

- On Zabbix 6.0 the settings page has no documentation link in its header, because that frontend's page shell has nowhere to put one. Zabbix added it in 6.2.
- Zabbix renamed the dialog's header wrapper in 7.0. The module styles both, so the dialog is branded on every version - it was not before 7.0.

There are no capabilities left out on any supported version.

### A note on where the key goes

The assistant talks to the AI service **from the Zabbix frontend (PHP)**. The browser sends only the conversation to the module's guarded `apda.chat` action and receives a normalized response stream. Provider keys, the MCP URL and the MCP bearer token are resolved and used server-side; stored secret values are not rendered back into the settings page. A public AI provider therefore never connects to an internal MCP address directly: the frontend exposes selected MCP tools to the model as function definitions, executes approved calls itself and returns only the selected tool result to the model. Users below Admin are not offered the problem-list assistant.

## Support &amp; links

- 📚 **[Documentation / Wiki](https://www.initmax.com/wiki/ai-problem-diagnostic-assistant/)**
- 🛒 **[Product page](https://www.initmax.com/product/ai-problem-diagnostics-assistant/)**
- 🎫 **[Portal](https://portal.initmax.com)** - downloads, tokens, support tickets
- ✉️ **[support@initmax.com](mailto:support@initmax.com)**

---

<div align="center">
<sub>PRO: <a href="./LICENSE-PRO.md">commercial</a> &nbsp;·&nbsp; © 2021-2026 initMAX s.r.o.</sub>
</div>
