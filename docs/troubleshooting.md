# Troubleshooting

Guia rápido para resolução de problemas comuns durante a instalação e execução do **brModelo** no Linux.

---

# 1. Aplicação não abre

Teste execução direta:

```bash
java -jar ~/.brModelo/brModelo.jar
```

Se abrir pelo terminal, mas não pelo menu do sistema, revise o launcher `.desktop`.

---

# 2. Erro: HeadlessException

Exemplo:

```text
java.awt.HeadlessException:
No X11 DISPLAY variable was set
```

## Causa

O brModelo é uma aplicação gráfica Java (Swing/AWT) e requer sessão gráfica ativa.

O erro normalmente ocorre quando:

* terminal TTY (sem GUI)
* SSH sem X11 forwarding
* ambiente headless
* sessão gráfica não iniciada

## Diagnóstico

Verifique:

```bash
echo $DISPLAY
echo $XDG_SESSION_TYPE
```

Resultado esperado:

```text
DISPLAY=:0
XDG_SESSION_TYPE=wayland
```

ou

```text
DISPLAY=:0
XDG_SESSION_TYPE=x11
```

---

# 3. Java instalado, mas aplicação continua falhando

Verifique a versão ativa:

```bash
java --version
```

Recomendado:

```text
Java 21
```

Se houver múltiplas versões instaladas:

### Fedora

```bash
sudo alternatives --config java
```

### Debian / Ubuntu

```bash
sudo update-alternatives --config java
```

Selecione:

```text
java-21-openjdk
```

---

# 4. Fedora usando Java diferente do validado

Problema observado:

```text
java-25-openjdk ativo
java-21-openjdk instalado
```

Nesse cenário, o sistema pode continuar executando uma versão não validada ou potencialmente incompatível.

Confirme:

```bash
which java
readlink -f $(which java)
```

Resultado esperado:

```text
/usr/lib/jvm/java-21-openjdk/bin/java
```

---

# 5. Erro relacionado a libawt_xawt.so

Exemplo:

```text
UnsatisfiedLinkError:
Can't load library: libawt_xawt.so
```

## Solução

Reinstalar Java 21.

### Fedora

```bash
sudo dnf reinstall java-21-openjdk
```

### Debian / Ubuntu

```bash
sudo apt reinstall openjdk-21-jre
```

Depois valide:

```bash
java --version
```

---

# 6. Launcher (.desktop) não aparece no menu

Atualize a base local:

```bash
update-desktop-database ~/.local/share/applications
```

Ou encerre sessão e faça login novamente.

Teste:

```bash
gtk-launch brModelo
```

---

# 7. Verificação rápida do ambiente

Comandos úteis:

```bash
java --version
echo $DISPLAY
echo $XDG_SESSION_TYPE
which java
readlink -f $(which java)
```

Exemplo esperado:

```text
openjdk 21.x
DISPLAY=:0
XDG_SESSION_TYPE=wayland
/usr/lib/jvm/java-21-openjdk/bin/java
```

---

# 8. Limitações conhecidas

O brModelo:

* requer ambiente gráfico ativo
* não funciona em TTY puro
* não funciona em ambiente headless
* pode exigir ajuste manual da versão ativa do Java
