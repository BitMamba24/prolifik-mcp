# Prolifik MCP server

Prolifik makes short-form video for social media. This is the public listing for its hosted MCP server, so any MCP client (Claude, ChatGPT, Cursor and others) can cut clips from long videos, render branded videos and schedule posts on your connected accounts.

The server is hosted. There is nothing to install or run from this repository.

- Endpoint: `https://app.getprolifik.com/mcp`
- Transport: Streamable HTTP
- Auth: OAuth 2.0 (sign in with your Prolifik account), or a Prolifik API key sent as `Authorization: Bearer <key>`
- Website: https://getprolifik.com/
- Docs: https://getprolifik.com/docs/

## Connect

Add a remote MCP server in your client with the URL `https://app.getprolifik.com/mcp`. The client opens a Prolifik sign-in window the first time it connects.

Clients that take a JSON config:

```json
{
  "mcpServers": {
    "prolifik": {
      "url": "https://app.getprolifik.com/mcp"
    }
  }
}
```

A Prolifik account is required. Plans start at €20 a month and the MCP server uses the same plan as the web app.

## What it can do

**AI Clipper.** Send up to 10 video links at once, or upload a file, and get the strongest moments back as vertical clips with captions.
`create_clip_job`, `create_clip_upload_url`, `get_clip_job_status`, `get_clip_job`, `list_clip_jobs`, `cancel_clip_job`, `get_clip_minutes`

**Branded videos.** Set up a brand once, point Prolifik at a URL or product, and render videos in that brand's voice and look.
`create_brand`, `get_brand`, `update_brand`, `list_brands`, `create_content_source`, `get_content_source`, `update_content_source`, `reanalyze_content_source`, `list_content_sources`, `delete_content_source`, `create_content_job`, `get_content_job`, `list_content_jobs`, `cancel_content_job`, `list_content`, `get_content_piece`, `update_content_piece`, `regenerate_content_piece`, `retry_content_render`, `delete_content_piece`, `create_content_upload_url`, `list_media_library`, `get_usage`

**Cloning.** Take a post that worked, get a cost estimate, and make new variations of it, in other languages if you want, spread across your accounts.
`estimate_clone`, `clone_post`, `get_clone_job`, `list_clone_jobs`, `retry_clone_job`, `delete_clone_job`, `add_clone_variations`, `localize_clone_variations`, `save_clone_variation_to_library`, `distribute_clone_job`

**AI influencers.** Create a consistent AI persona to front your videos.
`create_influencer`, `get_influencer`, `list_influencers`, `regenerate_influencer`, `delete_influencer`

**Studio.** Generate images and video clips with the image and video models in Prolifik Studio.
`list_studio_models`, `create_studio_generation`, `get_studio_generation`, `list_studio_generations`, `create_studio_upload_url`, `get_studio_credits`

**Publishing.** Post or schedule clips and videos to TikTok, Instagram Reels, YouTube Shorts and X.
`list_publish_destinations`, `publish_clip`, `list_clip_publishes`, `retry_clip_publish`, `publish_content`, `list_content_publishes`, `get_content_publish`, `update_content_publish`, `cancel_content_publish`

Publishing tools create real posts on your accounts. Good clients confirm the account, time and caption with you before calling them.

Jobs run in the background: a create tool returns at once, and the matching get tool reports progress until the job settles.

## Support

info@getprolifik.com
