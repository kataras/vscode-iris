# Iris for Visual Studio Code

For the moment, the Iris extension provides some very useful code snippets to reduce the time you spend to write common [Iris](https://iris-go.com) Go code inside the [Microsoft's Visual Studio Code](https://code.visualstudio.com/), which is the best code editor for the [Go Language](https://golang.org).

Snippets section contains the documentation for each snippet(word that is auto-completed by the Visual Studio Code's editor when you type its prefix, with the key `<tab>` you can actually apply the code that is referring to the snippet and by pressing `<tab>` again you can change the _default values_ for each code snippet's body).

The Iris extension will install the [vscode-go](https://github.com/golang/vscode-go) extension automatically for you, if it is not there already.

## Snippets

### pc

```go
app.PartyConfigure("/", new(users.API))

```

### api

```go
package api

import (
	"github.com/kataras/iris/v12"
)

type API struct {
}

func (api *API) Configure(r iris.Party) {
	
}
```

### helloweb

```go
package main

import (
    "time"

    "github.com/kataras/iris/v12"
)

func greet(ctx iris.Context) {
    ctx.Writef("Hello World! %s", time.Now())
}

func main() {
    app := iris.New()
    app.Get("/", greet)
    app.Listen(":8080")
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

### regview

```go
app.RegisterView(iris.HTML("./views", ".html"))
```

### handledir

```go
app.HandleDir("/path", "./directory")
```

### staticembedded

```go
app.HandleDir("/path", "./directory", iris.DirOptions{Asset: Asset, AssetNames: AssetNames})
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
