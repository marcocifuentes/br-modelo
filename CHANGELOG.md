# Changelog

Todas as mudanças relevantes deste projeto serão documentadas aqui.

---

## [v1.0] - 2026-05-23

### Added

* Guia manual de instalação do **brModelo** no Linux
* Documentação validada para Fedora 42/43, Debian 13 e Ubuntu 26.04 LTS
* Integração ao menu de aplicativos via launcher `.desktop`
* Download do `brModelo.jar` e ícone oficial via `curl`
* Estrutura de documentação separada:

  * `docs/instalacao.md`
  * `docs/troubleshooting.md`
* Guia de troubleshooting para falhas comuns de Java, GUI e launcher
* Validação prática em ambiente GNOME / Wayland

### Changed

* Recomendação de **Java 21** como versão validada para execução
* Ajustes de documentação para compatibilidade entre distribuições Linux
* Refinamento do processo de instalação e validação do ambiente
* Inclusão de validação prática no Fedora 43

### Fixed

* Documentação para diagnóstico de `HeadlessException`
* Orientação para seleção correta do Java via `alternatives` / `update-alternatives`
* Diagnóstico para problemas relacionados ao launcher `.desktop`
* Troubleshooting para erros comuns de execução do ambiente Java

### Known Issues

* Não funciona em ambientes headless
* Não funciona em TTY (terminal sem sessão gráfica)
* SSH requer X11 forwarding para aplicações gráficas
* Algumas distribuições podem exigir ajuste manual da versão ativa do Java

### Notes

* Este projeto documenta uma instalação manual
* Não utiliza empacotamento (Flatpak/Snap/AppImage)
* Compatibilidade depende do ambiente Linux e da configuração do Java
