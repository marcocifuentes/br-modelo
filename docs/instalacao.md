# brModelo Linux Installer

Guia manual de instalação do **brModelo** no Linux com integração ao menu de aplicativos.

---

# 1. Pré-requisitos

Antes de iniciar a instalação, o sistema deve possuir:

## Fedora / Debian / Ubuntu

- Java 21 ou superior
- curl
- ambiente gráfico Linux com suporte a XDG Desktop Entry (.desktop)

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
sudo apt install curl default-jre -y
```

---

## 2.2 Baixar o brModelo

```bash
mkdir -p "$HOME/.brModelo"

curl -fL -o "$HOME/.brModelo/brModelo.jar" \
https://www.sis4.com/brModelo/brModelo.jar
```

---

## 2.3 Adicionar ícone

```bash
curl -fL -o "$HOME/.brModelo/brModelo.png" \
https://raw.githubusercontent.com/chcandido/brModelo/master/src/imagens/logico.png
```

---

## 2.4 Criar launcher do sistema

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

## 2.5 Tornar o launcher executável

```bash
chmod +x "$HOME/.local/share/applications/brModelo.desktop"
```

---

## 2.6 Atualizar base de aplicativos (se necessário)

```bash
update-desktop-database ~/.local/share/applications
```

---

## 2.7 Executar

```bash
gtk-launch brModelo
```

ou via terminal:

```bash
java -jar ~/.brModelo/brModelo.jar
```

---

# 3. Ambiente testado

Este procedimento foi validado em:

- Fedora 42 Workstation (GNOME / Wayland)
- Debian 13 (GNOME)
- Ubuntu 26.04 LTS (GNOME)

---

# 4. Observações importantes

- Este instalador não utiliza Docker ou automação
- Depende de Java 21+ instalado no sistema
- Requer ambiente gráfico Linux funcional
- Requer ferramentas básicas como curl

---

# 5. Escopo

Este projeto é um instalador manual baseado em documentação.

Ele não garante compatibilidade universal entre distribuições Linux, pois depende de:

- versão do Java
- ambiente gráfico (GNOME/KDE/XFCE)
- ferramentas básicas do sistema

---

# 6. Fonte

- http://www.sis4.com/brModelo/index.html  
- https://github.com/chcandido/brModelo  