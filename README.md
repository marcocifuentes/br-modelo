# brModelo Linux Installer

Guia de instalação manual do **brModelo** para Linux, incluindo integração com menu de aplicativos (`.desktop`) e opção de atalho na área de trabalho.

Este repositório documenta um procedimento simples, reproduzível e validado para executar o **brModelo** em distribuições Linux modernas.

---

## 📌 O que este repositório resolve

O **brModelo** é distribuído como um arquivo `.jar` Java e não possui instalador nativo para Linux.

Este guia ajuda a:

- baixar e organizar o executável
- integrar o aplicativo ao menu do sistema
- criar um atalho opcional na área de trabalho
- manter uma instalação simples e reproduzível

---

## 🖥️ Distribuições testadas

Validado em:

- Ubuntu e derivados
- Fedora e derivados

Outras distribuições Linux podem funcionar, desde que possuam:

- Java instalado
- suporte a arquivos `.desktop`

---

## 📋 Pré-requisito

Verifique se o Java está instalado:

```bash
java --version
```

Se o comando falhar, instale uma versão do Java (JRE/JDK) pela sua distribuição antes de continuar.

---

## 🚀 Instalação

Siga o procedimento completo documentado em:

```text
docs/instalacao.md
```

---

## 🧪 Resultado esperado

Após concluir a instalação:

- brModelo disponível no menu de aplicativos
- execução sem terminal
- atalho opcional na área de trabalho

---

## ⚠️ Escopo do projeto

Este repositório:

- não instala Java automaticamente
- não gera pacotes `.deb`, `.rpm` ou Flatpak
- não altera configurações do sistema fora do ambiente do usuário

O objetivo é manter uma instalação simples, transparente e reproduzível.

---

## 🔗 Referências

Projeto oficial:

https://www.sis4.com/brModelo/

Código-fonte / referência comunitária:

https://github.com/chcandido/brModelo