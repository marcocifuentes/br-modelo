
## 🔧 Instalação via terminal(bash)
------------------------------------------------------------------------

## 1. Baixar o executável

``` bash
curl -OL http://www.sis4.com/brModelo/brModelo.jar
```

------------------------------------------------------------------------

## 2. Criar pasta oculta e mover arquivo

``` bash
mkdir -p $HOME/.brModelo & mv brModelo.jar $HOME/.brModelo
```

------------------------------------------------------------------------

## 3. Baixar ícone

``` bash
curl -L -o $HOME/.brModelo/brModelo.png https://github.com/chcandido/brModelo/raw/master/src/imagens/logico.png
```

------------------------------------------------------------------------

## 4. Criar atalho no menu

``` bash
echo -e "[Desktop Entry]\n\
Version=1.0\n\
Name=brModelo\n\
Exec=java -jar /home/${USER}/.brModelo/brModelo.jar\n\
Icon=/home/${USER}/.brModelo/brModelo.png\n\
Type=Application\n\
Comment=Ferramenta para MER\n\
Path=/home/${USER}/.brModelo\n\
Terminal=false\n\
StartupNotify=true\n\
Categories=Development;Education;" | tee $HOME/.local/share/applications/brModelo.desktop
```

Torne o atalho executável:

``` bash
chmod +x $HOME/.local/share/applications/brModelo.desktop
```

------------------------------------------------------------------------

## 5. Atalho na área de trabalho (opcional)

``` bash
cp $HOME/.local/share/applications/brModelo.desktop $HOME/Desktop/ & chmod +x $HOME/Desktop/brModelo.desktop
```

------------------------------------------------------------------------

## ✅ Fim

-   O **atalho estará disponível no menu de aplicativos**.
-   Se copiou para a área de trabalho, poderá abrir também por lá.
-   Agora você pode iniciar o **brModelo** sem precisar abrir o
    terminal.
