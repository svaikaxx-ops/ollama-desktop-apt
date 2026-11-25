# ollama-desktop — apt saugykla

AI darbalaukis Linux'ui (Debian 13 „trixie“, amd64). Čia — tik surinkti `.deb` paketai;
kodas ir pakeitimai — pagrindinėje repozitorijoje.

## Diegimas

```sh
sudo curl -fsSLo /usr/share/keyrings/ollama-desktop-archive-keyring.gpg \
  https://svaikaxx-ops.github.io/ollama-desktop-apt/ollama-desktop-archive-keyring.gpg
sudo curl -fsSLo /etc/apt/sources.list.d/ollama-desktop.sources \
  https://svaikaxx-ops.github.io/ollama-desktop-apt/ollama-desktop.sources
sudo apt update && sudo apt install ollama-desktop
```

Toliau nauja versija ateina kartu su sistemos atnaujinimais: `sudo apt update && sudo apt upgrade`
(arba programoje ⚙ → 🔄 Atnaujinimai → „⬆ Atnaujinti sistemą (apt)“).

Parašo raktas: `1BFD 33F2 B535 B2EC 115C  C0F6 1455 8486 096C 018F`
(ed25519, „ollama-desktop apt“, galioja iki 2031-11-19).

## Įdiegiamas atvaizdas (ISO)

Debian 13 + ollama-desktop (gyva sesija ir diegiklis) —
[Releases](https://github.com/svaikaxx-ops/ollama-desktop-apt/releases/latest): `ollama-desktop-*-amd64.iso`,
`SHA256SUMS`, `SHA256SUMS.sign`.

```sh
gpgv --keyring ./ollama-desktop-archive-keyring.gpg SHA256SUMS.sign SHA256SUMS && sha256sum -c SHA256SUMS
sudo dd if=ollama-desktop-*-amd64.iso of=/dev/sdX bs=4M conv=fsync   # sdX — USB raktas
```

Visas darbalaukis vietoj kito (prisijungimas iškart į ollama-desktop): `ollama-desktop-login`.
