# Midjourney Automation

> [!TIP]
>
> You can use Midjourney Automation directly from APIFY platform [apify.com/igolaizola/midjourney-automation](https://apify.com/igolaizola/midjourney-automation)
>
> If you want to generate videos instead, check out [apify.com/igolaizola/midjourney-video-automation](https://apify.com/igolaizola/midjourney-video-automation)

## 🎨 What does Midjourney Automation do?

Midjourney Automation enables you to automate image generation and upscaling on [Midjourney](https://www.midjourney.com) without manual intervention. With this actor, you can:

- 🤖 Process multiple prompts in bulk
- 🔄 Automatically upscale generated images
- 📊 Handle multiple jobs concurrently
- 🕒 Manage random wait times between operations
- 📁 Generate an album HTML for easy image browsing and downloading

## 🔑 Prerequisites

Before using this actor, you need:

1. An active Midjourney subscription
2. Your Midjourney cookie for authentication
3. The [Cookie-Editor Chrome extension](https://chromewebstore.google.com/detail/cookie-editor/hlkenndednhfkekhgcdicdfddnkalmdm)

## 🚀 Setup Guide

### Getting Your Midjourney Cookie

1. Install the Cookie-Editor Chrome extension
2. Log in to [www.midjourney.com](https://www.midjourney.com)
3. Click on the Cookie-Editor extension icon
4. Grant any required permissions
5. Click "Export" and select "Export as Header String"
6. Copy the exported cookie string

### Running the Actor

1. Paste your cookie string into the actor's `cookie` input field
2. Enter your desired prompts
3. Configure generation options
4. Select a proxy from your country (recommended)
5. Run the actor

## ⚙️ Input Parameters

| Parameter     | Type    | Description                                                                                                                                                       | Default   |
| ------------- | ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------- |
| `cookie`      | String  | Your Midjourney authentication cookie (required)                                                                                                                  | -         |
| `prompts`     | Array   | List of prompts to generate images                                                                                                                                | -         |
| `mode`        | Select  | Generation mode: "relaxed" (queued, no GPU time cost, only available for "Standard Plan" or higher), "fast" (standard speed), or "turbo" (4x faster, 2x GPU cost) | "relaxed" |
| `upscale`     | Select  | Upscaling mode: none, "subtle", or "creative"                                                                                                                     | none      |
| `privacy`     | Boolean | Enable privacy mode (only available for "Pro Plan" or higher)                                                                                                     | false     |
| `concurrency` | Integer | Number of concurrent jobs                                                                                                                                         | 1         |
| `minWait`     | Integer | Minimum wait time between operations (seconds)                                                                                                                    | 5         |
| `maxWait`     | Integer | Maximum wait time between operations (seconds)                                                                                                                    | 10        |
| `jobTimeout`  | Integer | Maximum time to wait for job completion (seconds)                                                                                                                 | 300       |

## 📋 Output Format

The actor provides results in a structured format:

```json
[
  {
    "album_url": "https://api.apify.com/v2/key-value-stores/1Ht4z6r0m1OfBqZs1/records/album.html#619775b2-1f53-409e-ad1d-5a8336b138b8_0",
    "prompt": "Modern residential houses in nature, minimalist and elegant architecture, large glass facades, surrounded by trees, mountains, or lakes, with sunlight streaming through --v 6.1",
    "url": "https://cdn.midjourney.com/619775b2-1f53-409e-ad1d-5a8336b138b8/0_0.png",
    "index": 3,
    "upscaled": true,
    "job_id": "619775b2-1f53-409e-ad1d-5a8336b138b8",
    "parent_job_id": "04bbf91d-1afa-480c-853f-b6f8c95b24b9"
  }
]
```

## 📸 Accessing Generated Images

The actor saves an "album.html" file to the KeyValue store for easy browsing and downloading of generated images. You can access it by:

- Clicking any "Album URL" field in the results table
- Going to Run > Storage > KeyValueStore and finding the "album.html" file

The album interface provides several features:

- Filter images by prompt text or other metadata
- Select multiple images for batch operations
- Open images in new tabs for detailed viewing
- Download selected images as a ZIP file

Here's an example album showcasing some generated images so you can see how your results will be displayed: [Browse Example Gallery](https://igolaizola.github.io/midjourney-automation/)

## ⚠️ Usage Guidelines and Best Practices

### Account Safety

- Automation of Midjourney accounts can result in termination
- Only use for batch jobs you would normally do manually
- Avoid running the automation 24/7
- Follow Midjourney's terms of service

### Performance Optimization

- Start with 1-2 concurrent jobs and adjust based on results
- Use proxies from your region for better reliability
- Set job timeouts appropriate for your chosen generation mode
- Regular cookie updates may be required for long sessions

### General Tips

- Test your setup with a small batch of prompts first
- Use descriptive prompts for better organization
- Monitor success rates and adjust settings as needed
- Failed jobs are logged but won't stop the entire process
- Privacy mode affects image visibility in your Midjourney profile

## 💳 How much will it cost to use Midjourney Automation?

Apify provides you with $5 free usage credits every month on the [Apify Free plan](https://apify.com/pricing). You can try and test Midjourney Automation for free with the Free plan for a limited time.

However, if you plan to use it regularly, you should get an Apify subscription. We recommend our [$49/month Personal plan](https://apify.com/pricing) - this plan covers the costs of Midjourney Automation and numerous executions.
