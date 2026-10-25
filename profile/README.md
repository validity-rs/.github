<picture>
  <source media="(prefers-color-scheme: dark)" srcset="banner-dark.svg">
  <img alt="validity-rs — fingerprint login on Linux for Synaptics/Validity sensors, written in Rust" src="banner-light.svg" width="100%">
</picture>

<p align="center">
  <a href="https://validity-rs.github.io"><b>Website</b></a> ·
  <a href="https://github.com/validity-rs/validity-rs#install">Install</a> ·
  <a href="https://github.com/validity-rs/validity-rs/releases/latest">Downloads</a> ·
  <a href="https://validity-rs.github.io/apt">APT repository</a> ·
  <a href="https://github.com/validity-rs/validity-rs/issues">Report a laptop</a>
</p>

<p align="center">
  <a href="https://github.com/validity-rs/validity-rs/releases/latest"><img alt="Release" src="https://img.shields.io/github/v/release/validity-rs/validity-rs?style=flat-square&color=26608e&label=release"></a>
  <img alt="Rust" src="https://img.shields.io/badge/rust-1.99%2B-26608e?style=flat-square&logo=rust">
  <img alt="Sensor" src="https://img.shields.io/badge/sensor-06cb%3A009a-26608e?style=flat-square">
  <a href="https://github.com/validity-rs/validity-rs/blob/main/LICENSE"><img alt="MIT" src="https://img.shields.io/badge/license-MIT-26608e?style=flat-square"></a>
</p>

The 2018 ThinkPads (T480, T480s, X280, X1 Carbon 6) ship a Synaptics **match-on-chip** fingerprint reader that libfprint doesn't drive. validity-rs speaks its encrypted protocol in Rust and serves **fprintd's D-Bus API**, so `fprintd-enroll`, `pam_fprintd`, desktops and screen lockers just work.

| | Project | What it is |
|---|---|---|
| 🔐 | [**validity-rs**](https://github.com/validity-rs/validity-rs) | The driver and `validity-daemon`, a drop-in replacement for fprintd's service. Optional PAM profile. |
| 👆 | [**fingerprint-settings**](https://github.com/validity-rs/fingerprint-settings) | *Fingerprints*: one screen, one button to register your finger. For Xfce, MATE, LXQt. GTK 4 / libadwaita. |
| 📦 | [**apt**](https://github.com/validity-rs/apt) | Signed APT repository for Debian 13 and Ubuntu 24.04 / 26.04. |
| 🌐 | [**validity-rs.github.io**](https://github.com/validity-rs/validity-rs.github.io) | The website. |

#### Why trust it

- **Templates never leave the sensor.** Matching happens on the chip; the host only learns *which* finger matched.
- **The password always works.** No package touches your PAM config; every failure falls back to the password.
- **Reproducible, attested packages** for Debian, Ubuntu, Fedora, Arch and Alpine, each one installed and tested in CI.
- **Fuzzed, mutation-tested**, and checked byte for byte against [python-validity](https://github.com/uunicorn/python-validity).

```sh
lsusb | grep -iE '06cb|138a'   # 06cb:009a? You're in.
```

<sub>Got a T480s, X280 or X1 Carbon 6? It should work, but nobody has tested it yet. <a href="https://github.com/validity-rs/validity-rs/issues">Tell us how it goes</a>.</sub>
