# eay-console

The web console for [eay-gateway](https://github.com/nannndev/eay-gateway). A single
`index.html` with no build step and no dependencies. It talks to the gateway's API like any other
client: overview, live activity and subagents, a streaming playground, providers and OAuth logins,
MCP tools, routing, skills, agents and keys.

## Use it

**Hosted:** open <https://nannndev.github.io/eay-console/> and start the gateway with that origin
allowed:

```sh
eay-gateway --console-origin https://nannndev.github.io
```

**Locally:** any static server on `localhost` works with no gateway flags, because the gateway
always allows `http://localhost:<port>`:

```sh
python3 -m http.server 8080   # then open http://localhost:8080
```

The console connects to `http://127.0.0.1:20129` by default. Change it in the sidebar, or open the
page with `?gateway=http://host:port`. If the gateway runs with `--admin-token`, the console asks
for it.

## Security notes

- The gateway refuses browser requests from origins it does not trust, so other websites cannot
  use it. Only add origins you control to `--console-origin`.
- The gateway URL and admin token are kept in this browser's local storage.
- If your gateway is reachable from other machines, always set `--admin-token`.

## License

MIT
