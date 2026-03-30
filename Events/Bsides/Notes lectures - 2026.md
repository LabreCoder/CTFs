# Resumo das Palestras — BSidesRJ

<b>*[Link para os sites citados no evento.](/Notes%20-%202026.md)*</b>

## 1. OPSEC for Red Teams — Operações Clandestinas Autorizadas

A palestra apresentou um princípio fundamental: não basta simular ameaças — é preciso agir como uma. Dentro desse contexto, o conceito de OPSEC (Operational Security) torna-se essencial para operações de Red Team realmente eficazes.

O palestrante trouxe uma reflexão direta: muitos operadores são detectados não por azar, mas por falhas simples na execução de suas ações. A proposta foi demonstrar como pequenos descuidos podem comprometer toda uma operação, especialmente quando não há atenção à forma como o ambiente está configurado.

Foram apresentados exemplos práticos, como operadores que utilizam ambientes baseados em máquinas virtuais com orquestradores como Proxmox. Dependendo da configuração da rede, ao obter acesso interno, um simples pedido DHCP pode revelar informações sensíveis — como um “banner” identificando o ambiente utilizado. Além disso, protocolos como mDNS/Bonjour, quando mal configurados, podem enviar pacotes em broadcast que denunciam a presença do operador.

A palestra também trouxe experiências reais vividas ao longo de anos em operações de Red Team, tanto no Brasil quanto no exterior, reforçando a importância da disciplina operacional e da atenção aos detalhes.

**Exemplo técnico:**  
Um operador utiliza um ambiente virtual com Proxmox. Ao conectar-se à rede alvo, um pedido DHCP pode incluir informações que revelam o nome do host ou características da infraestrutura, expondo o ambiente do atacante.

**Exemplo do dia a dia:**  
É como um investigador disfarçado que esquece de tirar o crachá da própria empresa antes de se infiltrar — um pequeno detalhe que compromete toda a operação.

---

## 2. Old Dogs, Old Tricks!

A palestra abordou um ponto intrigante: atacantes continuam previsíveis. Mesmo com o avanço das tecnologias, muitos padrões de ataque permanecem os mesmos, especialmente nas fases de reconhecimento, enumeração e movimentação lateral.

A proposta apresentada foi ir além da defesa tradicional baseada em bloqueio. Em vez de simplesmente negar acesso, a ideia é responder ao atacante com informações falsas, porém plausíveis. Essa abordagem de decepção defensiva busca distorcer o fingerprinting, quebrar automações e aumentar o custo operacional do ataque.

O palestrante demonstrou como é possível explorar padrões recorrentes de comportamento dos atacantes para criar respostas que os conduzam ao erro, gerando ao mesmo tempo uma telemetria rica e de alto valor, baseada em ações reais.

Outro ponto relevante foi o uso de ferramentas open-source para implementar essas estratégias, tanto em ambientes on-premises quanto em cloud, tornando a abordagem acessível e aplicável em diferentes cenários.

**Exemplo técnico:**  

Um exemplo que o Pr0teus apresentou foi de deixar um comentário dentro do código html da página com uma **tentação** para o invasor testar um SQLInjection e dessa forma acabar se revelando, ou ser redirecionado para uma página fake, tudo isso com o objetivo de testar até onde o invasor é capaz de ir e também de fazer ele gastar tempo e, principalmente, recursos. 

**Exemplo do dia a dia:**  
É como fornecer um mapa errado para alguém que tenta invadir um local — ele continua andando, mas sempre na direção errada.

---

## 3. Experiências na Análise de OSINT usando a Técnica de Avaliação de Dados

A palestra destacou um dos maiores desafios da atualidade: lidar com o excesso de informação. Em um mundo repleto de dados provenientes de fontes abertas (OSINT), públicas e não controladas, o verdadeiro diferencial está na capacidade de filtrar o que realmente importa.

