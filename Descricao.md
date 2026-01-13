### 💉 SQL Injection (SQLi) — DESCRIPTION

## 🇧🇷 PT-BR

A vulnerabilidade de SQL Injection ocorre quando dados controlados pelo usuário são incorporados a consultas SQL sem tratamento adequado (por exemplo, validação, normalização e, principalmente, parametrização). Nessas condições, a entrada pode alterar a lógica da consulta executada pelo banco de dados, levando a comportamentos não intencionais. Dependendo do contexto e dos privilégios da conta de banco utilizada pela aplicação, isso pode resultar em exposição de dados sensíveis, bypass de controles de autenticação/autorização, modificação ou exclusão de informações e, em casos mais graves, comprometimento da integridade e disponibilidade do sistema.

---

## 🇺🇸 EN

SQL Injection occurs when user-controlled input is incorporated into SQL queries without proper handling (such as validation, normalization, and, most importantly, parameterization). In these conditions, the input may change the query logic executed by the database, leading to unintended behavior. Depending on the context and the privileges of the database account used by the application, this may result in sensitive data exposure, authentication/authorization bypass, unauthorized data modification or deletion, and in severe cases, broader impact to system integrity and availability.

---

### 🧪 Cross-Site Scripting (XSS) — DESCRIPTION

## 🇧🇷 PT-BR

A vulnerabilidade de Cross-Site Scripting (XSS) ocorre quando uma aplicação incorpora conteúdo controlado pelo usuário em páginas web sem validação e/ou escape adequado, fazendo com que o navegador interprete esse conteúdo como parte do código da aplicação. Com isso, um atacante pode executar scripts no contexto do usuário afetado, o que pode resultar em sequestro de sessão, roubo de informações exibidas na página, ações indevidas em nome do usuário e impacto na confidencialidade e integridade da experiência. O risco e o alcance variam conforme o ponto de injeção, o nível de interação do usuário e as proteções do front-end e do navegador.

---

## 🇺🇸 EN

Cross-Site Scripting (XSS) occurs when an application includes user-controlled content in web pages without proper validation and/or output escaping, causing the browser to interpret it as part of the application’s code. This can lead to script execution in the victim’s browser within the user’s context, potentially resulting in session hijacking, exposure of data displayed in the page, unauthorized actions performed on behalf of the user, and broader confidentiality/integrity impact. Risk and scope vary depending on where the injection occurs, user interaction, and client-side protections.

---

### 🔑 IDOR (Insecure Direct Object Reference) — DESCRIPTION

## 🇧🇷 PT-BR

A vulnerabilidade de IDOR ocorre quando a aplicação expõe identificadores de recursos e permite acesso com base apenas nesses identificadores, sem validar corretamente a autorização do usuário para o objeto solicitado. Isso pode permitir acesso, alteração ou exclusão de dados de terceiros, causando violação de confidencialidade e integridade.

## 🇺🇸 EN

IDOR occurs when an application exposes resource identifiers and grants access based solely on those identifiers without properly enforcing authorization for the requested object. This may allow users to access, modify, or delete other users’ data, resulting in confidentiality and integrity violations.

---

### 🛡️ CSRF (Cross-Site Request Forgery) — DESCRIPTION

## 🇧🇷 PT-BR

A vulnerabilidade de CSRF ocorre quando a aplicação aceita ações sensíveis baseadas apenas na autenticação automática do navegador (ex.: cookies de sessão), sem mecanismos adicionais para confirmar a intenção do usuário. Assim, um usuário autenticado pode ser induzido a realizar requisições que causam alterações indevidas de estado dentro da aplicação.

## 🇺🇸 EN

CSRF occurs when an application accepts sensitive actions based solely on the browser’s automatic authentication (e.g., session cookies) without additional safeguards to confirm user intent. As a result, an authenticated user may be tricked into sending requests that cause unauthorized state changes within the application.

---

### 📂 LFI / RFI — DESCRIPTION

## 🇧🇷 PT-BR

LFI (Local File Inclusion) e RFI (Remote File Inclusion) são vulnerabilidades que ocorrem quando a aplicação utiliza entradas controladas pelo usuário para montar caminhos/recursos a serem carregados sem validação adequada. No LFI, isso pode permitir a leitura (ou inclusão) de arquivos locais do servidor; no RFI, quando aplicável, pode permitir a inclusão de conteúdo remoto. Dependendo do contexto, isso pode resultar em exposição de informações sensíveis, acesso a configurações internas e, em cenários mais graves, impacto na integridade do sistema.

## 🇺🇸 EN

LFI (Local File Inclusion) and RFI (Remote File Inclusion) occur when an application uses user-controlled input to build file paths/resources to be loaded without proper validation. In LFI, this may allow reading (or including) local server files; in RFI, where applicable, it may allow including remote content. Depending on context, this can lead to sensitive information disclosure, exposure of internal configuration, and in more severe cases, impact to system integrity.

---

### 🌐 SSRF (Server-Side Request Forgery) — DESCRIPTION

## 🇧🇷 PT-BR

