# Sistema de Gamificação Acadêmica
**Documento de Requisitos — v1.0**
Data: Junho/2026 | Autor: Jonathan Ponte

---

## 1. Visão Geral

Sistema de gamificação voltado para disciplinas de graduação, com o objetivo de aumentar o engajamento dos alunos por meio de mecânicas de jogo: missões, pontuação por XP, níveis, clãs, rankings e conquistas (badges).

---

## 2. Perfis de Usuário

| Perfil | Descrição |
|--------|-----------|
| **Admin** | Gerencia a plataforma, cria professores |
| **Professor** | Cria turmas, define missões e pontuações |
| **Aluno** | Participa de turmas, realiza missões, forma clãs |

---

## 3. Turmas

- O professor cria uma turma vinculada a uma disciplina
- A turma gera um **código único** de acesso
- O aluno entra na turma inserindo o código
- Um aluno pode estar em **múltiplas turmas** simultaneamente (cada turma = uma disciplina diferente)
- Cada turma tem seu próprio ranking e sistema de clãs independente

---

## 4. Missões

### 4.1 Tipos de Missão

| Tipo | Descrição |
|------|-----------|
| **Quiz** | Conjunto de perguntas com respostas dentro da plataforma |
| **Entrega de arquivo** | Aluno faz upload de um arquivo como entrega |
| **Presença** | Professor registra ou confirma a presença do aluno |
| **Missão cronometrada** | Tempo de execução é medido; mais rápido = mais XP |
| **Desafio surpresa** | Aparece de forma repentina, disponível por tempo limitado (ex: 2h) |

### 4.2 Regras das Missões

- O **professor define** o valor em XP de cada missão
- Toda missão tem **data de início e data de encerramento**
- Entregas dentro do prazo recebem o XP total
- **Entrega atrasada:** recebe XP reduzido (ex: -30% por dia de atraso)
- **Sem entrega:** recebe 0 XP e pode receber penalização adicional
- Missões cronometradas calculam bônus proporcional à velocidade de conclusão
- Desafios surpresa têm janela de disponibilidade configurável pelo professor (mínimo 1h)

### 4.3 Missões de Clã

- Algumas missões podem ser configuradas como **missões coletivas**
- A missão de clã só é concluída quando **todos os membros do clã completam** sua parte
- A pontuação é distribuída para todos os membros do clã ao concluir
- Membros podem ver o progresso dos colegas dentro da missão

---

## 5. Sistema de XP e Níveis

### 5.1 Ganho de XP

- Completar missão no prazo: XP cheio definido pelo professor
- Completar missão atrasada: XP reduzido (percentual configurável)
- Bônus por velocidade em missão cronometrada: até +50% do XP base
- Bônus por conquista de badge: XP fixo por badge (definido na tabela de badges)

### 5.2 Tabela de Níveis (v1.0)

| Nível | Nome | XP Necessário |
|-------|------|---------------|
| 1 | Calouro | 0 |
| 2 | Veterano | 500 |
| 3 | Especialista | 1.500 |
| 4 | Mestre | 3.500 |
| 5 | Lendário | 7.500 |

> Tabela pode ser customizada em versões futuras pelo professor ou admin.

---

## 6. Clãs

- Alunos formam clãs **dentro de cada turma**
- O clã é criado por um aluno que se torna o **líder**
- Outros alunos entram no clã por convite ou código do clã
- Cada turma tem um **ranking de clãs** paralelo ao ranking individual
- Missões coletivas são exclusivas para clãs
- Um aluno pertence a **no máximo um clã por turma**

---

## 7. Rankings

### 7.1 Ranking Individual

- Exibe os alunos da turma ordenados por XP total
- Destaque visual para o **top 3** da turma
- Atualizado em tempo real a cada missão concluída

### 7.2 Ranking de Clãs

- Exibe os clãs da turma ordenados pela soma de XP de seus membros
- Destaque para o clã líder
- Atualizado em tempo real

---

