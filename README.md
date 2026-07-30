# Hysteria 2 subscription

Stable subscription URL:

```text
https://raw.githubusercontent.com/Aricept094/hy2-subscription/refs/heads/main/karing.txt
```

One-click Karing import:

```text
karing://install-config?url=https%3A%2F%2Fraw.githubusercontent.com%2FAricept094%2Fhy2-subscription%2Frefs%2Fheads%2Fmain%2Fkaring.txt&name=Poland%20Hysteria%202
```

`sub.txt` contains one proxy URI per line. Update that file to add, replace, or
remove servers without changing the subscription URL configured in clients.

The feed intentionally contains only node URIs. Karing remains responsible for
DNS, TUN mode, routing rules, automatic selection, and latency testing. The
Hysteria URI supplies the endpoint, authentication, trusted TLS/SNI, and
Salamander obfuscation settings. It does not include `up` or `down` bandwidth
hints, so Karing does not inadvertently activate Brutal congestion control with
an inaccurate link rate.

This repository is public. Anyone with access to it can read and use the proxy
credentials in the subscription.
