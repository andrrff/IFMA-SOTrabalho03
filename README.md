# Divisão de Trabalho: Gerenciamento de Memória

**Instruções Gerais para o Grupo:**
*   Cada aluno deve preparar sua parte para durar aproximadamente o mesmo tempo (ex: 8-10 minutos por aluno, dependendo do tempo total da apresentação).
*   Mantenham uma coesão entre as partes, fazendo referências ao que já foi dito e preparando o terreno para o próximo colega.
*   Utilizem os diagramas (Figuras) do material, pois são muito elucidativos.
*   Ao final, reservem um tempo para uma conclusão geral do grupo, resumindo os principais aprendizados.

---

**Divisão dos Tópicos por Aluno:**

**Aluno 1: Introdução e Gerenciamento de Memória Sem Abstração**
*   **Tópicos:**
    *   A importância do gerenciamento de memória (RAM como recurso crítico).
    *   Lei de Parkinson para programas.
    *   O desejo do programador: memória ideal (grande, rápida, não volátil, barata).
    *   Conceito de Hierarquia de Memórias (cache, RAM, disco).
    *   Função do Gerenciador de Memória.
    *   **3.1 Sem abstração de memória:** (pp. 125-127)
        *   Primeiros computadores: programa via memória física diretamente.
        *   Organização da memória: SO na parte inferior/superior, ROM, BIOS (Figura 3.1).
        *   Problemas: impossibilidade de múltiplos programas, falta de proteção.
        *   Solução parcial com hardware (IBM 360, chaves de proteção).
        *   Problema da realocação (Figura 3.2) e realocação estática (limitações).
*   **Ênfase:**
    *   Justificar a necessidade do gerenciamento de memória.
    *   Explicar os desafios e limitações dos primeiros sistemas sem abstração de memória.
    *   Destacar o problema da realocação como um motivador para soluções mais avançadas.

**Aluno 2: Espaços de Endereçamento e Swapping**
*   **Tópicos:**
    *   **3.2 Uma abstração de memória: espaços de endereçamento:** (pp. 128-129)
        *   A noção de espaço de endereçamento (proteção e realocação).
        *   Exemplos de espaços de endereçamento (números de telefone, IPv4).
        *   Registradores base e limite: como funcionam para prover espaços privados e realocação dinâmica (Figura 3.3).
    *   **3.2.2 Troca de processos (Swapping):** (pp. 130-131)
        *   Motivação: demanda total de memória > RAM disponível.
        *   Funcionamento do swapping (Figura 3.4).
        *   Compactação de memória: o que é e por que geralmente não é feita.
        *   Alocação de memória para processos em crescimento (Figura 3.5).
*   **Ênfase:**
    *   O conceito de espaço de endereçamento como a primeira grande abstração.
    *   Como registradores base/limite implementam essa abstração de forma simples.
    *   O swapping como mecanismo para lidar com a sobrecarga de memória, seus benefícios e custos.

**Aluno 3: Gerenciamento de Memória Livre e Introdução à Memória Virtual**
*   **Tópicos:**
    *   **3.2.3 Gerenciando a memória livre:** (pp. 131-133)
        *   Mapas de bits (vantagens e desvantagens, Figura 3.6a,b).
        *   Listas encadeadas (ordenação, fusão de blocos, Figura 3.6c, Figura 3.7).
        *   Algoritmos de alocação:
            *   First fit, Next fit.
            *   Best fit, Worst fit.
            *   Quick fit.
    *   **3.3 Memória Virtual - Introdução:** (p. 134)
        *   Problema do "bloatware" e necessidade de executar programas maiores que a RAM.
        *   Solução antiga: Sobreposições (overlays) e suas desvantagens.
        *   A ideia básica da memória virtual: permitir execução parcial de programas na memória.
*   **Ênfase:**
    *   Comparar os métodos de gerenciamento de memória livre (mapas de bits vs. listas).
    *   Explicar e comparar os diferentes algoritmos de alocação de memória livre.
    *   Introduzir o conceito de memória virtual como uma evolução do swapping e overlays.