SSRF ocorre quando a aplicação permite que um usuário influencie requisições feitas pelo servidor para outros destinos (URLs/hosts) sem restrições adequadas. Isso pode levar o servidor a acessar recursos internos que não deveriam ser expostos, como serviços na rede privada, painéis administrativos ou endpoints de metadados. O impacto pode incluir vazamento de dados, enumeração de serviços internos e, dependendo da arquitetura, acesso indevido a sistemas ou credenciais em ambientes cloud.

## 🇺🇸 EN

SSRF occurs when an application allows a user to influence server-side requests to other destinations (URLs/hosts) without proper restrictions. This can cause the server to access internal resources that should not be exposed, such as private network services, admin panels, or metadata endpoints. Impact may include data exposure, internal service enumeration, and depending on the architecture, unauthorized access to systems or credentials in cloud environments.

---

### 🧨 Command Injection — DESCRIPTION

## 🇧🇷 PT-BR

Command Injection ocorre quando a aplicação executa comandos no sistema operacional a partir de entradas que podem ser influenciadas pelo usuário sem sanitização e controles adequados. Nessa condição, a entrada pode alterar o comando esperado, levando à execução de ações não autorizadas no servidor. O impacto pode variar de exposição de informações e alteração de arquivos até comprometimento mais amplo do host, dependendo dos privilégios do processo e das permissões disponíveis.

## 🇺🇸 EN

Command Injection occurs when an application executes operating system commands using input that can be influenced by the user without proper sanitization and controls. In this condition, the input may change the intended command, leading to unauthorized actions on the server. Impact can range from information disclosure and file modification to broader host compromise, depending on process privileges and available permissions.

---

🧬 XXE (XML External Entity) — DESCRIPTION

## 🇧🇷 PT-BR

XXE ocorre quando a aplicação processa XML com suporte a entidades externas e permite que entradas controladas pelo usuário sejam interpretadas sem restrições adequadas. Isso pode permitir que o parser resolva entidades que acessam recursos locais ou internos, levando a exposição de arquivos, vazamento de informações e, dependendo da configuração e do ambiente, interação indevida com serviços internos.

## 🇺🇸 EN

XXE occurs when an application processes XML with external entity support and allows user-controlled input to be parsed without proper restrictions. This may cause the parser to resolve entities that access local or internal resources, leading to file disclosure, information leakage, and depending on configuration and environment, unintended access to internal services.

---

### 🔀 Open Redirect — DESCRIPTION

## 🇧🇷 PT-BR

Open Redirect ocorre quando a aplicação redireciona o usuário para uma URL fornecida ou influenciada por entrada externa sem validação adequada do destino. Isso pode ser explorado para campanhas de phishing, redirecionamento para páginas maliciosas e abuso de confiança no domínio legítimo, afetando a segurança e a reputação da aplicação.

## 🇺🇸 EN

Open Redirect occurs when an application redirects users to a URL provided or influenced by external input without properly validating the destination. This can be abused for phishing, redirecting users to malicious pages, and leveraging trust in a legitimate domain, impacting both security and reputation.

---

### 📦 Insecure Deserialization — DESCRIPTION

## 🇧🇷 PT-BR

Insecure Deserialization ocorre quando a aplicação desserializa dados não confiáveis (por exemplo, objetos vindos do cliente) sem validação e controles apropriados. Dependendo do formato, bibliotecas e lógica envolvida, isso pode permitir alteração de estado da aplicação, bypass de controles e, em cenários mais graves, impactos severos como execução de ações não autorizadas no servidor.

## 🇺🇸 EN

Insecure Deserialization occurs when an application deserializes untrusted data (e.g., objects provided by the client) without proper validation and controls. Depending on the format, libraries, and application logic, this may enable state manipulation, access control bypass, and in more severe cases, high-impact outcomes such as unauthorized server-side actions.

-------

### 💥 RCE (Remote Code Execution) — DESCRIPTION

## 🇧🇷 PT-BR

RCE (Remote Code Execution) ocorre quando uma falha permite que um atacante execute código no ambiente do servidor remotamente, como resultado de validações ausentes, uso inseguro de componentes, parsing perigoso ou combinações de vulnerabilidades. O impacto é crítico, pois pode permitir controle do sistema, acesso a dados sensíveis, movimentação lateral e comprometimento de infraestrutura, dependendo dos privilégios e segmentações existentes.

## 🇺🇸 EN

RCE (Remote Code Execution) occurs when a flaw allows an attacker to execute code on the server environment remotely, often due to missing validations, unsafe component usage, dangerous parsing, or vulnerability chains. The impact is critical, as it may enable system control, access to sensitive data, lateral movement, and broader infrastructure compromise depending on privileges and segmentation.

---

### 🧩 SSTI (Server-Side Template Injection) — DESCRIPTION

## 🇧🇷 PT-BR

SSTI ocorre quando a aplicação renderiza templates no servidor utilizando dados controlados pelo usuário sem tratamento adequado, permitindo que o conteúdo influencie a lógica do mecanismo de template. Isso pode resultar em acesso indevido a dados, bypass de controles e, dependendo do engine e configurações, impactos severos no servidor.

## 🇺🇸 EN

SSTI occurs when an application renders server-side templates using user-controlled data without proper handling, allowing input to affect the template engine’s logic. This can lead to unauthorized data access, control bypass, and depending on the engine and configuration, severe server-side impact.
