# Iris for Visual Studio Code

For the moment, the Iris extension provides some very useful code snippets to reduce the time you spend to write common [Iris](https://iris-go.com) Go code inside the [Microsoft's Visual Studio Code](https://code.visualstudio.com/), which is the best code editor for the [Go Language](https://golang.org).

Snippets section contains the documentation for each snippet(word that is auto-completed by the Visual Studio Code's editor when you type its prefix, with the key `<tab>` you can actually apply the code that is referring to the snippet and by pressing `<tab>` again you can change the _default values_ for each code snippet's body).

The Iris extension will install the [vscode-go](https://github.com/Microsoft/vscode-go) extension automatically for you, if it is not there already.

## Snippets

### helloweb

```go
package main

import (
    "time"

    "github.com/kataras/iris"
)

func greet(ctx iris.Context) {
    ctx.Writef("Hello World! %s", time.Now())
}

func main() {
    app := iris.New()
    app.Get("/", greet)
    app.Run(iris.Addr(":8080"))
}
```

### newapp

```go
app := iris.New()


app.Run(iris.Addr(":8080"))
```

### newsessions

```go
sessionsManager := sessions.New(sessions.Config{
    Cookie: "cookieName",
})
```

### newwebsockets

```go
ws := websocket.New(websocket.Config{
    ReadBufferSize:  2048,
    WriteBufferSize: 2048,
})
app.Any("/iris-ws.js", websocket.ClientHandler())
app.Get("/endpoint", func(ctx iris.Context) {
    conn := ws.Upgrade(ctx)
    conn.OnDisconnect(func() {})
    conn.On("event", func() {

    })
})
```

### regview

```go
app.RegisterView(iris.HTML("./views", ".html"))
```

### staticweb

```go
app.StaticWeb("/assets", "./public")
```

### staticembedded

```go
app.StaticEmbedded("/assets", "./public", Asset, AssetNames)
```

### fav

```go
app.Favicon("./public/favicon.ico")
```

### hf

```go
func(ctx iris.Context) {

}
```

### handle

```go
app.Handle("GET", "/path", func(ctx iris.Context) {

})
```

### get

```go
app.Get("/path", func(ctx iris.Context) {

})
```

### post

```go
app.Post("/path", func(ctx iris.Context) {

})
```

### put

```go
app.Put("/path", func(ctx iris.Context) {

})
```

### delete

```go
app.Delete("/path", func(ctx iris.Context) {

})
```

## Install from Marketplace

Just click the link below and press the **Install** button, [vs code](https://code.visualstudio.com/) will open and ask you if you want to install the extension.

<https://marketplace.visualstudio.com/items?itemName=kataras2006.iris>