# 🔎 Relatório Técnico (Visão Especializada)

### 1. Reconhecimento
Durante a análise inicial da aplicação, foi inspecionado o código-fonte HTML da página.

Achado relevante:

- Presença de credenciais expostas associadas a um utilizador comum

- Isso indica falha no armazenamento seguro de informações sensíveis.

Evidência sugerida:

- Print do código HTML contendo as credenciais: [print](../images/html_code.png)

<hr>

### 2. Exploração

Após autenticação com o utilizador identificado, foi analisado o comportamento da aplicação durante a navegação.

#### Observação:

- O sistema utilizava parâmetros na URL para definir o nível de acesso do utilizador

#### Exemplo de estrutura identificada:

> /profile.php?user=guest

#### Ação realizada:

- Manipulação direta do parâmetro de utilizador

#### Exemplo modificado:

> /profile.php?user=admin

#### Resultado:

- A aplicação concedeu acesso ao painel administrativo sem validação adicional

Isso confirma a ausência de verificação de autorização no lado do servidor.

#### Evidências:

> Print da URL antes e depois da modificação: [antes](../images/guest_page.png)<br>
> Print do acesso ao painel administrativo: [depois](../images/admin_page.png)

<hr>

### 3. Pós-Exploração

#### Com o acesso administrativo obtido, foi possível:

- Visualizar funcionalidades restritas
- Confirmar elevação de privilégio
- Acessar áreas críticas do sistema

#### Prova de exploração:

- Acesso ao painel de administrador ou captura da flag do desafio

<hr>

### 4. Análise da Vulnerabilidade

A falha ocorre devido à confiança indevida em dados controlados pelo cliente (client-side).

#### O sistema não valida:

- Identidade do utilizador autenticado
- Permissões associadas à sessão

#### Isso viola princípios fundamentais de segurança, como:

- Confiança zero (Zero Trust)
- Validação no servidor (Server-Side Enforcement)

<hr>

### 5. Boas práticas adicionais:

1. Utilizar tokens de sessão seguros
2. Implementar autenticação e autorização separadamente
3. Registrar logs de acesso e atividades suspeitas
4. Aplicar frameworks com controlo de acesso robusto

<hr>

### 6. Conclusão

A exploração demonstrou, de forma prática, como uma falha simples pode abrir portas para o controlo total de um sistema.

Mais do que explorar, este exercício reforça um princípio essencial:
a segurança deve residir na validação rigorosa no servidor, jamais na confiança do cliente.
