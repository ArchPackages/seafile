# seafile — Arch Linux package

Packaging for [Seafile](https://github.com/haiwen/seafile) 9.0.22, the Seafile
sync daemon (`seaf-daemon`).

## Fork provenance

Forked from the AUR package **seafile**:

<https://aur.archlinux.org/packages/seafile>  
<https://aur.archlinux.org/seafile.git>

Originally packaged and maintained by **Joffrey** <j-off@live.fr>, with
contributions from **eolianoe**, **Edvinas Valatka** and **Aaron Lindsay**.
Many thanks to them, and to the Seafile developers at Haiwen for the upstream
project.

This fork is maintained by **Miroslav Pavleski** <miroslav@pavleski.net>.

## Change in this fork

Requires `libwebsockets >= 5.0.0`. libwebsockets 4.5.8 calls process-wide
`OPENSSL_cleanup()` when Seafile tears down its notification context, which
later crashes `seaf-daemon` inside OpenSSL while libcurl is still using it.

Build with `makepkg -f`; install with `pacman -U`.
