# go-oled-i2c

[![Go Report Card](https://goreportcard.com/badge/github.com/sachingorade/go-oled-i2c)](https://goreportcard.com/report/github.com/sachingorade/go-oled-i2c)
[![GoDoc](https://godoc.org/github.com/sachingorade/go-oled-i2c?status.svg)](https://godoc.org/github.com/sachingorade/go-oled-i2c)
[![MIT License](http://img.shields.io/badge/License-MIT-yellow.svg)](./LICENSE)

Go implementation for .96 OLED I2C manipulation

This is a very basic Go implementation for 0.96" Oled i2c display manipulation.

## Why
Story behing this library is that I have an Omega2+ with me and I wanted to do something with it(which should be suited 
for this little beast's capability). So I decided to build a local file server with this. Now a basic file server is okay
but I also have various 0.96" Oled display with me so decided to add for this file server.

I tried initializing this Oled with Go's Periph package but it was not working. So while searching for other i2c libraries
for Go, I found [go-i2c](https://github.com/d2r2/go-i2c/) and it was working.. TADA!

So I wrote this wrapper around this library for 0.96" Oled display.

## Features
As of now the library is very basic and only supports,
1. Switch on/off display functions
1. Clear function
1. Write text function
1. Set cursor function

## Usage
Library is very easy to use. Check the following example,
```go
package main

import (
	"log"
	goled "github.com/sachingorade/go-oled-i2c"
)

func main() {
	oled, err := goled.BeginOled()
	if err != nil {
		log.Fatal(err)
		return
	}
	defer oled.Close()

	oled.Clear()

	oled.Write("Hello from go!")
}
```

## License
Licensed under MIT :)
