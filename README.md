# webview_go (Ubuntu 24.04 compatible fork)

This is a fork of [webview/webview_go](https://github.com/webview/webview_go) updated for **Ubuntu 24.04** compatibility.
The original project provides Go bindings for [webview](https://github.com/webview/webview), a tiny cross-platform library to render web-based GUIs using native web engines.

## Overview

This fork ensures smooth building and runtime support on **Ubuntu 24.04 (Noble Numbat)**, fixing issues caused by:

* Updated GTK and WebKit2GTK versions
* Library path or pkg-config resolution differences

The API and usage remain **fully compatible** with the upstream project.

## Key Changes

* Updated **CGO linker flags** for Ubuntu 24.04.
* Adjusted build scripts for compatibility with **WebKitGTK 4.1** and **GTK 3.24+**.

## Installation

### Prerequisites

Ensure you have the necessary dependencies installed:

```bash
sudo apt update
sudo apt install libwebkit2gtk-4.1-dev
```

### Get the module

```bash
go get github.com/cretingame/webview_go_ubuntu
```

Or clone manually:

```bash
git clone https://github.com/cretingame/webview_go_ubuntu.git
cd webview_go_ubuntu
```
***

# webview_go

[![GoDoc](https://godoc.org/github.com/webview/webview_go?status.svg)](https://godoc.org/github.com/webview/webview_go)
[![Go Report Card](https://goreportcard.com/badge/github.com/webview/webview_go)](https://goreportcard.com/report/github.com/webview/webview_go)

Go language binding for the [webview library][webview].

> [!NOTE]
> Versions <= 0.1.1 are available in the [old repository][webview].

### Getting Started

See [Go package documentation][go-docs] for the Go API documentation, or simply read the source code.

Start with creating a new directory structure for your project.

```sh
mkdir my-project && cd my-project
```

Create a new Go module.

```sh
go mod init example.com/app
```

Save one of the example programs into your project directory.

```sh
curl -sSLo main.go "https://raw.githubusercontent.com/cretingame/webview_go_ubuntu/master/examples/basic/main.go"
```

Install dependencies.

```sh
go get github.com/cretingame/webview_go_ubuntu
```

Build the example. On Windows, add `-ldflags="-H windowsgui"` to the command line.

```sh
go build
```

### Notes

Calling `Eval()` or `Dispatch()` before `Run()` does not work because the webview instance has only been configured and not yet started.

[go-docs]: https://pkg.go.dev/github.com/webview/webview_go
[webview]: https://github.com/webview/webview
