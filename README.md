# joystick
Go Joystick API

[![GoDoc](https://godoc.org/github.com/SimulatedSimian/joystick?status.svg)](https://godoc.org/github.com/SimulatedSimian/joystick)

Package joystick implements a Polled API to read the state of an attached joystick.
currently Windows & Linux are supported.
Package is pure go and requires no external dependencies

## Installation:
```bash
$ go get github.com/simulatedsimian/joystick/...
```
## Sample Program 
```bash
$ go intstall github.com/simulatedsimian/joystick/joysticktest
$ joysticktest 0
```
Displays the state of the specified joystick
## Example:
```go
import "github.com/simulatedsimian/joystick"
```
```go
js, err := joystick.Open(jsid)
if err != nil {
  panic(err)
}

fmt.Printf("Joystick Name: %s", js.Name())
fmt.Printf("   Axis Count: %d", js.AxisCount())
fmt.Printf(" Button Count: %d", js.ButtonCount())

state, err := joystick.Read()
if err != nil {
  panic(err)
}

fmt.Printf("Axis Data: %v", state.AxisData)
js.Close()
```
