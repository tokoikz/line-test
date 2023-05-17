<template>
  <!-- UI components here -->
  <button @click="sendRichMessage">Send Message</button>
</template>

<script>
import axios from 'axios';

export default {
  methods: {
    sendRichMessage() {
      const headers = {
        "Authorization": "Bearer {CHANNEL_ACCESS_TOKEN}",
        "Content-Type": "application/json"
      };

      const data = {
        "to": "{USER_ID}",
        "messages": [
          {
            "type": "template",
            "altText": "This is a buttons template",
            "template": {
              "type": "buttons",
              "thumbnailImageUrl": "https://example.com/original.jpg",
              "imageAspectRatio": "rectangle",
              "imageSize": "cover",
              "imageBackgroundColor": "#FFFFFF",
              "title": "Menu",
              "text": "Please select",
              "defaultAction": {
                "type": "uri",
                "label": "View detail",
                "uri": "http://example.com/page/123"
              },
              "actions": [
                {
                  "type": "postback",
                  "label": "Buy",
                  "data": "action=buy&itemid=123"
                },
                {
                  "type": "postback",
                  "label": "Add to cart",
                  "data": "action=add&itemid=123"
                },
                {
                  "type": "uri",
                  "label": "View detail",
                  "uri": "http://example.com/page/123"
                }
              ]
            }
          }
        ]
      };

      axios
        .post('https://api.line.me/v2/bot/message/push', data, { headers })
        .then(response => {
          console.log(response.data);
        })
        .catch(error => {
          console.error(error);
        });
    }
  }
};
</script>