**Aluno 4: Paginação – Conceitos Fundamentais e Tabelas de Página**
*   **Tópicos:**
    *   **3.3.1 Paginação:** (pp. 134-136)
        *   Endereços virtuais e a Unidade de Gerenciamento de Memória (MMU) (Figura 3.8).
        *   Páginas (virtuais) e Quadros de página (físicos).
        *   Mapeamento de endereços virtuais para físicos (exemplo da Figura 3.9).
        *   Falta de Página (Page Fault) e o bit Presente/Ausente.
    *   **3.3.2 Tabelas de Páginas:** (pp. 136-138)
        *   Estrutura do endereço virtual: Número da Página Virtual + Deslocamento (Figura 3.10).
        *   A Tabela de Páginas como função de mapeamento.
        *   Estrutura de uma Entrada da Tabela de Páginas (Figura 3.11):
            *   Número do quadro de página.
            *   Bit Presente/Ausente.
            *   Bits de Proteção (leitura/escrita/execução).
            *   Bits Modificada (sujo) e Referenciada.
            *   Bit de desabilitação de cache.
*   **Ênfase:**
    *   O mecanismo central da paginação: como a MMU traduz endereços.
    *   A importância da Tabela de Páginas e o significado de cada campo em uma entrada.
    *   O que é uma falta de página e como o bit Presente/Ausente é crucial.

**Aluno 5: Acelerando a Paginação e Lidando com Memórias Grandes**
*   **Tópicos:**
    *   **3.3.3 Acelerando a paginação:** (pp. 138-140)
        *   Problemas de desempenho da paginação (acessos à memória para a tabela).
        *   TLB (Translation Lookaside Buffers) / Memória Associativa (Figura 3.12).
        *   Funcionamento da TLB: hit e miss.
        *   Gerenciamento da TLB por software (soft miss, hard miss, page table walk).
    *   **3.3.4 Tabelas de páginas para memórias grandes:** (pp. 141-143)
        *   Problema do tamanho excessivo das tabelas de página.
        *   Tabelas de páginas multinível (conceito e exemplo da Figura 3.13).
        *   Tabelas de páginas invertidas (conceito e Figura 3.14).
*   **Ênfase:**
    *   A importância da TLB para o desempenho da paginação e como ela funciona.
    *   Como as tabelas de página multinível e invertidas abordam o problema do tamanho das tabelas em sistemas com grandes espaços de endereçamento virtual.

**Aluno 6: Algoritmos de Substituição de Página**
*   **Tópicos:**
    *   **3.4 Algoritmos de substituição de páginas:** (pp. 144-152)
        *   O problema: quando ocorre uma falta de página e não há quadros livres.
        *   Algoritmo Ótimo (teórico, base de comparação).
        *   Algoritmo NRU (Não Usadas Recentemente) - classes de páginas.
        *   Algoritmo FIFO (Primeiro a Entrar, Primeiro a Sair).
        *   Algoritmo Segunda Chance (modificação do FIFO, Figura 3.15).
        *   Algoritmo do Relógio (implementação eficiente da Segunda Chance, Figura 3.16).
        *   Algoritmo LRU (Menos Recentemente Usada) – ideal, mas difícil de implementar.
        *   Simulação de LRU: NFU (Não Frequentemente Usada) e Envelhecimento (Aging) (Figura 3.17).
        *   Algoritmo do Conjunto de Trabalho (Working Set) (Figuras 3.18, 3.19).
        *   Algoritmo WSClock (Figura 3.20).
    *   Resumo dos algoritmos de substituição de página (Figura 3.21).
*   **Ênfase:**
    *   Explicar a necessidade de algoritmos de substituição.
    *   Detalhar o funcionamento, vantagens e desvantagens dos principais algoritmos (especialmente Relógio, Envelhecimento e WSClock, que são práticos).
    *   Utilizar as figuras para ilustrar os algoritmos.

