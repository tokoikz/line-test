### リッチメッセージをAPIで送る

* LINEアプリにするかどうかは、一旦保留（今やることではない）

* リファレンス
https://developers.line.biz/ja/reference/messaging-api/#send-push-message

My-first-app
https://github.com/tokoikz/my_first_app

* チャネルアクセストークン
https://developers.line.biz/console/channel/1660801483/messaging-api


curl -v -X POST https://api.line.me/v2/bot/message/push \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer zl11V8FNpU8TJHmpbwto49dkJvXecFSXd7aDyhkMOu8PO4BvciFwLcM+dfhod0qjWT3eqR9Sn1+1DBBxoa72s8TpGAbTJg91BBPaCiIG49z0uNHqEGlrS3RUOkUT+XKHfo+NRe0b4j6yOAGAML7KwgdB04t89/1O/w1cDnyilFU=' \
-H 'X-Line-Retry-Key: ae5d5955-9c42-240f-b83d-9b0591a73585' \
-d '{
    "to": "U84b063c39a1319cec8ea0838a8686b76",
    "messages":[
        {
            "type":"text",
            "text":"Hello, world1"
        },
        {
            "type":"text",
            "text":"Hello, world2"
        }
    ]
}'

Ub946695a7676a19189990b952fcbf227（戸張さん）
U310fc0b5299ac5ae291a0e2683a5cc94（柴田さん）
U400ffaaf95d7d4438e4588170c8bb7c1（冨田さん）
U84b063c39a1319cec8ea0838a8686b76（床井）

curl -v -X POST <https://api.line.me/v2/bot/message/push> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer zl11V8FNpU8TJHmpbwto49dkJvXecFSXd7aDyhkMOu8PO4BvciFwLcM+dfhod0qjWT3eqR9Sn1+1DBBxoa72s8TpGAbTJg91BBPaCiIG49z0uNHqEGlrS3RUOkUT+XKHfo+NRe0b4j6yOAGAML7KwgdB04t89/1O/w1cDnyilFU=' \
-H ''X-Line-Retry-Key: ae585956-1c42-440f-b031-9b0591a73085' \
-d '{
    "to": "U84b063c39a1319cec8ea0838a8686b76",
    "messages":[
        {
            "type":"text",
            "text":"Hello, world1"
        },
        {
            "type":"text",
            "text":"Hello, world2"
        }
    ]
}'



curl -X POST \
-H "Content-Type: application/json" \
-H "Authorization: Bearer zl11V8FNpU8TJHmpbwto49dkJvXecFSXd7aDyhkMOu8PO4BvciFwLcM+dfhod0qjWT3eqR9Sn1+1DBBxoa72s8TpGAbTJg91BBPaCiIG49z0uNHqEGlrS3RUOkUT+XKHfo+NRe0b4j6yOAGAML7KwgdB04t89/1O/w1cDnyilFU=" \
-d '{
  "to": "U84b063c39a1319cec8ea0838a8686b76",
  "messages": [
    {
      "type": "flex",
      "altText": "Flex Message",
      "contents": {
        "type": "bubble",
        "body": {
          "type": "box",
          "layout": "vertical",
          "contents": [
            {
              "type": "text",
              "text": "Hello, World!"
            }
          ]
        }
      }
    }
  ]
}' \
https://api.line.me/v2/bot/message/push