O palestrante trouxe a aplicação da técnica conhecida como Admiralty System, que auxilia na avaliação tanto da confiabilidade da fonte quanto da credibilidade da informação. Essa metodologia permite estruturar a análise de forma mais precisa, reduzindo o risco de decisões baseadas em dados incorretos ou irrelevantes.

Foi enfatizado que o trabalho do analista não é apenas coletar dados, mas interpretá-los com criticidade, distinguindo sinais relevantes em meio ao ruído informacional.

**Exemplo técnico:**  
Ao analisar um perfil em rede social, o analista verifica a consistência das postagens, a origem das informações e cruza dados com outras fontes para validar a veracidade.

**Exemplo do dia a dia:**  
É como ouvir um boato — antes de acreditar, você busca confirmar com outras pessoas e avaliar se a fonte é confiável.

---

## 4. De 0 ao SOC: a curva real que ninguém ensina

A palestra trouxe uma visão prática e estruturada sobre a jornada até o SOC (Security Operations Center), explicando por que há tantas vagas disponíveis e, ao mesmo tempo, poucos profissionais preparados para ocupá-las.

Foi apresentada uma curva de aprendizado clara, que começa pelos fundamentos essenciais — redes, sistemas e automação — e evolui para práticas específicas do SOC, como uso de SIEM, análise de logs e entendimento de frameworks como MITRE ATT&CK.

Um dos pontos mais marcantes foi a necessidade de construir um portfólio simples, porém verificável. Mais do que certificados, o mercado busca profissionais que consigam demonstrar suas habilidades na prática.

A palestra também trouxe uma analogia interessante: aplicar o mesmo raciocínio de um SOC na própria carreira. Ou seja, coletar evidências do aprendizado, correlacionar com as exigências do mercado e agir estrategicamente para evoluir.

A mensagem final reforça que o caminho não é rápido, mas, quando seguido com ordem e consistência, torna-se totalmente possível.

**Exemplo técnico:**  
Um candidato documenta suas análises de logs em um repositório público, demonstrando sua capacidade de investigação e correlação de eventos.

**Exemplo do dia a dia:**  
É como montar um currículo com provas reais — não apenas dizer que sabe, mas mostrar o que já fez.

---

## 5. Ambientes Descartáveis na Prática: Containers, OPSEC e Segurança com Kasm Workspaces

A palestra apresentou uma abordagem moderna para segurança operacional baseada no uso de ambientes descartáveis. A proposta é abandonar a dependência de máquinas locais, VPNs e configurações complexas, migrando para ambientes isolados, efêmeros e acessados diretamente pelo navegador.

Utilizando ferramentas como Kasm Workspaces, é possível criar ambientes temporários que são destruídos após o uso, reduzindo drasticamente riscos de persistência de ameaças, vazamento de dados e rastreamento.

Foram discutidos os ganhos em segurança, agilidade e simplicidade, além de comparações com abordagens tradicionais, evidenciando como essa mudança de paradigma pode elevar o nível de proteção das operações.

A palestra também trouxe demonstrações práticas, mostrando como essa abordagem pode ser aplicada no dia a dia de profissionais de segurança.

**Exemplo técnico:**  
Um analista acessa um ambiente Kasm Workspace para investigar um arquivo suspeito. Ao finalizar a sessão, todo o ambiente é destruído, eliminando qualquer persistência de malware.

**Exemplo do dia a dia:**  
É como usar um bloco de notas descartável — após utilizá-lo, você o destrói, garantindo que nenhuma informação fique exposta.

---


<!-- Descrição sobre cada uma das palestras disponíveis no site do evento >

