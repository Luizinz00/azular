# GDD — Simulador de Conservação Patrimonial

## Diagnóstico Interativo

**Game Design Document**

### Equipe de Desenvolvimento

- Matheus Fernandes
- Bruno Borges
- Ana Vitória Maciel
- Alysson Rodrigues
- Luis Henrique Lindoso
- Rafael Santos

**Instituição:** UNDB  
**Disciplina:** Tecnologias Emergentes

---

## 01. Visão Geral do Jogo

| Campo | Informação |
|---|---|
| Gênero | Simulação Educacional / Puzzle — Tomada de Decisão |
| Plataforma | Realidade Virtual — Meta Quest / PC VR |
| Engine | Unity + XR Interaction Toolkit |
| Duração da Experiência | 3 a 5 minutos |

---

## 02. Objetivo do Jogo

Treinar o usuário na identificação e resolução de problemas de conservação patrimonial, por meio da escolha correta de ferramentas adequadas para cada situação.

### Foco Principal

- Aprendizado prático
- Tomada de decisão
- Associação problema → solução

---

## 03. Conceito Principal

O jogador é colocado em um ambiente controlado onde:

- Uma parede apresenta um problema.
- Ferramentas estão disponíveis à sua frente.
- Ele deve escolher a ferramenta correta para resolver o problema.

### Ciclo Central do Jogo

```txt
Identificar → Escolher → Testar → Aprender
```

---

## 04. Gameplay — Loop Principal

1. O jogador inicia no ambiente.
2. Observa a parede com o problema.
3. Opcionalmente, consulta o Diário de Campo.
4. Escolhe uma ferramenta.
5. Executa a ação.
6. O sistema verifica a resposta:
   - Correto → problema resolvido.
   - Incorreto → erro com feedback simples.
7. O próximo problema aparece.
8. O ciclo se repete até finalizar.
9. A tela final exibe o resultado.

---

## 05. Mecânicas Principais

### 5.1 Seleção de Ferramentas

- As ferramentas ficam dispostas na bancada.
- O jogador pega as ferramentas utilizando o controle VR.
- O jogador aponta ou clica para aplicar a ferramenta sobre o problema.

---

### 5.2 Sistema de Problemas

Cada rodada apresenta:

- Um problema visual na parede.
- Um conjunto de ferramentas possíveis.

### Exemplos de Problemas

- Umidade
- Mofo
- Cupim
- Rachaduras

---

### 5.3 Sistema de Resolução

| Ação | Resultado |
|---|---|
| Ferramenta correta | Problema resolvido + próximo cenário |
| Ferramenta errada | Feedback visual |

---

### 5.4 Sistema de Pontuação

O sistema registra:

- Número de acertos.
- Número de tentativas.
- Eficiência do jogador.

---

### 5.5 Diário de Campo

O Diário de Campo é um componente importante do jogo.

### Função

Servir como guia de aprendizado e apoiar o jogador na tomada de decisões.

### Conteúdo

- Descrição dos problemas.
- Ferramentas recomendadas para cada situação.

---

## 06. Sistema de Feedback — Chef

### Função do Chef

- Mostrar o resultado ao final da sessão.
- Dar feedback objetivo ao jogador.

### Exemplo de Feedback

```txt
Você acertou 5 de 10 problemas. Foram necessárias 12 tentativas.
```

---

## 07. Estrutura de Cena

O jogo opera em cena única ou em fluxo contínuo.

---

### 7.1 Ambiente

- Sala fechada, estilo “cubão”.
- Jogador posicionado no centro.
- Uma parede exibindo o problema atual.
- Bancada com ferramentas à frente do jogador.

---

### 7.2 Dinâmica

- O jogador resolve o problema.
- A parede “reseta”.
- Um novo problema aparece em seguida.
- O loop continua até o fim da sessão.

---

## 08. Ferramentas do Jogo

### Exemplos de Ferramentas Disponíveis

- Higrômetro
- Lupa
- Lanterna
- Espátula
- Câmera de inspeção
- Termômetro

Cada ferramenta possui:

- Uso específico e bem definido.
- Associação direta com um tipo de problema.

---

## 09. Problemas do Jogo

### Exemplos de Problemas Apresentados ao Jogador

1. Umidade
2. Mofo
3. Cupins
4. Rachaduras estruturais

Cada problema possui:

- Indícios visuais apresentados na parede.
- Ferramenta correta associada para resolução.

---

## 10. Interface — UI/UX

### Elementos da Interface

- Feedback visual de erro.
- Feedback implícito de resolução.
- Diário de Campo acessível durante o jogo.
- Tela final com resultado e pontuação.

---

## 11. Feedbacks do Sistema

### Resposta Correta

- Mudança visual na parede, indicando que o problema foi resolvido.
- Transição automática para o próximo problema.

### Resposta Errada

- Exibição de ícone de erro.
- Som simples de erro, opcional.

---

## 12. Estrutura Lógica — Unity

Estado do jogo e fluxo de execução:

```txt
INÍCIO
  ↓
PROBLEMA ATIVO
  ↓
AGUARDANDO AÇÃO DO JOGADOR
  ↓
VERIFICAÇÃO
  ├── CORRETO → PRÓXIMO PROBLEMA
  └── ERRADO  → CONTINUA NA MESMA RODADA
  ↓
FIM — APÓS X PROBLEMAS
  ↓
RESULTADO FINAL — CHEF
```

---

## 13. Objetivos de Aprendizagem

- Reconhecer problemas de conservação patrimonial.
- Associar ferramentas corretas a cada problema.
- Desenvolver habilidades de tomada de decisão.

---

## 14. Critérios de Sucesso

O projeto será considerado bem-sucedido se:

- O jogador conseguir resolver os problemas propostos.
- O jogador utilizar o Diário de Campo como suporte durante o jogo.
- O jogador aprender por tentativa e acerto consciente.

---

## 15. Diferencial do Projeto

- Simplicidade com propósito educacional claro.
- Foco em decisão, não em exploração livre.
- Loop rápido e eficiente.
- Adaptação às limitações de tempo e escopo do projeto.

---

## MVP Recomendado

Para manter o projeto viável, o MVP deve conter:

- Uma cena fechada.
- Uma parede com problemas visuais alternáveis.
- Uma bancada com ferramentas.
- Sistema de seleção de ferramenta.
- Validação de resposta correta ou incorreta.
- Diário de Campo simples.
- Sistema de pontuação.
- Tela final com feedback do Chef.

---

## Problemas e Ferramentas — Sugestão Inicial

| Problema | Indício Visual | Ferramenta Recomendada |
|---|---|---|
| Umidade | Mancha escura ou área molhada na parede | Higrômetro |
| Mofo | Pontos escuros ou esverdeados | Lupa |
| Cupim | Pequenos buracos ou marcas na madeira | Câmera de inspeção |
| Rachadura estrutural | Fenda visível na parede | Espátula ou câmera de inspeção |

---

## Observação de Escopo

O projeto deve priorizar a clareza da experiência e a tomada de decisão.

Como a duração prevista é de 3 a 5 minutos, o foco deve ser entregar uma experiência funcional, curta e compreensível.
