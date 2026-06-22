# 🔧 Otimizações

> [← Voltar ao índice](../README.md)

Daqui em diante, as otimizações de fato — das mais simples às mais complexas.

> [!NOTE]
> Nem toda forma de otimização é definitiva. No caso de interfaces, a lógica do que é "pesado" é explicada, e as otimizações das mais famosas são abordadas. Aprenda o princípio para aplicar onde for.

---

## Subseções

| Seção | Conteúdo |
|-------|----------|
| [🖥️ Hardware](./hardware/README.md) | Aceleração de hardware (VAAPI, VDPAU, NVIDIA) |
| [🪟 Desktop](./desktop/README.md) | Otimizações por DE (KDE Plasma, Gnome, Xfce) |

---

## O que deixa as interfaces pesadas?

<details>
<summary><strong>1. Efeitos visuais (composições)</strong></summary>

- **Blur (desfoque):** O efeito mais pesado. Requer renderização em tempo real de cada pixel atrás das janelas. → *Impacto: muito pesado*
- **Sombras:** Menos pesado que blur, mas ainda consome ciclos de GPU/CPU. → *Impacto: pesado a médio*
- **Animações:** Fade in/out (baixo), slide (baixo), magic lamp (alto), wobbly windows (alto)
- **Transparência:** Requer composição de múltiplas camadas. → *Impacto: baixo*

</details>

<details>
<summary><strong>2. Serviços em segundo plano</strong></summary>

- **Indexadores:** Baloo (KDE), Tracker (Gnome) — vasculham arquivos constantemente para busca rápida.
- **Polkit Agents:** Alguns são mais pesados que outros.

> *Baloo* sozinho pode consumir **100–500 MB** de RAM + I/O constante no disco.

</details>

<details>
<summary><strong>3. Addons e extensões</strong></summary>

- **Plasma Widgets:** Os oficiais são leves, mas widgets da comunidade podem consumir recursos e tornar o desktop instável.
- **Gnome Extensions:** Executam em JavaScript, overhead considerável. Algumas mal escritas vazam memória.

</details>

<details>
<summary><strong>4. Temas e ícones</strong></summary>

- **Temas complexos:** Muitos elementos SVG, gradientes e sombras embutidas.
- **Icon packs gigantes:** Conjuntos com milhares de ícones em alta resolução.
- **Impacto:** Geralmente menor, mas temas mal otimizados adicionam latência perceptível.

</details>

<details>
<summary><strong>5. Aplicações do ecossistema da DE</strong></summary>

- Gerenciadores de arquivos pesados, lojas de aplicativos e editores de texto nativos podem ser substituídos por alternativas mais simples, ao custo da integração com a DE.

</details>
