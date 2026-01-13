# 🛠️ Recomendações / Recommendations (Top Issues)

> PT: Recomendações em alto nível, focadas em prevenção e correção, sem conteúdo de exploração.  
> EN: High-level recommendations focused on prevention and remediation, without exploit content.

---

### 🗃️ SQL Injection (SQLi) — RECOMENDAÇÃO / RECOMMENDATION

## 🇧🇷 PT-BR
Para mitigar **SQL Injection**, utilize **consultas parametrizadas (prepared statements)** em todas as interações com o banco de dados, evitando a montagem de queries por concatenação de strings. Aplique validação de entrada conforme o tipo esperado (formato, tamanho e caracteres permitidos) e use o **princípio do menor privilégio** nas credenciais do banco (permissões mínimas necessárias). Em produção, evite expor mensagens detalhadas de erro do banco para o usuário final; registre falhas de forma controlada e segura, e mantenha revisão de código e testes para prevenir regressões.

## 🇺🇸 EN
To mitigate **SQL Injection**, use **parameterized queries (prepared statements)** for all database interactions and avoid building SQL statements through string concatenation. Enforce input validation based on expected type (format, length, and allowed characters) and apply the **principle of least privilege** to database credentials (minimum required permissions). In production, avoid exposing detailed database error messages to end users; log failures safely and in a controlled manner, and maintain code review and testing to prevent regressions.

---

### 🧪 Cross-Site Scripting (XSS) — RECOMENDAÇÃO / RECOMMENDATION

## 🇧🇷 PT-BR
Para reduzir o risco de **XSS**, aplique **escape/codificação de saída** de acordo com o contexto (HTML, atributos, URL e JavaScript) e evite renderizar conteúdo não confiável como HTML. Prefira frameworks e templates que façam escaping automaticamente, e aplique validação de entrada quando fizer sentido (tipo, formato, tamanho). Como camada adicional, implemente uma **Content Security Policy (CSP)** bem definida e utilize cookies com **HttpOnly** e **Secure** quando aplicável, reduzindo o impacto em caso de falhas.

## 🇺🇸 EN
To reduce **XSS** risk, apply **context-aware output encoding/escaping** (HTML, attributes, URL, and JavaScript) and avoid rendering untrusted content as HTML. Prefer frameworks/templates that escape by default and enforce input validation where applicable (type, format, length). As an additional layer, implement a well-defined **Content Security Policy (CSP)** and use **HttpOnly** and **Secure** cookies when applicable to reduce impact if issues arise.

---

### 🔑 IDOR — RECOMENDAÇÃO / RECOMMENDATION

## 🇧🇷 PT-BR
Para corrigir **IDOR**, implemente **autorização no servidor (server-side)** para cada requisição, verificando explicitamente se o usuário autenticado tem permissão para o recurso/ação solicitados (**controle por objeto**). Evite depender de validações apenas no front-end e adote uma estratégia consistente de autorização (por exemplo, RBAC/ABAC) com regras centralizadas. Inclua testes de autorização (cenários permitidos e negados) e revise endpoints/rotas para garantir que o controle de acesso seja aplicado de forma uniforme.

## 🇺🇸 EN
To fix **IDOR**, enforce **server-side authorization** on every request by explicitly verifying that the authenticated user is allowed to access/act on the requested resource (**object-level access control**). Do not rely on front-end checks; adopt a consistent authorization strategy (e.g., RBAC/ABAC) with centralized rules. Add authorization tests (allowed/denied scenarios) and review endpoints/routes to ensure access controls are applied uniformly.

---

### 🛡️ CSRF — RECOMENDAÇÃO / RECOMMENDATION

## 🇧🇷 PT-BR
Para prevenir **CSRF**, implemente **tokens anti-CSRF** para operações que alteram estado (como POST/PUT/PATCH/DELETE) e valide o token no servidor. Configure cookies de sessão com políticas adequadas (**SameSite**, além de **Secure** e **HttpOnly** quando aplicável) e evite ações sensíveis via GET. Quando fizer sentido, utilize validação de **Origin/Referer** como defesa adicional e aplique confirmação do usuário em operações de alto risco.

## 🇺🇸 EN
To prevent **CSRF**, implement **anti-CSRF tokens** for state-changing operations (POST/PUT/PATCH/DELETE) and validate them server-side. Configure session cookies with appropriate policies (**SameSite**, plus **Secure** and **HttpOnly** when applicable) and avoid sensitive actions via GET. Where appropriate, use **Origin/Referer** validation as an additional defense and require user confirmation for high-risk operations.

---

### 🌐 SSRF — RECOMENDAÇÃO / RECOMMENDATION

## 🇧🇷 PT-BR
Para mitigar **SSRF**, restrinja destinos de requisições server-side usando **allowlist** de domínios/hosts e valide URLs de forma robusta (esquema, host, porta e resolução). Bloqueie acesso a endereços internos e metadados sensíveis conforme a arquitetura e mantenha controles de rede (segmentação/egress rules) para limitar comunicação do servidor com serviços internos. Registre tentativas anômalas e trate redirecionamentos com cuidado, evitando que a aplicação seja induzida a acessar destinos não autorizados.