**Aluno 7: Questões de Projeto, Implementação e Segmentação**
*   **Tópicos:**
    *   **3.5 Questões de projeto para sistemas de paginação:** (pp. 153-160)
        *   Políticas de alocação local vs. global (Figura 3.22).
        *   Controle de carga e PFF (Page Fault Frequency) (Figura 3.23).
        *   Tamanho de página (trade-offs: fragmentação interna vs. tamanho da tabela/overhead de E/S).
        *   Páginas compartilhadas (Figura 3.25) e Bibliotecas Compartilhadas (Figura 3.26).
        *   Arquivos Mapeados em Memória.
        *   Política de Limpeza (daemon de paginação).
    *   **3.6 Questões de Implementação (Visão geral):** (pp. 161-165)
        *   Envolvimento do SO com a paginação (criação, execução, falta, término).
        *   Tratamento de Falta de Página (passos gerais).
        *   Backup de Instrução (Figura 3.27).
        *   Armazenamento de Apoio (Backing Store) (Figura 3.28).
        *   Separação Política vs. Mecanismo (Figura 3.29).
    *   **3.7 Segmentação (Visão geral):** (pp. 166-168)
        *   Conceito de segmentação, vantagens (Figura 3.30, 3.31).
        *   Comparação com paginação (Figura 3.32).
        *   Implementação pura e fragmentação externa (Figura 3.33).
    *   **Segmentação com Paginação (MULTICS e Intel x86 - brevemente, focando no conceito):** (pp. 168-173, Figuras 3.34-3.41).
    *   **3.8 Pesquisa em gerenciamento de memória e 3.9 Resumo (breve conclusão):** (pp. 174-175).
*   **Ênfase:**
    *   As decisões de projeto que impactam o desempenho e a eficiência dos sistemas de paginação.
    *   Os aspectos práticos da implementação do gerenciamento de memória.
    *   O conceito de segmentação como uma alternativa/complemento à paginação e como a combinação das duas (ex: MULTICS) tenta obter o melhor de ambos.

---

Esta divisão tenta equilibrar a quantidade de conteúdo e a complexidade. É importante que os alunos se comuniquem para garantir que a apresentação flua bem. Boa sorte com o trabalho!

---

