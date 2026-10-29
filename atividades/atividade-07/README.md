# Atividade 07 - Execução do Algoritmo do Banqueiro

**Aluno(a):** Caio Macilon Lima Carnerio

Este documento contém a explicação dos testes propostos para o Algoritmo do Banqueiro e detalha a saída gerada pelo simulador. Os prints da execução estão anexados nesta mesma pasta.

## 1. Explicando os Testes e as Saídas Geradas

### Verificação do Estado Inicial
* **O que foi testado:** O sistema valida a matriz de alocação inicial calculando a matriz de "Necessidade" e cruzando com os recursos disponíveis para garantir que não há deadlock.
* **Saída gerada:** O algoritmo determina que o estado atual é **SEGURO**. Ele encontra uma sequência (P1 -> P3 -> P4 -> P0 -> P2) onde todos os processos conseguem ser atendidos com os recursos atuais `[3, 3, 2]`.

### Teste de Caso 1: Requisição de P1 `[1, 0, 2]`
* **O que foi testado:** O processo P1 solicita 1 unidade de R0 e 2 de R2. O sistema verifica se a requisição está dentro do limite máximo do processo e se há recursos disponíveis.
* **Saída gerada:** A requisição é **CONCEDIDA**. Como a requisição é menor que a necessidade máxima e menor que os recursos disponíveis, o sistema faz uma alocação provisória. A simulação encontra uma nova sequência segura e efetiva a alocação.

### Teste de Caso 2: Requisição de P4 `[3, 3, 0]`
* **O que foi testado:** O processo P4 solicita 3 unidades de R0 e 3 de R1 após a alocação de P1 ter ocorrido.
* **Saída gerada:** A requisição é **NEGADA** (processo bloqueado). A saída acusa que os recursos são insuficientes no momento: P4 pede 3 unidades de R0, mas o sistema só possui 2 unidades disponíveis (pois P1 já consumiu recursos no teste anterior). O processo deve aguardar.

