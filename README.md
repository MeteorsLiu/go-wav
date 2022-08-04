# go-wav ![workflow status](https://github.com/youpy/go-wav/actions/workflows/go.yml/badge.svg)

A fork of github.com/youpy/go-wav.

More python-like interface was added.


usage:


```
ackage main

import (
	"flag"
	"fmt"
	"github.com/youpy/go-wav"
	"io"
	"os"
)

func main() {
	infile_path := flag.String("infile", "", "wav file to read")
	flag.Parse()

	file, _ := os.Open(*infile_path)
	reader := wav.NewReader(file)

  defer file.Close()
  // You can get python-like info about the wav file by calling this method.
  info, err := reader.Info()
  fmt.Println("The number of frames: %d", info.NFrames)
  fmt.Println("The number of channels: %d", info.NChannels)
  fmt.Println("The sample width of files: %d", info.SampleWidth)
  fmt.Println("The frame rate of files: %d", info.FrameRate)
```

