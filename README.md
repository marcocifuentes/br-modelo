# brModelo Linux Installer

Instalador manual do brModelo para Linux com integração ao menu de aplicativos.

---

## Descrição

Este repositório fornece um guia simples e validado para instalação do **brModelo** no Linux.

A instalação inclui:

- download do `brModelo.jar`
- organização dos arquivos locais
- configuração de ícone
- criação de launcher `.desktop`
- integração ao menu de aplicativos

---

## Distribuições testadas

- Fedora 42 / 43 Workstation (GNOME / Wayland)
- Debian 13 (GNOME)
- Ubuntu 26.04 LTS (GNOME)

---

## Pré-requisitos

- Java 21 (recomendado)
- curl
- ambiente gráfico Linux ativo (GNOME/KDE/XFCE)
- suporte a XDG Desktop Entry (.desktop)

---

## ⚠️ Compatibilidade do Java

Recomendado: **Java 21**

Versões mais recentes (ex: Java 25) podem causar problemas com aplicações Swing/AWT em algumas distribuições Linux.

Verifique a versão ativa:

```bash
java --version
```

Se necessário, ajuste a versão padrão:

```bash
sudo alternatives --config java
```

---

## Instalação

Consulte o guia completo:

```text
docs/instalacao.md
```

---

## Escopo

Este projeto é um instalador manual baseado em documentação.

Não garante compatibilidade universal entre distribuições Linux. O funcionamento depende de:

- versão do Java ativa no sistema
- ambiente gráfico (GNOME/KDE/XFCE)
- disponibilidade de ferramentas básicas do sistema

---

## Limitações importantes

- Não funciona em SSH sem X11 forwarding
- Não funciona em TTY (terminal puro sem GUI)
- Requer sessão gráfica ativa para aplicações Swing/AWT

---

## Fontes

- http://www.sis4.com/brModelo/index.html  
- https://github.com/chcandido/brModelo  

---

# Summary (English)

This repository provides a manual and validated installation guide for **brModelo** on Linux.

It includes:

- downloading the `brModelo.jar`
- setting up local application structure
- desktop launcher integration
- menu integration

---

## Tested distributions

- Fedora 42 / 43 Workstation
- Debian 13
- Ubuntu 26.04 LTS

---

## Requirements

- Java 21 (recommended)
- curl
- active Linux desktop environment (GNOME/KDE/XFCE)
- XDG desktop entry support (.desktop files)

---

## Notes

This installer is manual and does not guarantee universal compatibility across all Linux environments.

See full instructions in `docs/instalacao.md`.
```