# Divine-optimization
Uma documentação e guia de vastas formas nefastas de otimizar um sistema operacional.
---

<details>
<summary><strong>Índice</strong></summary>

- [Início](#início)
- [Sistema Operacional](#sistema-operacional)
	- [Por que não o Windows](#por-que-não-o-windows)
	- [Interfaces](#interfaces-de-wm--wc)
		- [X11 & Wayland](#protocolos-de-servidor-gr%C3%A1fico-x11--wayland)
</details>

## Início 
* Esta documentação tem como intuito guiar maneiras de tirar mais proveito do hardware a partir do software.
* Essa documentação não faz milagres. Lembre-se: mesmo com o melhor modelo de otimização, o gargalo é o hardware, não o software.
* O nome do repositório é inspirado no livro [*Divina Comédia*](https://pt.wikipedia.org/wiki/Divina_Com%C3%A9dia). Não porque esse guia é engraçado, pois você descerá aos infernos aqui.
* Este guia está em constante evolução e sujeito a alterações.

> [!TIP]
> Eu, Deive, [tenho um servidor no Discord](https://disboard.org/pt-br/server/1371434807988588636) no qual você pode pedir uma luz.

## Sistema Operacional

### Por que não o Windows
* Prepare seu coração. Essa documentação é pensada para sistemas Unix (aka Linux), esqueça o Windows.
* Windows é muito limitado quanto a modificações realmente relevantes.
* Acredite, o foco aqui não é desativar animações em uma interface ou adicionar mais swap. Aqui vamos mexer com conceitos como governadores de CPU; kernel; compilação; swap, zram, zswap; cache e mais.
* "Qual distribuição Linux eu escolho?" - Isso depende muito. Tem vários guias na internet, mas no geral escolha algo como [*Mint*](https://www.linuxmint.com/). Se seu computador rodar KDE, use [*Fedora "KDE"*](https://kde.fedoraproject.org/) *(abordaremos interfaces em seguida)*, [*CachyOS*](https://cachyos.org/) ou tanto faz. **Aqui o que eu abordar funciona para 98% das distros.**

> [!NOTE]
> Mais pra frente eu vou abordar sobre uma distro avançada chamada Gentoo. Em hipótese alguma eu a recomendo para um iniciante, ok?

### Interfaces (DE, WM & WC)
* O que é uma DE?
  * Um **D**esktop **E**nvironment é um ecossistema de ambiente desktop, contendo: Um gerenciador de janelas (WM) e aplicações próprias (seja uma taskbar ou um editor de texto)
* O que é um WM?
  * Um **W**indow **M**anager gerencia a criação, manipulação, destruição e decorações de janelas na tela do X11.
* O que é um WC?
  * Um **W**ayland **C**ompositor é o equivalente a um WM para Wayland.
> [!NOTE]
> **DEs**: *KDE Plasma; Gnome; Xfce; Cinnamon; Mate etc.*
>
> **WMs**: *I3wm; Openbox; Bspwm; DWM; Awesomewm; Kwin (Plasma X11); Mutter (Gnome X11); Xfwm (Xfce X11) etc.*
>
> **WCs**: *Hyprland; Wayfire; River; Niri; Mango; Labwc (Openbox-like); Sway (I3wm-like) etc.*

#### Protocolos de servidor gráfico (X11 & Wayland)
* O que é um protocolo de servidor gráfico?
  * Um [protocolo de servidor gráfico](https://pt.wikipedia.org/wiki/Sistema_de_janelas) é um componente de uma [interface gráfica](https://pt.wikipedia.org/wiki/Interface_gr%C3%A1fica_de_usu%C3%A1rio) que fornece suporte à implementação de [gerenciadores de janelas](#interfaces-de-wm--wc), e fornece suporte básico para o hardware gráfico, dispositivos apontadores, como mouses, e teclados.
* O que é o X11?
  * O [X](https://pt.wikipedia.org/wiki/X_Window_System)11 é um software de sistema e um [protocolo](https://pt.wikipedia.org/wiki/Sistema_de_janelas) que fornece uma base para [interfaces gráficas](interfaces-de--wm--wc) e funcionalidade rica de dispositivos de entrada para redes de computadores. Ele cria uma camada de abstração de hardware onde o software é escrito para usar um conjunto generalizado de comandos, permitindo a independência de dispositivo e reutilização de programas em qualquer computador que implemente o X.
* O que é o Wayland?
  * O [Wayland](https://pt.wikipedia.org/wiki/Wayland_(protocolo_de_servidor_gr%C3%A1fico)) é um [protocolo de servidor gráfico](#protocolos-de-servidor-gr%C3%A1fico-x11--wayland) moderno que visa substituir o [X](https://pt.wikipedia.org/wiki/X_Window_System)11. Ele foi projetado para ser mais simples, seguro e eficiente, eliminando muitas das complexidades herdadas do X. No Wayland, o compositor gerencia tudo diretamente (janelas, renderização, entrada), resultando em menos latência e melhor desempenho gráfico.
 

# Fontes
<!-- Essa categoria é sempre no final, são os créditos. -->
- [Wikipedia](https://pt.wikipedia.org/)
- [Gentoo Wiki](https://wiki.gentoo.org/wiki/Main_Page)
