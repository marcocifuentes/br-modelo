# brModelo Linux Installer

Instalador manual do brModelo para Linux com integração ao menu de aplicativos.

---

## Descrição

Este repositório fornece um guia simples e validado para instalação do **brModelo** no Linux.

A instalação inclui:

* download do `brModelo.jar`
* organização dos arquivos locais
* configuração de ícone
* criação de launcher `.desktop`
* integração ao menu de aplicativos

---

## Distribuições testadas

* Fedora 42 / 43 Workstation (GNOME / Wayland)
* Debian 13 (GNOME)
* Ubuntu 26.04 LTS (GNOME)

---

## Pré-requisitos

* Java 21 (recomendado)
* curl
* ambiente gráfico Linux ativo (GNOME/KDE/XFCE)
* suporte a XDG Desktop Entry (`.desktop`)

---

## Documentação

### Instalação

```text
docs/instalacao.md
```

### Troubleshooting

```text
docs/troubleshooting.md
```

### Changelog

```text
CHANGELOG.md
```

---

## Compatibilidade

O projeto foi validado com **Java 21**.

Versões mais recentes do Java podem exigir ajustes dependendo da distribuição Linux e ambiente gráfico.

Verifique a versão ativa:

```bash
java --version
```

---

## Escopo

Este projeto documenta um processo manual de instalação do **brModelo** no Linux.

O funcionamento pode variar conforme:

* versão ativa do Java
* ambiente gráfico (GNOME/KDE/XFCE)
* configuração do sistema

---

## Limitações conhecidas

* requer ambiente gráfico ativo
* não funciona em TTY (terminal puro)
* não funciona em SSH sem X11 forwarding
* depende de Java configurado corretamente

---
## Créditos

O **brModelo** é um software desenvolvido por terceiros.

Este repositório **não mantém, modifica ou distribui o código-fonte do brModelo**, apenas documenta um processo manual de instalação e integração no Linux.

Projeto original do brModelo:

* Site oficial: http://www.sis4.com/brModelo/index.html
* Repositório comunitário: https://github.com/chcandido/brModelo

Objetivo deste repositório:

* documentar uma instalação manual validada no Linux
* facilitar a integração ao menu de aplicativos
* registrar troubleshooting e compatibilidade testada
---

# Summary (English)

This repository provides a validated manual installation guide for **brModelo** on Linux.

It includes:

* `brModelo.jar` installation
* local application structure
* desktop launcher setup
* desktop menu integration
* troubleshooting documentation

## Tested distributions

* Fedora 42 / 43 Workstation
* Debian 13
* Ubuntu 26.04 LTS

## Requirements

* Java 21 (recommended)
* curl
* active Linux desktop environment
* XDG Desktop Entry support (`.desktop`)

## Documentation

Installation guide:

```text
docs/instalacao.md
```

Troubleshooting guide:

```text
docs/troubleshooting.md
```

Changelog:

```text
CHANGELOG.md
```
