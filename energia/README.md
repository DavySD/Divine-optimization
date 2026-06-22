# ⚡ Energia

> [← Voltar ao índice](../README.md)

Esta seção aborda gestão de energia da CPU: governors, como funcionam e qual escolher.

---

## Índice

- [CPU Governors](#cpu-governors)
  - [O que são](#o-que-são)
  - [Listando governors disponíveis](#listando-governors-disponíveis)
  - [Governors e suas características](#governors-e-suas-características)

---

## CPU Governors

### O que são

Um **CPU governor** (ou escalonador de CPU) é um recurso do kernel usado para ajustar (dinamicamente ou não) a frequência da CPU com base na carga de trabalho, visando um equilíbrio entre desempenho e eficiência energética.

Toda CPU vem com governors disponíveis, mas não necessariamente os mesmos. Laptops costumam ter mais opções que desktops, por exemplo.

Os governors são essenciais no quesito de desempenho, pois ditam o esforço da máquina. Muitas distros (ex.: Debian) costumam vir com o `powersave` ativado por padrão, o que pode acarretar em desempenho inferior.

---

### Listando governors disponíveis

```bash
┌─ /home/deive
└─ η cat /sys/devices/system/cpu/cpu0/cpufreq/scaling_available_governors
performance schedutil ondemand powersave conservative
```

No exemplo acima, esses são os cinco governors disponíveis. Em computadores desktop, é provável que existam apenas `performance` e `powersave`.

---

### Governors e suas características

* **Performance**: Força a CPU a operar sempre na frequência de clock mais alta possível. Valor estático, não muda. Não oferece nenhum benefício de economia de energia. Pode acarretar em temperaturas elevadas e maior consumo energético geral. Ideal quando a máquina tem alimentação garantida e estará constantemente sob carga (em jogos ou serviços de renderização pesadas por exemplo.)

* **Ondemand**: Funciona dinamicamente, alcançando a frequência máxima sob alta carga e a mínima em idle. Ajusta o consumo conforme a demanda, ao custo de latência perceptível na transição entre frequências.

* **Conservative**: Similar ao `ondemand`, mas transita entre frequências de forma gradual em vez de saltar diretamente entre máximo e mínimo.

* **Schedutil**: Funciona dinamicamente com o mesmo objetivo do `ondemand`, porém integra-se diretamente ao escalonador do kernel Linux, entregando resultados superiores na maioria dos casos. A escolha moderna.

* **Powersave**: Oposto exato do `performance` — força a CPU a operar sempre na frequência mais baixa. Valor estático. Máxima economia de energia, mas sacrifica totalmente o desempenho.

---

> [!WARNING]
> Usar governors de alto desempenho pode ser prejudicial em casos de superaquecimento ou consumo energético excessivo.
> Sempre monitore as temperaturas do seu computador.
