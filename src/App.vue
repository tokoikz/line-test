<template>
  <div>
    <button @click="sendPostRequest">Send Message</button>
  </div>
</template>

<script>
export default {
  methods: {
    sendPostRequest() {
      const url = 'https://api.line.me/v2/bot/message/push'; // リクエストを送信するエンドポイントのURL

      const data = {
        to: 'U84b063c39a1319cec8ea0838a8686b76',
        messages: [
          {
            type: 'flex',
            altText: 'Flex Message',
            contents: {
              type: 'bubble',
              body: {
                type: 'box',
                layout: 'vertical',
                contents: [
                  {
                    type: 'text',
                    text: 'Hello, World!'
                  }
                ]
              }
            }
          }
        ]
      };

      fetch(url, {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
          'Authorization': 'Bearer zl11V8FNpU8TJHmpbwto49dkJvXecFSXd7aDyhkMOu8PO4BvciFwLcM+dfhod0qjWT3eqR9Sn1+1DBBxoa72s8TpGAbTJg91BBPaCiIG49z0uNHqEGlrS3RUOkUT+XKHfo+NRe0b4j6yOAGAML7KwgdB04t89/1O/w1cDnyilFU='
        },
        body: JSON.stringify(data)
      })
        .then(response => {
          if (response.ok) {
            console.log('Message sent successfully');
          } else {
            console.error('Failed to send message');
          }
        })
        .catch(error => {
          console.error('Error sending message:', error);
        });
    }
  }
};
</script>