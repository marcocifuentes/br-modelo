# brModelo Linux Installer

Guia manual de instalação do **brModelo** no Linux com integração ao menu de aplicativos.

---

# 1. Pré-requisitos

Antes de iniciar a instalação, o sistema deve possuir:

## Fedora / Debian / Ubuntu

- Java 21 (recomendado)
- curl
- ambiente gráfico Linux ativo (GNOME/KDE/XFCE)
- suporte a XDG Desktop Entry (.desktop)

---

# ⚠️ Importante (execução)

O brModelo é uma aplicação gráfica Java (Swing/AWT).

Ele NÃO funciona em:

- SSH sem X11 forwarding
- TTY (terminal sem interface gráfica)
- ambientes headless

Requer:

- sessão gráfica ativa
- variável `DISPLAY` configurada

---

# 2. Instalação

## 2.1 Instalar dependências

### Fedora

```bash
sudo dnf install curl java-21-openjdk -y
```

### Debian / Ubuntu

```bash
sudo apt update
sudo apt install curl openjdk-21-jre -y
```

---

## 2.2 Verificar Java ativo (obrigatório)

Antes de continuar:

```bash
java --version
```

Se houver múltiplas versões instaladas:

```bash
sudo alternatives --config java
```

Selecione **Java 21**.

---

## 2.3 Baixar o brModelo

```bash
mkdir -p "$HOME/.brModelo"

curl -fL -o "$HOME/.brModelo/brModelo.jar" \
https://www.sis4.com/brModelo/brModelo.jar
```

---

## 2.4 Adicionar ícone

```bash
curl -fL -o "$HOME/.brModelo/brModelo.png" \
https://raw.githubusercontent.com/chcandido/brModelo/master/src/imagens/logico.png
```

---

## 2.5 (Opcional) Teste de execução direta

Antes de criar atalhos:

```bash
java -jar "$HOME/.brModelo/brModelo.jar"
```

---

## 2.6 Criar launcher do sistema

```bash
mkdir -p "$HOME/.local/share/applications"

cat > "$HOME/.local/share/applications/brModelo.desktop" <<EOF
[Desktop Entry]
Version=1.0
Name=brModelo
Comment=Ferramenta para MER
Exec=java -jar $HOME/.brModelo/brModelo.jar
Icon=$HOME/.brModelo/brModelo.png
Path=$HOME/.brModelo
Type=Application
Terminal=false
StartupNotify=true
Categories=Development;Education;
EOF
```

---

## 2.7 Tornar o launcher executável

```bash
chmod +x "$HOME/.local/share/applications/brModelo.desktop"
```

---

## 2.8 Atualizar base de aplicativos (se necessário)

```bash
update-desktop-database ~/.local/share/applications
```

---

## 2.9 Executar

Via menu do sistema:

```text
brModelo
```

Ou via terminal:

```bash
java -jar ~/.brModelo/brModelo.jar
```

---

# 3. Ambiente testado

Este procedimento foi validado em:

- Fedora 42 / 43 Workstation (GNOME / Wayland)
- Debian 13 (GNOME)
- Ubuntu 26.04 LTS (GNOME)

---

# 4. Observações importantes

- Instalação manual (sem script automatizado)
- Não utiliza Docker ou empacotamento Flatpak/Snap
- Depende de Java 21 configurado como padrão ativo
- Requer ambiente gráfico funcional

---

# 5. Escopo

Este projeto é um instalador manual baseado em documentação.

Não garante compatibilidade universal entre distribuições Linux, pois depende de:

- versão ativa do Java (não apenas instalado)
- ambiente gráfico (GNOME/KDE/XFCE)
- configuração correta de `alternatives`
- ferramentas básicas do sistema

---

# 6. Fonte

- http://www.sis4.com/brModelo/index.html  
- https://github.com/chcandido/brModelo  
```