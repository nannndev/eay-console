# eay-console

The web console for [eay-gateway](https://github.com/nannndev/eay-gateway): one self-contained
`index.html` (no build step, no dependencies).

The gateway embeds this file at build time and serves it at `http://127.0.0.1:20129/` and `/ui`,
so the console talks to the gateway on the same origin.

## Editing

1. Edit `index.html` here and push.
2. In eay-gateway, move the submodule to the new commit and rebuild:

   ```sh
   git submodule update --remote crates/eay-gateway/console
   git add crates/eay-gateway/console && git commit -m "chore: update console"
   cargo run --bin eay-gateway
   ```

To try changes without a commit, edit `crates/eay-gateway/console/index.html` inside your
eay-gateway checkout and rebuild; push from that folder when done.

## License

MIT