## 🇺🇸 EN
To mitigate **SSRF**, restrict server-side request destinations using an **allowlist** of domains/hosts and perform robust URL validation (scheme, host, port, and resolution). Block access to internal ranges and sensitive metadata endpoints as required by your architecture and enforce network controls (segmentation/egress rules) to limit server communication with internal services. Log anomalous attempts and handle redirects carefully to avoid reaching unauthorized destinations.

---

### 🧨 Command Injection — RECOMENDAÇÃO / RECOMMENDATION

## 🇧🇷 PT-BR
Para evitar **Command Injection**, não execute comandos do sistema com entrada controlada pelo usuário. Quando a execução for inevitável, utilize APIs seguras (sem shell), parâmetros estritamente controlados e validação por allowlist. Execute o processo com privilégios mínimos, isole a execução (containers/sandbox quando possível) e registre eventos de forma segura. Além disso, revise fluxos que chamam ferramentas externas e mantenha dependências atualizadas.

## 🇺🇸 EN
To prevent **Command Injection**, avoid executing OS commands with user-controlled input. When execution is unavoidable, use safe APIs (no shell), strictly controlled parameters, and allowlist-based validation. Run the process with minimal privileges, isolate execution (containers/sandbox where possible), and log events safely. Also review flows that invoke external tools and keep dependencies up to date.

---

### 📂 LFI / RFI — RECOMENDAÇÃO / RECOMMENDATION

## 🇧🇷 PT-BR
Para mitigar **LFI/RFI**, evite construir caminhos de arquivos a partir de entradas não confiáveis. Use referências internas (IDs) mapeadas para recursos permitidos, aplique validação por allowlist e normalize caminhos para impedir traversal. Desabilite inclusão remota quando aplicável e mantenha permissões de arquivos restritas (somente o necessário). Monitore tentativas de acesso suspeitas e trate erros de forma controlada para não revelar caminhos internos.

## 🇺🇸 EN
To mitigate **LFI/RFI**, avoid constructing file paths from untrusted input. Use internal references (IDs) mapped to allowed resources, enforce allowlist validation, and normalize paths to prevent traversal. Disable remote inclusion where applicable and restrict file permissions to the minimum required. Monitor suspicious access attempts and handle errors in a controlled way to avoid leaking internal paths.

---

### 🧬 XXE — RECOMENDAÇÃO / RECOMMENDATION

## 🇧🇷 PT-BR
Para prevenir **XXE**, desabilite a resolução de entidades externas e DTDs no parser XML e utilize configurações seguras da biblioteca utilizada. Prefira formatos alternativos quando possível (ex.: JSON) e valide o conteúdo recebido de forma estrita. Restrinja acesso do processo a recursos locais/externos desnecessários e mantenha bibliotecas atualizadas. Registre falhas de parsing sem expor detalhes sensíveis.

## 🇺🇸 EN
To prevent **XXE**, disable external entity resolution and DTD processing in the XML parser and use secure parser settings for your library. Prefer alternative formats when possible (e.g., JSON) and validate input strictly. Restrict process access to unnecessary local/external resources and keep libraries updated. Log parsing failures without exposing sensitive details.

---

### 📦 Insecure Deserialization — RECOMENDAÇÃO / RECOMMENDATION

## 🇧🇷 PT-BR
Para reduzir riscos de **desserialização insegura**, evite desserializar dados não confiáveis e prefira formatos simples (JSON com validação de esquema) em vez de objetos complexos. Quando a desserialização for necessária, aplique validação rigorosa, controles de tipo (allowlist), integridade (assinaturas/HMAC quando aplicável) e limite permissões do processo. Mantenha bibliotecas atualizadas e monitore tentativas anômalas relacionadas a payloads inválidos.

## 🇺🇸 EN
To reduce **insecure deserialization** risk, avoid deserializing untrusted data and prefer simple formats (schema-validated JSON) over complex objects. When deserialization is required, enforce strict validation, type controls (allowlist), integrity protection (signatures/HMAC when applicable), and least-privilege execution. Keep libraries updated and monitor abnormal attempts involving invalid payloads.

---

### 🧩 SSTI — RECOMENDAÇÃO / RECOMMENDATION

## 🇧🇷 PT-BR
Para mitigar **SSTI**, nunca trate dados do usuário como template. Separe claramente dados e lógica, use renderização segura por padrão e restrinja capacidades do engine (desativar recursos perigosos quando possível). Valide e sanitize entradas conforme contexto e evite avaliar expressões dinâmicas oriundas de fontes externas. Inclua testes de segurança específicos para templates e revise componentes que renderizam conteúdo no servidor.

## 🇺🇸 EN
To mitigate **SSTI**, never treat user input as template code. Clearly separate data and logic, use safe-by-default rendering, and restrict template engine capabilities (disable dangerous features where possible). Validate and sanitize input based on context and avoid evaluating dynamic expressions from external sources. Add template-focused security tests and review server-side rendering components.

---

