# 🚀 CTF Writeup — Neighbour (TryHackMe)


### 📌 Visão Geral

Este repositório documenta a resolução do laboratório Neighbour, disponível na plataforma TryHackMe.

O desafio apresenta um cenário clássico de falha em controlo de acesso, permitindo explorar uma vulnerabilidade do tipo IDOR (Insecure Direct Object Reference) para obter privilégios elevados dentro da aplicação.

Mais do que uma simples conquista técnica, este exercício reforça princípios fundamentais da segurança da informação: não confiar no cliente e validar sempre no servidor.

<hr>

### 🎯 Objetivo

O objetivo deste laboratório foi:

- Identificar vulnerabilidades no controlo de acesso
- Explorar falhas de validação de permissões
- Obter acesso administrativo sem credenciais legítimas
- Documentar o processo de exploração de forma profissional

<hr>

### 🧠 Conceitos Abordados
- IDOR (Insecure Direct Object Reference)
- Controlo de acesso (Access Control)
- Manipulação de parâmetros na URL
- Princípio de menor privilégio (Least Privilege)
- Validação server-side
- Enumeração e análise de código fonte

<hr>

### 🔍 Metodologia

A abordagem seguiu etapas clássicas de um teste de segurança:

1. Reconhecimento
- Análise do código-fonte HTML
- Identificação de informações sensíveis expostas
- Descoberta de credenciais de utilizador comum

2. Exploração
- Autenticação na aplicação
- Manipulação de parâmetros na URL
- Alteração do nível de privilégio (user → admin)

3. Pós-Exploração
- Acesso ao painel administrativo
- Validação da elevação de privilégios
- Captura da flag do desafio

<hr>

### ⚠️ Vulnerabilidade Identificada
#### IDOR (Insecure Direct Object Reference)

A aplicação permitia que o nível de acesso fosse definido diretamente por parâmetros manipuláveis na URL.

#### Exemplo vulnerável:

> /profile.php?user=guest

#### Exploração:

> /profile.php?user=admin

#### Impacto:

- Escalação de privilégios
- Acesso não autorizado
- Comprometimento total da aplicação

<hr>

### Boas práticas recomendadas:
- Nunca confiar em dados do cliente
- Utilizar sessões seguras
- Implementar controlo de acesso robusto
- Evitar exposição de credenciais no frontend
- Realizar testes de segurança recorrentes

<hr>

### 📊 Classificação de Risco
- Critério	        |    Avaliação
- Complexidade	    |      Baixa
- Impacto	        |      Alto
- Probabilidade	    |      Alta
- Severidade Final	|   🔴 Alta

<hr>

### 📎 Evidências

Acessar a pasta de [images](images/)!


<hr>

### 🧾 Estrutura do Repositório
```
├── README.md
├── report/
│   ├── relatorio_gerencial.md
│   └── relatorio_tecnico.md
└── images/
    ├── admin_page.png
    ├── guest_page.png
    └── html_code.png
```
<hr>

### 💡 Lições Aprendidas

Este laboratório ensina, com simplicidade e profundidade, que:

- Pequenas falhas podem gerar grandes impactos
- Segurança não é apenas tecnologia, mas disciplina
- A validação no servidor é indispensável
- A documentação bem feita diferencia profissionais

<hr>

### 🔗 Plataforma

Desafio realizado em:
👉 https://tryhackme.com

<hr>

### 📣 Considerações Finais

A prática constante, aliada à documentação clara, constrói não apenas conhecimento, mas reputação.

Cada vulnerabilidade compreendida é uma porta fechada contra riscos futuros — e um passo firme na jornada da cibersegurança.