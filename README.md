# Hysteria 2 subscription

Stable subscription URL:

```text
https://raw.githubusercontent.com/Aricept094/hy2-subscription/refs/heads/main/sub.txt
```

One-click Karing import:

```text
karing://install-config?url=https%3A%2F%2Fraw.githubusercontent.com%2FAricept094%2Fhy2-subscription%2Frefs%2Fheads%2Fmain%2Fsub.txt&name=Frankfurt%20Hysteria%202
```

`sub.txt` contains one proxy URI per line. Update that file to add, replace, or
remove servers without changing the subscription URL configured in clients.

The feed intentionally contains only node URIs. Karing remains responsible for
DNS, TUN mode, routing rules, automatic selection, and latency testing. The
Hysteria URI supplies the endpoint, authentication, trusted TLS/SNI, and
Salamander obfuscation settings. It does not include `up` or `down` bandwidth
hints, so Karing does not inadvertently activate Brutal congestion control with
an inaccurate link rate.

## Port hopping

The final node uses Karing-compatible Hysteria 2 multi-port URI syntax:
`hysteria2://...:30000,30001-30100?...`. Port `30000` is the server's base
listener and `30001-30100` is the hopping range. Karing's URI importer requires
the base port before the comma; a bare `:30000-30100` range can be silently
dropped even though it is accepted by the official Hysteria client.

After updating Karing, refresh or re-import this profile so the stored node is
replaced. If an iOS build shows the final node as a single fixed port, update
Karing before troubleshooting the server; Karing has had platform-specific
port-hopping and `server_ports` conversion issues.

This repository is public. Anyone with access to it can read and use the proxy
credentials in the subscription.
