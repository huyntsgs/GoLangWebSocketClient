# GoLang Websocket

  This project was created to test GoLang as a WebSocket Server.

## Go Dependencies

  `go get github.com/gorilla/websocket`

  `go get github.com/satori/go.uuid`

## Use

  `go run main.go`

## Disclaimer

    I obtained *ALL* this code and documentation from other sources.

## Architecture

```

package main

import (
  "encoding/json"
  "fmt"
  "net/http"
  "github.com/gorilla/websocket"
  "github.com/satori/go.uuid"
)

    type ClientManager struct {
        clients    map[*Client]bool
        broadcast  chan []byte
        register   chan *Client
        unregister chan *Client
    }

    type Client struct {
        id     string
        socket *websocket.Conn
        send   chan []byte
    }

    type Message struct {
        Sender    string `json:"sender,omitempty"`
        Recipient string `json:"recipient,omitempty"`
        Content   string `json:"content,omitempty"`
    }


```

  At this point the Golang application can be run with the following:

    `go run main.go`

  Note: You cannot test it in your web browser, but a websocket connection can be established at

    `ws://localhost:12345/ws`
