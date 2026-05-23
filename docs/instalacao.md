# Instalação do brModelo no Linux

Guia de instalação manual do **brModelo** em distribuições Linux, com integração ao menu de aplicativos.

## Ambiente validado

Testado e validado em:

- Fedora 42 Workstation (GNOME / Wayland)
- Debian 13

---

## Pré-requisito: Java com suporte gráfico

O **brModelo** é uma aplicação Java desktop e requer suporte gráfico (GUI).

### Fedora

Instale o OpenJDK:

```bash
sudo dnf install java-21-openjdk
```

### Ubuntu e derivados

```bash
sudo apt install default-jre
```

---

## 1. Baixar o executável

```bash
curl -fLO https://www.sis4.com/brModelo/brModelo.jar
```

---

## 2. Criar diretório da aplicação

```bash
mkdir -p "$HOME/.brModelo" \
&& mv brModelo.jar "$HOME/.brModelo/"
```

---

## 3. Testar execução do brModelo

Antes de continuar, valide se o aplicativo abre corretamente:

```bash
java -jar "$HOME/.brModelo/brModelo.jar"
```

Se abrir normalmente:

```text
OK → continuar
```

---

## 4. Baixar ícone

```bash
curl -fL \
-o "$HOME/.brModelo/brModelo.png" \
https://raw.githubusercontent.com/chcandido/brModelo/master/src/imagens/logico.png
```

---

## 5. Criar launcher no menu de aplicativos

Criar diretório:

```bash
mkdir -p "$HOME/.local/share/applications"
```

Criar launcher:

```bash
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

Tornar executável:

```bash
chmod +x "$HOME/.local/share/applications/brModelo.desktop"
```

---

## 6. Validar launcher

Teste via terminal:

```bash
gtk-launch brModelo
```

Se abrir corretamente:

```text
OK → integração concluída
```

Depois pesquise por **brModelo** no menu de aplicativos do sistema.

---

## Troubleshooting

### `HeadlessException`

Se ocorrer erro semelhante a:

```text
No X11 DISPLAY variable was set,
or no headful library support was found
```

Verifique se o Java desktop está instalado.

No Fedora:

```bash
dnf list --installed | grep openjdk
```

Esperado:

```text
java-21-openjdk
java-21-openjdk-headless
```

Se necessário:

```bash
sudo dnf install java-21-openjdk
```

Também confirme se o comando está sendo executado dentro de uma sessão gráfica Linux (GNOME/KDE/XFCE) e não em:

- TTY
- SSH sem forwarding gráfico
- terminal sem `DISPLAY`

Validação:

```bash
echo $DISPLAY
echo $XDG_SESSION_TYPE
```

Exemplo esperado:

```text
:0
wayland
```

---

## Resultado esperado

Após concluir a instalação:

- brModelo disponível no menu de aplicativos
- execução via:

```bash
gtk-launch brModelo
```

- launcher persistente no ambiente desktop