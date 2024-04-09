<!-- markdownlint-disable MD030 -->

# Flowise Embed

Javascript library to display flowise chatbot on your website

![Flowise](https://github.com/FlowiseAI/FlowiseChatEmbed/blob/main/images/ChatEmbed.gif?raw=true)

Install:

```bash
yarn install
```

Dev:

```bash
yarn dev
```

Build:

```bash
yarn build
```

## Embed in your HTML

### PopUp

```html
<script type="module">
  import Chatbot from 'https://cdn.jsdelivr.net/gh/aritellavsn/ApexMchat/dist/web.js';
  Chatbot.init({
    chatflowid: '<chatflowid>',
    apiHost: 'http://localhost:3000',
  });
</script>
```

### FullPage

```html
<script type="module">
  import Chatbot from './web.js';
  Chatbot.initFull({
    chatflowid: '<chatflowid>',
    apiHost: 'http://localhost:3000',
  });
</script>
<devinai-fullchatbot></devinai-fullchatbot>
```

To enable full screen, add `margin: 0` to <code>body</code> style, and confirm you don't set height and width

```html
<body style="margin: 0">
  <script type="module">
    import Chatbot from './web.js';
    Chatbot.initFull({
      chatflowid: '<chatflowid>',
      apiHost: 'http://localhost:3000',
      theme: {
        chatWindow: {
          // height: 700, don't set height
          // width: 400, don't set width
        },
      },
    });
  </script>
</body>
```

## Configuration

You can also customize chatbot with different configuration

```html
<script type="module">
  import Chatbot from 'https://cdn.jsdelivr.net/gh/aritellavsn/ApexMchat/dist/web.js';
  Chatbot.init({
    chatflowid: '91e9c803-5169-4db9-8207-3c0915d71c5f',
    apiHost: 'http://localhost:3000',
    chatflowConfig: {
      // topK: 2
    },
    observersConfig: {
      // (optional) Allows you to execute code in parent based upon signal observations within the chatbot.
      // The userinput field submitted to bot ("" when reset by bot)
      observeUserInput: (userInput) => {
        console.log({ userInput });
      },
      // The bot message stack has changed
      observeMessages: (messages) => {
        console.log({ messages });
      },
      // The bot loading signal changed
      observeLoading: (loading) => {
        console.log({ loading });
      },
    },
    theme: {
            button: {
                backgroundColor: "#3888AD",
                right: 20,
                bottom: 20,
                size: "medium",
                iconColor: "white",
                customIconSrc: "https://i.imgur.com/iJDkLk3.png",
            },

            chatWindow: {
                title: ‘Chat Agent,
                titleAvatarSrc: 'https://i.imgur.com/x7kgWUM.png',
                welcomeMessage: "Hello! How can I help?",
                backgroundColor: "#ffffff",
                fontSize: 16,
                poweredByTextColor: "#3888AD",
                botMessage: {
                    backgroundColor: "#f7f8ff",
                    textColor: "#303235",
                    showAvatar: true,
                    avatarSrc: "https://i.imgur.com/e8emxwj.png",
                },

                userMessage: {
                    backgroundColor: "#000000",
                    textColor: "#ffffff",
                    showAvatar: true,
                    avatarSrc: "https://i.imgur.com/6UAV5t9.png",
                },
                textInput: {
                    placeholder: "Type your question",
                    backgroundColor: "#ffffff",
                    textColor: "#303235",
                    sendButtonColor: "#3888AD",
                },
            },
        },
    });
</script>
```

## License

Source code in this repository is made available under the [MIT License](https://github.com/FlowiseAI/Flowise/blob/master/LICENSE.md).
