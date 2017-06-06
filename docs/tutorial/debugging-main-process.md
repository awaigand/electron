# Debugging the Main Process

The DevTools in an Electron browser window can only debug JavaScript that's
executed in that window (i.e. the web pages). To debug JavaScript that's
executed in the main process you will need to use an external debugger and
launch Electron with the `--inspect` or `--inspect-brk` switch since version 1.7.2a.
For versions prior to 1.7.2a, see [the equivalent tutorial on the project page](https://electron.atom.io/docs/tutorial/debugging-main-process/).

## Command Line Switches (since 1.7.2a)

Use one of the following command line switches to enable debugging of the main
process:

### `--inspect=[port]`

Electron will listen for V8 inspector protocol messages on the specified `port`,
an external debugger will need to connect on this port. The default `port` is
`5858`.

```shell
electron --inspect=5858 your/app
```

### `--inspect-brk=[port]`

Like `--inspect` but pauses execution on the first line of JavaScript.

## External Debuggers

You will need to use a debugger that supports the V8 inspector protocol.

- Connect Chrome by visiting `chrome://inspect` and selecting to inspect the
  launched Electron app present there.
- [Debugging the Main Process in VSCode](debugging-main-process-vscode.md)
