# Google Ads MCP Server by Insightful Pipe

[![MCP Compatible](https://img.shields.io/badge/MCP-Compatible-blue)](https://insightfulpipe.com/mcp-servers/google-ads)
[![Insightful Pipe](https://img.shields.io/badge/Insightful_Pipe-MCP_Servers-purple)](https://insightfulpipe.com/mcp-servers)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Listed on MCP Market](https://mcpmarket.com/badge/server/google-ads-20.svg)](https://mcpmarket.com/server/google-ads-20?utm_source=readme&utm_medium=badge)

> **Connect Google Ads to AI assistants for advertising analytics and campaign management.**

Part of the [Insightful Pipe MCP Server Collection](https://insightfulpipe.com/mcp-servers) — Connect your Google Ads account to Claude, ChatGPT, Cursor, and other AI assistants using the Model Context Protocol (MCP). Analyze campaigns, optimize ad spend, and get AI-driven insights directly in your conversations.

[![Explore All MCP Servers](https://img.shields.io/badge/Explore_All-MCP_Servers-blue?style=for-the-badge)](https://insightfulpipe.com/mcp-servers)

![Google Ads MCP Server](https://insightfulpipe.com/images/google_ads-icon.svg)

## MCP Server URL

```
https://google-ads.insightfulmcp.com/
```

## What is Google Ads MCP?

Google Ads MCP is a **remote Model Context Protocol server** that enables AI assistants to interact with your Google Ads data. This MCP integration allows you to:

- Query campaign performance metrics using natural language
- Analyze ad group and keyword performance
- Get AI-powered recommendations for campaign optimization
- Monitor ROAS, CTR, CPC, and conversion metrics
- Create and manage campaigns, ad groups, and keywords
- Execute custom GAQL queries for advanced reporting

## Installation

### Claude

1. Copy the MCP Server URL: `https://google-ads.insightfulmcp.com/`
2. Open [Claude Connectors Settings](https://claude.ai/settings/connectors)
3. Scroll to the bottom and click **Add custom connector**
4. Paste the URL and click **Add**
5. Click **Connect** and sign in to InsightfulPipe if asked. Claude then lists the connector as connected.

### ChatGPT

Custom MCP servers are added through ChatGPT's **Developer mode**. Availability depends on your ChatGPT plan, and workspace admins may need to allow it.

1. Turn on **Developer mode** in ChatGPT settings
2. Create a new app for a remote MCP server and paste the URL: `https://google-ads.insightfulmcp.com/`
3. Sign in to InsightfulPipe if asked. The connection finishes as soon as you are signed in.

See OpenAI's guide: [Developer mode and MCP apps in ChatGPT](https://help.openai.com/en/articles/12584461-developer-mode-and-mcp-apps-in-chatgpt)

### Claude Code

```bash
claude mcp add --transport http google-ads https://google-ads.insightfulmcp.com/
```

### Cursor

Add the server to `~/.cursor/mcp.json` (all projects) or `.cursor/mcp.json` (one project):

```json
{
  "mcpServers": {
    "google-ads": {
      "url": "https://google-ads.insightfulmcp.com/"
    }
  }
}
```

When Cursor shows **Needs authentication**, click **Connect** and sign in to InsightfulPipe if asked.

### Gemini CLI

```bash
gemini mcp add --transport http google-ads https://google-ads.insightfulmcp.com/
```

## Available Actions

99 actions: 37 read, 62 write.

### Read Actions (37)

<details>
<summary>Show all 37 read actions</summary>

| Action | Description |
|--------|-------------|
| `account_performance_report` | Account performance for a date range: clicks, cost, impressions, conversions and all conversions |
| `ad_performance_report` | Ad performance for a date range: status, clicks, cost, impressions and conversions per ad |
| `bidding_strategy_report` | Portfolio bidding strategy performance for a date range: type, status, clicks, cost, cost per conversion, impressions, average CPC and conversions |
| `campaign_performance_report` | Campaign performance for a date range: status, bidding strategy type, clicks, cost, impressions, conversions and all conversions |
| `dsa_search_terms_report` | Dynamic Search Ads search terms: headline and landing page served, clicks, cost, impressions and conversions |
| `gaql` | Execute a GAQL (Google Ads Query Language) query |
| `generate_keyword_ideas` | Generate keyword ideas from seed keywords or URL using Keyword Planner |
| `get_account_info` | Customer account information and settings |
| `get_ad_group_bidding` | Ad group bidding strategy information |
| `get_ad_group_labels` | Ad group label associations |
| `get_ad_groups` | Ad group performance data and configuration |
| `get_ad_labels` | Ad group ad label associations |
| `get_ads` | Ad creative performance data and policy information |
| `get_audiences` | Audience targeting and demographic performance data |
| `get_campaign_bidding` | Campaign bidding strategy configurations |
| `get_campaign_budgets` | Campaign budget configuration and recommendations |
| `get_campaign_labels` | Campaign label associations |
| `get_campaigns` | Campaign performance data and configuration |
| `get_change_history` | Change status history for Google Ads entities |
| `get_clicks` | Click-level performance and location data |
| `get_client_accounts` | Customer client hierarchy and management information |
| `get_criterion_labels` | Ad group criterion label associations |
| `get_customer_labels` | Customer label associations |
| `get_display_keywords` | Display keyword targeting performance |
| `get_geo_performance` | Geographic and location-based performance data |
| `get_keywords` | Keyword performance data and statistics |
| `get_labels` | Label management and organization data |
| `get_non_manager_accounts` | Customer client non-manager accounts only |
| `get_shopping_performance` | Shopping campaign product-level performance data |
| `get_topics` | Topic targeting performance data |
| `get_user_interests` | User interest categories and availability |
| `get_user_locations` | User location-based performance data |
| `keyword_performance_report` | Keyword performance for a date range: status, first-page, first-position and top-of-page CPC estimates |
| `list_bidding_strategies` | List portfolio bidding strategies with type, status, targets, bid limits and attached campaign counts |
| `list_conversion_actions` | List conversion actions (id, name, type, category, status); pass conversion_action_id for one with its tag snippets |
| `search_terms_report` | Search terms that triggered ads: match type, clicks, cost, impressions and conversions |
| `suggest_geo_targets` | Search for geo target constants by name (city, postal code, region) to get IDs for location targeting |

</details>

### Write Actions (62)

<details>
<summary>Show all 62 write actions</summary>

| Action | Description |
|--------|-------------|
| `add_audience_targeting` | Target a user list (remarketing audience) with an ad group |
| `add_call_asset` | Add a phone call asset to the account (shows phone number with ads) |
| `add_callout_asset` | Add callout text snippets to the account or to a campaign (e.g., 'Free Shipping', '24/7 Support') |
| `add_demographic_targeting` | Add age and/or gender demographic targeting to an ad group |
| `add_dsa_webpage_targeting` | Add a webpage-targeting criterion to a DSA ad group (incl. page-feed label targeting) |
| `add_keywords` | Add keywords to an ad group |
| `add_label` | Create a new label for organizing campaigns, ad groups, and ads |
| `add_lead_form_asset` | Add a lead form to a campaign (users submit info directly from the ad) |
| `add_location_targeting` | Add geographic location targeting to a campaign (countries, cities, postal codes, regions) |
| `add_negative_keywords` | Add negative keywords at campaign or ad group level |
| `add_price_asset` | Add a price asset to the account (shows product/service pricing under ads) |
| `add_proximity_targeting` | Add radius/proximity targeting to a campaign (target users within a radius around coordinates) |
| `add_sitelinks` | Add sitelink assets to a campaign (clickable links below the ad) |
| `add_structured_snippet_asset` | Add a structured snippet to a campaign (category-based highlights) |
| `apply_label` | Apply a label to campaigns, ad groups, or ads |
| `attach_conversion_actions_to_campaign` | Bind specific conversion actions to an App campaign via Campaign.selective_optimization |
| `create_ad_group` | Create a new ad group (always created as PAUSED) |
| `create_app_ad` | Create an App ad in an existing App campaign ad group |
| `create_app_campaign` | Create an App campaign with its initial App ad group (always created as PAUSED) |
| `create_app_deep_link_asset` | Create an app deep link asset for App ads |
| `create_asset_group` | Add an asset group to an existing Performance Max campaign |
| `create_bidding_strategy` | Create a portfolio bidding strategy (Target CPA, Target ROAS, Maximize Conversions or Maximize Conversion Value) that campaigns share |
| `create_campaign` | Create a new campaign (always created as PAUSED) |
| `create_conversion_action` | Create a conversion action to track valuable user actions |
| `create_display_campaign` | Create a Display campaign with ad group and responsive display ad in one atomic request |
| `create_dsa_campaign` | Create a Dynamic Search Ads (DSA) Search campaign (always created as PAUSED) |
| `create_dynamic_search_ad` | Create a Dynamic Search Ad in a DSA ad group (always created as PAUSED) |
| `create_page_feed` | Create a DSA page feed (AssetSet of type PAGE_FEED) with page URLs and labels |
| `create_performance_max_campaign` | Create a Performance Max campaign with asset group in one atomic request |
| `create_responsive_display_ad` | Create a responsive display ad (always created as PAUSED) |
| `create_responsive_search_ad` | Create a responsive search ad (always created as PAUSED) |
| `create_search_campaign` | Create a new Search campaign (always created as PAUSED) |
| `create_user_list` | Create a new user list (remarketing audience) for Customer Match |
| `create_youtube_video_asset` | Create a reusable YouTube video asset by video ID |
| `link_asset_group_assets` | Attach existing assets to a Performance Max asset group |
| `link_page_feed_to_campaign` | Link a page-feed asset set to a DSA campaign (CampaignAssetSet) |
| `pause_ad` | Pause an individual ad |
| `pause_ad_group` | Pause an ad group |
| `remove_customer_list_members` | Remove members from a Customer Match user list |
| `remove_keywords` | Remove keywords from an ad group |
| `remove_negative_keywords` | Remove negative keywords at campaign or ad group level |
| `resume_ad` | Resume (enable) a paused ad |
| `resume_ad_group` | Resume (enable) a paused ad group |
| `set_asset_group_listing_filters` | Choose which Merchant Center products a Performance Max asset group advertises |
| `set_campaign_device_targeting` | Target or exclude a device for a whole campaign, including Demand Gen |
| `set_device_bid_modifier` | Set bid adjustment for a specific device type on an ad group |
| `unlink_asset_group_assets` | Detach assets from a Performance Max asset group |
| `update_ad` | Update an ad's status (enabled, paused, removed) |
| `update_ad_group` | Update an ad group: name, bids, targets, rotation, URL settings, or status (enabled, paused, removed) |
| `update_app_ad` | Update an existing App ad's inline text and referenced assets |
| `update_asset_group` | Update a Performance Max asset group: name, landing pages, or status (enabled, paused, removed) |
| `update_asset_group_signals` | Add or remove audience and search theme signals on an existing asset group |
| `update_bidding_strategy` | Update a portfolio bidding strategy: name, target, bid limits, or remove it |
| `update_campaign` | Update a campaign: name, dates, budget, bidding strategy and targets, network settings, geo target type, URL settings, or status (enabled, paused, removed) |
| `update_campaign_targeting` | Add or remove the locations and languages a campaign targets |
| `update_conversion_action` | Update an existing conversion action's settings |
| `update_keywords` | Update existing keywords (status, bids) |
| `update_responsive_search_ad` | Update an existing responsive search ad's headlines, descriptions, or URLs |
| `upload_click_conversions` | Upload offline click conversions (Enhanced Conversions for Leads) |
| `upload_customer_list` | Upload members to a Customer Match user list (remarketing audience) |
| `upload_image_asset` | Upload an image asset from a URL to Google Ads |
| `upload_media_bundle_asset` | Upload an HTML5 media bundle asset from a ZIP URL |

</details>

## Control What Your AI Can Do

You decide what AI agents can do with each connected account:

- **Turn individual actions on or off** for every connected account, so agents only see the actions you allow.
- **Connect as Read-only or Read & Write.** A read-only connection can only enable read actions.
- **Destructive actions stay off by default.** Actions such as deletes are disabled until an admin enables them.
- **Team access per account.** Restricted team members only use the accounts they are granted, with the read actions enabled on them.

New Google Ads campaigns, ad groups and ads are created **paused**, so nothing goes live until you enable it.

## Usage Examples

### Query Campaign Performance

```
"Show me my Google Ads campaign performance for the last 30 days"
```

### Analyze Keywords

```
"What are my top 10 performing keywords by conversion rate?"
```

### Generate Keyword Ideas

```
"Generate keyword ideas for 'running shoes' using Keyword Planner"
```

### Execute Custom GAQL Query

```
"Run a GAQL query to get campaign metrics grouped by device"
```

### Create Campaign

```
"Create a new search campaign called 'Summer Sale' with a $50 daily budget"
```

### Add Keywords

```
"Add 'best running shoes' as a phrase match keyword to my Running campaign"
```

## Supported Campaign Types

- **Search Campaigns** - Text ads on Google Search
- **Display Campaigns** - Visual ads across the Google Display Network
- **Shopping Campaigns** - Product listing ads
- **Video Campaigns** - YouTube and video partner ads
- **Performance Max** - AI-powered cross-channel campaigns
- **App Campaigns** - Mobile app promotion

## Why Use Google Ads MCP?

### For Marketers
- **Save time** - Query data without logging into Google Ads
- **Natural language** - No need to learn complex reporting interfaces
- **AI insights** - Get recommendations you might have missed

### For Agencies
- **Multi-account management** - Query across client accounts
- **Automated reporting** - Generate client reports conversationally
- **Scalable analysis** - Analyze more data in less time

### For Developers
- **MCP standard** - Built on the open Model Context Protocol
- **Easy integration** - Works with any MCP-compatible AI assistant
- **Full API access** - Both read and write operations supported

## Security & Privacy

- **OAuth 2.0** - Secure authentication with Google
- **Granular permissions** - Control read vs write access
- **Data encryption** - All data transmitted securely

## Pricing

The Google Ads MCP server is included in every InsightfulPipe plan, together with all other MCP servers and the CLI. Plans start at $29.99/month, and you can try it for 7 days. See [insightfulpipe.com/pricing](https://insightfulpipe.com/pricing) for current plans.

## Ready-Made Skills and Prompts

- [Claude skills for Google Ads](https://insightfulpipe.com/marketing-claude-skills/google-ads) — ready-made skills that run on your connected data

## Explore More MCP Servers by Insightful Pipe

Visit **[insightfulpipe.com/mcp-servers](https://insightfulpipe.com/mcp-servers)** to discover our full collection of MCP servers for marketing and analytics.

### Advertising MCP Servers
- [Facebook Ads MCP](https://insightfulpipe.com/mcp-servers/facebook-ads) - Meta advertising analytics
- [TikTok Ads MCP](https://insightfulpipe.com/mcp-servers/tiktok-ads) - TikTok advertising
- [LinkedIn Ads MCP](https://insightfulpipe.com/mcp-servers/linkedin-ads) - B2B advertising
- [Microsoft Ads MCP](https://insightfulpipe.com/mcp-servers/microsoft-ads) - Bing advertising
- [Pinterest Ads MCP](https://insightfulpipe.com/mcp-servers/pinterest-ads) - Pinterest advertising
- [Snapchat Ads MCP](https://insightfulpipe.com/mcp-servers/snapchat-ads) - Snapchat advertising
- [X Ads MCP](https://insightfulpipe.com/mcp-servers/x-ads) - Twitter/X advertising

### Analytics MCP Servers
- [Google Analytics MCP](https://insightfulpipe.com/mcp-servers/google-analytics) - Website analytics
- [Google Search Console MCP](https://insightfulpipe.com/mcp-servers/google-search-console) - SEO analytics

**[View All MCP Servers →](https://insightfulpipe.com/mcp-servers)**

## Resources

- [Documentation](https://insightfulpipe.com/docs/connectors-google-ads)
- [Video Tutorial](https://www.youtube.com/playlist?list=PLJNzvjxzI5Xwe__BJJLAelSF0ewO3mEFk)
- [InsightfulPipe Blog](https://insightfulpipe.com/blog)

## Support

- **Documentation**: [insightfulpipe.com/docs](https://insightfulpipe.com/docs)
- **All MCP Servers**: [insightfulpipe.com/mcp-servers](https://insightfulpipe.com/mcp-servers)
- **Email**: support@insightfulpipe.com

---

**[Insightful Pipe](https://insightfulpipe.com)** — AI-powered marketing analytics through MCP servers. [Explore all integrations →](https://insightfulpipe.com/mcp-servers)

## License

MIT License - see [LICENSE](LICENSE) for details.
