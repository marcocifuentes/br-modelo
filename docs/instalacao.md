# 🔧 Instalação Manual do brModelo no Linux

Guia para instalação manual do **brModelo** em distribuições Linux, com integração ao menu de aplicativos e opção de atalho na área de trabalho.

---

## 📋 Pré-requisitos

Verifique se o Java está instalado:

```bash
java --version
```

Se o comando falhar, instale uma versão do Java (JRE/JDK) pela sua distribuição antes de continuar.

Exemplo:

### Ubuntu / Debian

```bash
sudo apt install default-jre
```

### Fedora

```bash
sudo dnf install java-latest-openjdk
```

---

## 1. Baixar o executável

Baixe o arquivo oficial do **brModelo**:

```bash
curl -fLO https://www.sis4.com/brModelo/brModelo.jar
```

---

## 2. Criar diretório da aplicação e mover arquivo

Crie o diretório oculto do brModelo e mova o executável:

```bash
mkdir -p "$HOME/.brModelo" \
&& mv brModelo.jar "$HOME/.brModelo/"
```

---

## 3. Baixar ícone da aplicação

Baixe o ícone utilizado no menu do sistema:

```bash
curl -fL \
-o "$HOME/.brModelo/brModelo.png" \
https://github.com/chcandido/brModelo/raw/master/src/imagens/logico.png
```

---

## 4. Criar atalho no menu de aplicativos

Crie o diretório local de aplicações (caso ainda não exista):

```bash
mkdir -p "$HOME/.local/share/applications"
```

Crie o arquivo `.desktop` para integração com o menu:

```bash
cat > "$HOME/.local/share/applications/brModelo.desktop" <<EOF
[Desktop Entry]
Version=1.0
Name=brModelo
Exec=java -jar $HOME/.brModelo/brModelo.jar
Icon=$HOME/.brModelo/brModelo.png
Type=Application
Comment=Ferramenta para modelagem entidade-relacionamento (MER)
Path=$HOME/.brModelo
Terminal=false
StartupNotify=true
Categories=Development;Education;
EOF
```

Torne o atalho executável:

```bash
chmod +x "$HOME/.local/share/applications/brModelo.desktop"
```

---

## 5. Criar atalho na área de trabalho (Opcional)

Copie o atalho para a área de trabalho do usuário:

```bash
cp "$HOME/.local/share/applications/brModelo.desktop" \
"$(xdg-user-dir DESKTOP)/" \
&& chmod +x "$(xdg-user-dir DESKTOP)/brModelo.desktop"
```

---

## ✅ Resultado esperado

Após concluir a instalação:

- O **brModelo** estará disponível no menu de aplicativos.
- Opcionalmente, haverá um atalho na área de trabalho.
- O programa poderá ser iniciado sem abrir terminal.

---

## 🧪 Distribuições testadas

- Ubuntu e derivados
- Fedora e derivados

---

## 🔗 Fontes e referências

Site oficial do brModelo:

https://www.sis4.com/brModelo/

Código-fonte / referência comunitária:

https://github.com/chcandido/brModelo