**Planilha de Divisão de Tópicos: Gerenciamento de Memória (Capítulo 3)**

                                                                                                                         
| Aluno | Nome do Aluno | Tópico Principal                                        | Subtópicos / Conteúdo Detalhado (Principais Seções do Livro)                                                                                                                                                                                                                                                                                                      | Páginas de Referência | Figuras Chave (Exemplos) | Pontos de Ênfase / Dicas                                                                                                                                |
| :---- | :------------ | :------------------------------------------------------ | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :-------------------- | :----------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **1** | Savyo | **Introdução e Gerenciamento de Memória Sem Abstração** | - Importância do gerenc. de memória, Lei de Parkinson, Desejo do programador, Hierarquia de Memórias, Função do Gerenc. de Memória.<br>- **3.1 Sem abstração de memória:** Primeiros computadores, Organização da memória (SO, ROM, BIOS), Problemas (múltiplos programas, falta de proteção), Solução parcial com hardware (IBM 360), Problema da realocação, Realocação estática. | 125-127               | 3.1, 3.2                 | Justificar a necessidade do gerenc. de memória. Explicar desafios e limitações dos primeiros sistemas. Destacar problema da realocação.                    |
| **2** | André | **Espaços de Endereçamento e Swapping**                 | - **3.2 Uma abstração de memória: espaços de endereçamento:** Noção (proteção e realocação), Exemplos, Registradores base e limite (realocação dinâmica).<br>- **3.2.2 Troca de processos (Swapping):** Motivação, Funcionamento, Compactação de memória, Alocação para processos em crescimento.                                                                                    | 128-131               | 3.3, 3.4, 3.5            | O conceito de espaço de endereçamento como abstração. Como registradores base/limite funcionam. Swapping: o que é, benefícios e custos.                   |
| **3** | a definir... | **Gerenciamento de Memória Livre e Introdução à Memória Virtual** | - **3.2.3 Gerenciando a memória livre:** Mapas de bits, Listas encadeadas (fusão de blocos), Algoritmos de alocação (First fit, Next fit, Best fit, Worst fit, Quick fit).<br>- **3.3 Memória Virtual - Introdução:** Problema do "bloatware", Sobreposições (overlays), Ideia básica da memória virtual.                                                                           | 131-134               | 3.6, 3.7                 | Comparar métodos de gerenc. de memória livre. Explicar e comparar algoritmos de alocação. Introduzir memória virtual como evolução.                      |
| **4** | Hiago | **Paginação: Conceitos Fundamentais e Tabelas de Página** | - **3.3.1 Paginação:** Endereços virtuais e MMU, Páginas e Quadros de página, Mapeamento de endereços, Falta de Página (Page Fault) e bit Presente/Ausente.<br>- **3.3.2 Tabelas de Páginas:** Estrutura do endereço virtual (Número da Página + Deslocamento), Tabela de Páginas como função, Estrutura de uma Entrada (Número do quadro, P/A, Proteção, Modif./Ref., Desab. cache).     | 134-138               | 3.8, 3.9, 3.10, 3.11     | Mecanismo central da paginação (MMU). Importância da Tabela de Páginas e seus campos. O que é uma falta de página.                                      |
| **5** | a definir... | **Acelerando a Paginação e Tabelas para Memórias Grandes** | - **3.3.3 Acelerando a paginação:** TLB (Translation Lookaside Buffers) / Memória Associativa, Funcionamento da TLB (hit e miss), Gerenciamento da TLB por software (soft/hard miss, page table walk).<br>- **3.3.4 Tabelas de páginas para memórias grandes:** Tabelas de páginas multinível, Tabelas de páginas invertidas.                                                              | 138-143               | 3.12, 3.13, 3.14         | Importância da TLB para o desempenho. Como tabelas multinível e invertidas resolvem o problema de tabelas grandes.                                       |
| **6** | a definir... | **Algoritmos de Substituição de Página**                | - **3.4 Algoritmos de substituição de páginas:** Problema, Algoritmo Ótimo, NRU, FIFO, Segunda Chance, Relógio, LRU, Simulação de LRU (NFU, Envelhecimento/Aging), Conjunto de Trabalho (Working Set), WSClock.<br>- **Resumo dos algoritmos de substituição de página (Figura 3.21).**                                                                                             | 144-153               | 3.15-3.21                | Explicar a necessidade dos algoritmos. Detalhar o funcionamento, vantagens e desvantagens dos principais algoritmos práticos (Relógio, Aging, WSClock). |
| **7** | a definir... | **Questões de Projeto, Implementação e Segmentação**    | - **3.5 Questões de projeto:** Alocação local vs. global, Controle de carga (PFF), Tamanho de página, Páginas/Bibliotecas compartilhadas, Arquivos Mapeados, Política de Limpeza.<br>- **3.6 Questões de Implementação (Visão geral):** Envolvimento do SO, Tratamento de Falta de Página, Backup de Instrução, Armazenamento de Apoio, Separação Política/Mecanismo.<br>- **3.7 Segmentação (Visão geral):** Conceito, Vantagens, Comparação com paginação, Implementação pura e fragmentação externa.<br>- **Segmentação com Paginação (MULTICS e Intel x86 - *brevemente, focar no conceito*).** <br>- **3.8 Pesquisa e 3.9 Resumo (breve conclusão do capítulo).** | 153-175               | 3.22, 3.23, 3.25-3.33 (e menção a 3.34-3.41 se for falar de Multics/x86) | Decisões de projeto que impactam o desempenho. Aspectos práticos da implementação. Conceito de segmentação como alternativa/complemento à paginação.    |

---

Esta estrutura deve ajudar o grupo a se organizar e apresentar o conteúdo de forma equilibrada.