1. OPSEC for red teams - operações clandestinas autorizadas
Palestrante: Oliveira Lima
Detalhes: Como costumo dizer: não simule a ameaça — seja a ameaça. Para isso, precisamos de certas doses de OPSEC para preparar os times defensores a lidarem com ameaças que estão realmente prontas para tal. Falaremos sobre por que, muitas vezes, os operadores são detectados — não por azar, mas simplesmente por não se atentarem à forma como suas ações são executadas. Desde o exemplo simples do operador que utiliza um equipamento com setup em VMs, usando orquestradores como Proxmox. Será que os operadores sabem que, dependendo de como suas redes estão configuradas, ao obter acesso à rede interna durante um pedido DHCP, o pacote pode enviar um “banner” gigante chamado Proxmox? Ou que, dependendo da configuração de rede do setup, pacotes do protocolo mDNS/Bonjour em broadcast podem denunciar a presença do operador? Levarei também diversas outras situações vividas ao longo de anos de operações de Red Team no Brasil e no mundo, além de exemplos técnicos e casos apresentados em conferências.
Sobre

Oliveira Lima Jr é fundador da Hakai security e tem mais de 14 anos de experiência em cibersegurança, com foco em pentest e operações de Red Team. Ao longo de sua carreira como pesquisador, já reportou diversas vulnerabilidades críticas em empresas como Trend Micro, Cisco, D-Link, entre outras — além de ter mais de 40 CVEs registrados em seu nome.

2. Old dogs old tricks!
Palestrante: Felipe Proteus
Deatlhes: Atacantes continuam previsíveis. Nesta palestra, Felipe Pr0teus apresenta técnicas de decepção defensiva em nível de rede que exploram padrões recorrentes de reconhecimento, enumeração e movimento lateral, substituindo a negação pura por respostas falsas, porém plausíveis, capazes de distorcer fingerprinting, quebrar automação e aumentar o custo operacional do ataque, gerando telemetria de alto sinal a partir de comportamento real, usando ferramentas open-source, em cenários on-prem e cloud.

3. Experiências na Análise de OSINT usando a Técnica de Avaliação de Dados (Admiralty System)
Palestrante: César Montenegro Justo
Detalhes: Em meio à abundância de dados oriundos de fontes abertas (OSINT), públicas e não controladas, o grande desafio dos analistas é distinguir o que é realmente relevante do que constitui apenas ruído.

4. De 0 ao SOC: a curva real que ninguém ensina (e por que isso importa)
Palestrante: Kizzy Macedo Benjamin
Detalhes: Por que há tantas vagas em SOC e tão pouca gente entrando? Nesta palestra, você entende a verdadeira curva de aprendizado do Blue Team — uma ordem clara que começa pelos fundamentos (redes, sistemas e automação), evolui para práticas de SOC (SIEM, logs, MITRE) e chega ao que realmente gera entrevistas: um portfólio simples, mas verificável. Você aprende a aplicar o mesmo modelo de raciocínio do SOC à carreira: coletar evidências do seu aprendizado, correlacionar com o que as vagas pedem e agir para mostrar suas habilidades. Menos cursos aleatórios, mais progresso mensurável. O caminho não é rápido — mas, com a ordem certa, é totalmente possível.

Sobre

Profissional com mais de 20 anos de experiência em tecnologia, atua como Analista de Segurança da Informação na M. Dias Branco. É Cientista da Computação pela Universidade Gama Filho e Mestre em Sistemas de Informação pela UNIRIO.

5. Ambientes Descartáveis na Prática: Containers, OPSEC e Segurança com Kasm Workspaces
Palestrante: Marco Combat
Detalhes: Esta palestra apresenta uma abordagem moderna para segurança operacional baseada em ambientes descartáveis com Kasm Workspaces. Ao invés de depender de máquinas locais, VPNs e configurações complexas, a proposta é operar com ambientes isolados, efêmeros e executados diretamente no navegador.

Serão explorados os ganhos em segurança, agilidade e redução de riscos, além de comparações com abordagens tradicionais e demonstrações práticas.
Sobre

Marco Combat é especialista em cibersegurança, arquitetura de sistemas e computação em nuvem, com mais de 20 anos de experiência em tecnologia.

É professor, na WB Educação, de pós-graduação e instrutor em temas como OSINT, cloud e inteligência aplicada, formando profissionais em todo o Brasil. Ao longo da carreira, liderou projetos de desenvolvimento, automação e segurança, com foco em ambientes escaláveis, resilientes e seguros.

>
