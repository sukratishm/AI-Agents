# Social Media Post Generator

An automated workflow that creates platform-specific social media posts from content links stored in Google Sheets. The system adapts the tone and format to suit different platforms (LinkedIn, Instagram, Twitter, Medium, and Facebook).

## Overview

This project uses n8n workflows to:
1. Monitor a Google Sheet for new content links
2. Generate detailed summaries of the content using Perplexity AI
3. Create tailored social media posts for different platforms using OpenAI
4. Automatically post to LinkedIn (with expansion potential for other platforms)

## System Architecture

The workflow consists of the following components:

- **Google Sheets Trigger**: Monitors a specified Google Sheet for new rows
- **Content Processing**: Extracts the latest content link added
- **Perplexity AI Integration**: Summarizes the content from the link
- **OpenAI Integration**: Generates platform-specific posts based on the summary
- **LinkedIn Publishing**: Automatically posts the content to LinkedIn

## Setup Instructions

### Prerequisites

- n8n account and installation
- Google Sheets API access
- Perplexity AI API key
- OpenAI API key
- LinkedIn Developer account with appropriate permissions

### Google Sheets Configuration

1. Create a Google Sheet with the following structure:
   - Column A: Content links (URLs to articles you want to share)
   - Additional metadata columns as needed

2. Share the Google Sheet with the service account email from your Google API credentials

### n8n Workflow Setup

1. Import the provided JSON workflow file into your n8n instance
2. Configure the following credentials:
   - Google Sheets Trigger account
   - Perplexity AI API key
   - OpenAI API key
   - LinkedIn OAuth2 credentials

3. Update the Google Sheet document ID in the workflow if needed
4. Activate the workflow

## How It Works

1. When a new row is added to your Google Sheet, the workflow is triggered
2. The system extracts the latest link from the sheet
3. Perplexity AI creates a detailed summary of the content
4. OpenAI generates platform-specific posts optimized for:
   - LinkedIn: Professional, insightful content with a call-to-action
   - Instagram: Friendly, visually engaging, concise content with emojis
   - Twitter (X): Punchy, opinionated content within 280 characters
   - Medium: Thoughtful, narrative-driven content with deeper insights
   - Facebook: Conversational, informative content with engagement hooks
5. The LinkedIn post is automatically published with the original article link

## Customization

### Modifying Platform Tones

You can adjust the tone and style for each platform by editing the OpenAI node's prompt:

```
Based on the following article summary. Create tailored social media posts for LinkedIn, Instagram, Twitter (X), Medium, and Facebook. Adapt the tone, length, and format to fit each platform's audience and style.

LinkedIn: Professional, insightful, value-driven. Add a brief call-to-action or question to spark conversation.

Instagram: Friendly, visually engaging, concise. Use line breaks and emojis sparingly but effectively.

Twitter (X): Punchy, opinionated, informative. Stay within 280 characters. Use hashtags where relevant.

Medium: Thoughtful, narrative-driven, deeper insight. Expand the idea with a short introduction and a reflective tone.

Facebook: Conversational, informative, slightly longer than Twitter/Instagram. Encourage engagement with a question or relatable hook.
```

### Adding More Social Media Platforms

To add more platforms:
1. Update the OpenAI prompt to include the new platform
2. Add the appropriate n8n node for the platform's API
3. Connect the node to the workflow

## Security Considerations

- This workflow contains API keys and OAuth credentials that should be kept secure
- The project is currently set to use a private repository to protect sensitive information
- Review API rate limits to ensure compliance with service providers

## Future Enhancements

- Add support for posting to multiple social media platforms
- Implement image generation for visual platforms
- Add analytics tracking for post performance
- Create a scheduling feature for optimal posting times
- Implement feedback loop to improve post quality

## Troubleshooting

- If the workflow fails to trigger, check the Google Sheets API permissions
- If summarization fails, verify the Perplexity AI API key
- If post generation fails, check the OpenAI API key and model availability
- If LinkedIn posting fails, verify OAuth credentials and permissions

## License

[Your chosen license]

## Acknowledgments

- n8n for the workflow automation platform
- Perplexity AI for content summarization
- OpenAI for post generation


# AI-Agents
JSON files for my AI agents
