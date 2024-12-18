# MCP-Twikit

A Model Context Protocol (MCP) server for interacting with Twitter.

<a href="https://glama.ai/mcp/servers/49i9dd08w8"><img width="380" height="200" src="https://glama.ai/mcp/servers/49i9dd08w8/badge" alt="mcp-twikit MCP server" /></a>

## Installation

```json
{
    "mcpServer": {
        "command": "uvx",
        "args": ["--from", "git+https://github.com/adhikasp/mcp-twikit", "mcp-twikit"],
        "env": {
            "TWITTER_USERNAME": "@example",
            "TWITTER_EMAIL": "me@example.com",
            "TWITTER_PASSWORD": "secret",
        }
    }
}
```

## Example usage

Using [mcp-client-cli](https://github.com/adhikasp/mcp-client-cli)


### Comparing sentiments across different twitter accounts

```
$ llm compare 20 latest tweet directed @IndiHomeCare, @di_cbn, @BiznetHome, @ID_MyRepublic. What are people sentiment to the product? Do 1 search for each account

I'll help you analyze the latest tweets for these internet service providers in Indonesia to understand the public sentiment. I'll use the search_twitter function for each account.

Tool Calls:
  search_twitter
  Args:
    query: to:IndiHomeCare
    count: 20
    sort_by: Latest

Tool Calls:
  search_twitter
  Args:
    query: to:di_cbn
    count: 20
    sort_by: Latest

Tool Calls:
  search_twitter
  Args:
    query: to:BiznetHome
    count: 20
    sort_by: Latest

Tool Calls:
  search_twitter
  Args:
    query: to:ID_MyRepublic
    count: 20
    sort_by: Latest

Sentiment Analysis Summary:

1. IndiHomeCare:
- Predominantly Negative Sentiment
- Key Issues:
  - Unstable internet connection
  - Slow response times
  - Intermittent service disruptions
  - Long waiting times for customer support
- Specific Complaints:
  - Network instability
  - Lagging internet
  - Unresolved technical issues
  - Lack of timely communication

2. CBN (di_cbn):
- Mostly Negative Sentiment
- Key Issues:
  - Prolonged internet outages (some reporting 1-2 days of no service)
  - Slow customer support response
  - Lack of clear communication about service disruptions
- Specific Complaints:
  - LOS (Line of Sight) issues
  - No timely resolution of technical problems
  - Delayed email and support responses

3. BiznetHome:
- Strongly Negative Sentiment
- Key Issues:
  - Frequent network interruptions
  - Slow internet speeds
  - Poor customer support responsiveness
- Specific Complaints:
  - Packet loss
  - Inconsistent connection
  - Long download times
  - Unresolved technical issues

4. MyRepublic (ID_MyRepublic):
- Extremely Negative Sentiment
- Key Issues:
  - Severe and prolonged service disruptions
  - Complete internet outages
  - Inability to access online services and games
  - Extremely poor customer support
- Specific Complaints:
  - Multi-day service interruptions
  - Inability to access websites and online games
  - Missed technician appointments
  - Lack of compensation or clear communication

Overall Sentiment Ranking (from Bad to Worst):
1. IndiHomeCare (Bad)
2. CBN (Worse)
3. BiznetHome (Very Bad)
4. MyRepublic (Extremely Bad)

Common Themes Across Providers:
- Poor network stability
- Slow customer support response
- Lack of transparent communication
- Prolonged service interruptions
- Unresolved technical issues

Recommendation: These Indonesian internet service providers are experiencing significant customer satisfaction issues. Customers are frustrated with unreliable services, poor technical support, and lack of timely problem resolution.
```

### Getting tweets from your home timeline

```
$ llm what is happening on my twitter timeline?

I'll help you check your Twitter timeline. I'll retrieve the latest tweets from your timeline:

Tool Calls:
  get_timeline
  Args:

I'll summarize the key highlights from your Twitter timeline:

1. Professional/Tech Highlights:
- @ibamarief is preparing to onboard their first intern, noting it's a significant responsibility
- @papanberjalan shared a critique about web developers not understanding computer performance
- @pathofexile is running a Twitch Drops promotion for their game

2. Notable Tweets:
- @elonmusk posted a cryptic "Hmm"
- @realDonaldTrump discussed eliminating Daylight Saving Time
- @blinkist shared an article about billionaires reading up to 50 books per year

3. Miscellaneous Interesting Tweets:
- @nealtaparia shared a thread about 11 companies built around a single product
- @Rixhabh__ posted about creative and iconic ads
- Several tweets in Indonesian covering various topics from personal stories to social issues

Would you like me to elaborate on any of these tweets or provide more context about any specific post?
```
