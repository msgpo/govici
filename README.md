# go-vici

## About

The strongSwan [vici protocol](https://www.strongswan.org/apidoc/md_src_libcharon_plugins_vici_README.html) is used for external applications to monitor, configure, and control the IKE daemon charon. This go package provides a pure-go implementation of a vici client.

## Getting started
`go get -u github.com/enr0n/vici`

## Usage

```go
package main

import (
	"fmt"

	"github.com/enr0n/vici"
)

func main() {
	session, err := vici.NewSession()
	if err != nil {
		fmt.Println(err)
		return
	}

	m, err := session.Version()
	if err != nil {
		fmt.Println(err)
		return
	}

	fmt.Printf("%v %v\n", m.Get("daemon"), m.Get("version"))
}
```

For a complete list of examples, look in the `_examples` directory.
