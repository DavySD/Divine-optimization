# Divine-optimization
Uma documentação e guia de vastas formas nefastas de otimizar um sistema operacional.
---

<details>
<summary><strong>Índice</strong></summary>

- [Início](#início)
- [Sistema Operacional](#sistema-operacional)
	- [Por que não o Windows](#por-que-não-o-windows)
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