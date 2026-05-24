# Changelog

Todas as mudanças relevantes deste projeto serão documentadas aqui.

---

## [v1.0] - 2026-05-23

### Added
- Guia completo de instalação manual do brModelo no Linux
- Suporte documentado para Fedora 42/43, Debian 13 e Ubuntu 26.04 LTS
- Criação de launcher `.desktop` com integração ao menu do sistema
- Download automatizado do `brModelo.jar` e ícone oficial
- Estrutura de documentação separada (`docs/instalacao.md`)
- Validação prática em ambientes com GNOME / Wayland

### Fixed
- Ajuste de compatibilidade com Java (fixação de Java 21 como recomendado)
- Correção de problemas de execução relacionados a Java 25 e Swing/AWT
- Inclusão de troubleshooting para `alternatives` no Fedora
- Correção de falhas de execução em ambiente gráfico mal configurado

### Known Issues
- Não funciona em ambientes headless (SSH sem X11 forwarding / TTY)
- Pode exigir ajuste manual de Java padrão via `alternatives`
- Compatibilidade depende do ambiente gráfico ativo

### Notes
- Este projeto não automatiza instalação
- Foco em documentação técnica confiável e reprodutível