## 8. Badges (Conquistas)

Lista inicial de 20 badges do sistema:

| # | Badge | Descrição | XP Bônus |
|---|-------|-----------|----------|
| 1 | **Primeira Missão** | Completou a primeira missão na plataforma | 50 |
| 2 | **Pontual** | Entregou 5 missões consecutivas dentro do prazo | 100 |
| 3 | **Veloz** | Completou uma missão cronometrada no top 10% mais rápidos | 150 |
| 4 | **Flash** | Completou um desafio surpresa | 200 |
| 5 | **Maratonista** | Completou missões por 7 dias consecutivos | 200 |
| 6 | **Dedicado** | Completou 10 missões no total | 100 |
| 7 | **Incansável** | Completou 50 missões no total | 300 |
| 8 | **Lenda da Turma** | Chegou ao topo do ranking individual da turma | 500 |
| 9 | **Pódio** | Ficou no top 3 do ranking ao menos uma vez | 200 |
| 10 | **Guerreiro do Clã** | Completou 5 missões coletivas de clã | 150 |
| 11 | **Líder Nato** | Criou um clã e liderou até o top 3 do ranking de clãs | 300 |
| 12 | **Time Unido** | O clã completou uma missão coletiva com 100% de participação | 250 |
| 13 | **Virada** | Subiu 5 posições no ranking em uma semana | 150 |
| 14 | **Perfeccionista** | Tirou a pontuação máxima em um quiz | 100 |
| 15 | **Multitarefa** | Completou 3 missões diferentes no mesmo dia | 150 |
| 16 | **Sobrevivente** | Completou uma missão no último minuto antes do prazo | 50 |
| 17 | **Mestre do Tempo** | Ficou entre os 3 mais rápidos em uma missão cronometrada | 200 |
| 18 | **Presença Total** | Registrou presença em todas as aulas de uma semana | 150 |
| 19 | **Explorador** | Participou de turmas de 3 disciplinas diferentes | 100 |
| 20 | **Lendário** | Atingiu o nível máximo (Lendário) | 1000 |

---

## 9. Notificações

O sistema deve notificar o aluno quando:

- Uma nova missão for criada na turma
- Um desafio surpresa aparecer
- O prazo de uma missão estiver próximo (24h antes)
- O aluno subir de nível
- O aluno ganhar um badge
- Um colega de clã concluir sua parte em missão coletiva
- O clã concluir uma missão coletiva

---

## 10. Requisitos Não Funcionais

| Requisito | Descrição |
|-----------|-----------|
| **Autenticação** | JWT com refresh token; roles: admin, professor, aluno |
| **Performance** | Ranking atualizado em tempo real via eventos assíncronos |
| **Escalabilidade** | Arquitetura de microsserviços com comunicação via fila de mensagens |
| **Documentação** | Todos os endpoints documentados com Swagger/OpenAPI |
| **Containerização** | Toda a aplicação deve rodar via Docker Compose |
| **CI/CD** | Pipeline automatizado com GitHub Actions |
| **Banco de dados** | PostgreSQL para dados relacionais; MongoDB para badges e eventos |

---

## 11. Próximos Passos

- [x] Criar estrutura base do projeto no GitHub
- [x] Implementar Auth Service — registro e login com JWT ✅
- [ ] Finalizar Auth Service (refresh token, /validate, Swagger, testes)
- [ ] Definir schema de banco de dados de cada serviço
- [ ] Mapear todos os endpoints REST por microsserviço
- [ ] Definir os eventos publicados na fila RabbitMQ
- [ ] Implementar User Service
- [ ] Implementar Mission Service
- [ ] Implementar Score Service
- [ ] Implementar Badge Service
- [ ] Implementar Notification Service
- [ ] Implementar API Gateway
- [ ] Configurar CI/CD com GitHub Actions

---

## 12. Histórico de Versões

| Versão | Data | Descrição |
|--------|------|-----------|
| v1.0 | Jun/2026 | Documento inicial de requisitos |
