## C2O
**English**·<a href="https://github.com/He0607/coze2openai/blob/main/README_CN.md">中文</a> 

**Use Coze on your favorite OpenAI client.**

This project converts the Coze API to the OpenAI API format, giving you access to [Coze](https://www.coze.com) LLMs, knowledge base, plugins, and workflows within your preferred OpenAI clients. 


## Features
- Convert Coze API into an OpenAI API
- Support streaming and blocking
- Support Chatbots API on Coze

## Preparation
1. Register with [Coze](https://www.coze.com) and obtain your API token
![cozeapitoken](pictures/token.png)

2. Create your bot and publish it to the API
![cozeapi](pictures/api.png)

3. Obtain the bot's ID,the number after the bot parameter, and configure it as an environment variable
```bash
https://www.coze.com/space/73428668341****/bot/73428668*****
```

## Deployment
### Zeabur
[![Deploy on Zeabur](https://zeabur.com/button.svg)](https://zeabur.com/templates/BZ515Z?referralCode=fatwang2)

### Vercel
[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/fatwang2/coze2openai&env=BOT_ID&envDescription=COZE_BOT_ID)

**Note:** Vercel's serverless functions have a 10-second timeout limit.


### Local Deployment
1. Set the environment variable on `.env` file
```bash
BOT_ID=xxxx
```

2. Install dependencies 
```bash
pnpm install
```

3. Run the project
```bash
pnpm start
```

## Usage
```JavaScript
const response = await fetch('http://localhost:3000/v1/chat/completions', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json',
    'Authorization': 'Bearer YOUR_COZE_API_KEY',
  },
  body: JSON.stringify({
    model: 'Coze',
    messages: [
      { role: 'system', content: 'You are a helpful assistant.' },
      { role: 'user', content: 'Hello, how are you?' },
    ],
  }),
});

const data = await response.json();
console.log(data);
```
## Environment Variable
This project provides some additional configuration items set with environment variables:

| Environment Variable | Required | Description                                                                                                                                                               | Example                                                                                                              |
| -------------------- | -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| `BOT_ID`     | Yes      | The ID of the bot. Obtain it from the Develop page URL of your bot in Coze. The number after the bot parameter is the bot ID.| `73428668*****`|

## Roadmap
**Coming Soon**
*   Image support
*   Audio-to-text
*   Text-to-audio
*   Docker support
*   Workflow Bot
*   Variables support

**Available Now**
*   Continuous dialogue
*   Zeabur & Vercel deployment
*   Streaming & Blocking
*   Plugins on Coze

## Contact
Feel free to reach out for any questions or feedback

[X](https://sum4all.site/twitter)\
[telegram](https://sum4all.site/telegram)

<a href="https://www.buymeacoffee.com/fatwang2" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" alt="Buy Me A Coffee" style="height: 60px !important;width: 217px !important;" ></a>

## License
This project is licensed under the MIT License.
