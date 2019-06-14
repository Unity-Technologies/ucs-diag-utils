## Unity Cache Server Diagnostic Tools

### Client Stream Player


#### Usage

`stream_player.js [options] <filePath> [ServerAddress]`

Option                          | Description
------------------------------- | -----------
  -i --iterations <n>           | Number of times to send the recorded session to the server (default: 1)
  -c --max-concurrency <n>      | Number of concurrent connections to make to the server (default: 1)
  -d --debug-protocol           | Print protocol stream debugging data to the console.
  -q --no-verbose               | Do not show progress and result statistics.
  -h, --help                    | Show usage information.
  
#### Description

The stream player can read one ore more recorded client session at `<filePath>`, optionally print the protocol stream to the console, and optionally send the protocol stream to a remote Cache Server at `[ServerAddress]` for e.g. performance load testing.

#### Notes

* If `<filePath>` is a directory, all files within the directory (recursively) will be read and played back. Some rudimentary validation is done on each file to detect whether or not it is a valid client session stream.
* If `[ServerAddress]` is omitted, data will be sent to a temporary "no-op" TCP server. This is useful if you are only concerned with reading the debug protocol stream with the `-d` option.
