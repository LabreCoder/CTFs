# 📄 Relatório Gerencial (Visão Executiva)

## 1. Introdução

Durante a execução de um laboratório prático da plataforma TryHackMe, foi analisado um ambiente simulado com foco em controlo de acesso em aplicações web. O objetivo consistiu em identificar fragilidades que permitissem a elevação indevida de privilégios dentro do sistema.

## 2. Sumário de Riscos

Foi identificada uma falha crítica no controlo de acesso, permitindo que utilizadores comuns obtivessem privilégios administrativos através da manipulação de parâmetros na URL.

Essa vulnerabilidade caracteriza-se como IDOR (Insecure Direct Object Reference), onde o sistema confia excessivamente em dados fornecidos pelo cliente.

## 3. Impacto no Negócio

O impacto associado a essa falha é elevado:

Comprometimento total do sistema
Acesso não autorizado a funcionalidades administrativas
Possível exposição de dados sensíveis
Risco de alteração ou exclusão de informações críticas

Em um cenário real, tal fragilidade poderia resultar em perdas financeiras, danos reputacionais e não conformidade com normas de segurança.

## 4. Postura de Risco

#### Classificação: Alta

A vulnerabilidade apresenta:

1. Baixa complexidade de exploração
2. Alta probabilidade de ocorrência
3. Impacto crítico no ambiente

## 5. Recomendações

Para mitigar o risco identificado, recomenda-se:

- Implementar controlo de acesso baseado em sessão no lado do servidor
- Validar permissões de utilizadores independentemente de parâmetros da URL
- Evitar exposição de informações sensíveis no código fonte HTML
- Aplicar princípios de menor privilégio (Least Privilege)
- Realizar testes contínuos de segurança (pentests e code review)
