# Análise de Riscos — Fila-Food

## 1. Cenário analisado

O Fila-Food é uma aplicação web criada para gerenciar filas virtuais em estabelecimentos de alimentação.

O projeto foi desenvolvido originalmente sem apoio de Inteligência Artificial. Para esta atividade, a IA Generativa foi utilizada posteriormente como ferramenta de apoio na análise do código, identificação dos riscos, organização das informações e definição inicial das estratégias de resposta.

## 2. Principais riscos identificados

### 2.1 Senhas armazenadas em texto puro

**Descrição:** As senhas de clientes e restaurantes são armazenadas e comparadas diretamente no banco de dados, sem uso de hash.

**Probabilidade:** Alta  
**Impacto:** Alto

**Consequências possíveis:**

- exposição de credenciais;
- acesso indevido a contas;
- comprometimento de dados;
- reutilização das mesmas senhas em outros serviços.

### 2.2 Ausência de autenticação e autorização robustas

**Descrição:** O sistema não possui controle adequado de sessão, token ou autorização por perfil.

**Probabilidade:** Alta  
**Impacto:** Alto

**Consequências possíveis:**

- alteração indevida de filas;
- exclusão de registros;
- acesso a informações de outros usuários;
- manipulação de dados por pessoas não autorizadas.

### 2.3 Falta de validação dos dados de entrada

**Descrição:** A API aceita dados sem validação suficiente de formato, obrigatoriedade, limites e consistência.

**Probabilidade:** Alta  
**Impacto:** Médio

**Consequências possíveis:**

- registros inválidos;
- falhas de execução;
- dados inconsistentes;
- comportamento incorreto da aplicação.

### 2.4 Manipulação incorreta da fila

**Descrição:** O controle da fila ainda é simplificado e não contempla integralmente regras como posição, prioridade, desistência, chamada do cliente e concorrência entre atendimentos.

**Probabilidade:** Média  
**Impacto:** Alto

**Consequências possíveis:**

- ordem incorreta de atendimento;
- duplicidade de clientes;
- conflitos de atualização;
- perda de confiança no sistema.

### 2.5 Ausência de testes automatizados

**Descrição:** O projeto não possui uma estratégia clara de testes para backend, frontend, segurança e regras de negócio.

**Probabilidade:** Alta  
**Impacto:** Médio

**Consequências possíveis:**

- regressões;
- erros não identificados;
- dificuldade de manutenção;
- maior risco durante alterações futuras.

### 2.6 Dependências desatualizadas

**Descrição:** O projeto utiliza versões antigas de bibliotecas e frameworks.

**Probabilidade:** Média  
**Impacto:** Médio

**Consequências possíveis:**

- vulnerabilidades conhecidas;
- incompatibilidade com versões atuais do Node.js;
- dificuldade de manutenção;
- aumento do esforço para atualização futura.

### 2.7 Uso de SQLite em um cenário com múltiplos usuários

**Descrição:** O SQLite é adequado para protótipos, mas pode apresentar limitações em um ambiente com maior volume de acessos e operações simultâneas.

**Probabilidade:** Média  
**Impacto:** Médio

**Consequências possíveis:**

- bloqueios de escrita;
- baixa escalabilidade;
- degradação de desempenho;
- dificuldade de operação em produção.

## 3. Matriz qualitativa de riscos

| Risco | Probabilidade | Impacto | Prioridade |
|---|---|---|---|
| Senhas armazenadas em texto puro | Alta | Alto | Crítica |
| Falta de autenticação e autorização | Alta | Alto | Crítica |
| Manipulação incorreta da fila | Média | Alto | Alta |
| Falta de validação de entrada | Alta | Médio | Alta |
| Ausência de testes automatizados | Alta | Médio | Alta |
| Dependências desatualizadas | Média | Médio | Média |
| Uso de SQLite em múltiplos acessos | Média | Médio | Média |

## 4. Estratégia de resposta prioritária

A estratégia mais importante é **mitigar o risco de acesso não autorizado e manipulação indevida da fila**.

Ações recomendadas:

- armazenar senhas com hash seguro, utilizando bcrypt ou Argon2;
- implementar autenticação com sessão segura ou token;
- criar controle de autorização por perfil;
- garantir que clientes e restaurantes só possam alterar seus próprios dados;
- validar todos os dados recebidos pela API;
- restringir os campos permitidos em operações de atualização;
- registrar operações críticas em logs;
- criar testes automatizados para autenticação, autorização e regras da fila.

Essa estratégia é prioritária porque, sem segurança e controle de acesso, o sistema não pode ser utilizado de forma confiável, mesmo como piloto.

## 5. Como a Inteligência Artificial Generativa apoiou a atividade

A IA Generativa foi utilizada para:

- analisar o código e a estrutura do projeto;
- identificar riscos técnicos, operacionais e de segurança;
- organizar os riscos em categorias;
- classificar qualitativamente probabilidade e impacto;
- sugerir estratégias iniciais de resposta;
- estruturar este documento.

## 6. Limitações e cuidados no uso da IA

As sugestões da IA não devem ser consideradas decisões definitivas.

Durante a análise, foi necessário considerar que a IA:

- pode gerar riscos genéricos;
- pode interpretar incorretamente partes do código;
- não conhece todo o contexto original do projeto;
- não executou testes reais no ambiente;
- pode apresentar recomendações com excesso de confiança;
- depende da qualidade das informações fornecidas.

Por isso, todas as conclusões devem passar por validação humana antes de qualquer alteração no projeto.

## 7. Conclusão

O Fila-Food é um protótipo válido para demonstração do conceito de fila virtual, mas ainda apresenta riscos importantes para uso real.

Os pontos mais críticos estão relacionados à segurança, controle de acesso, integridade da fila, validação de dados e ausência de testes.

A IA Generativa contribuiu para acelerar a identificação e a organização dos riscos, mas a análise final, a priorização e a responsabilidade pelas decisões continuam sendo humanas.
