# Assinafy

**Assinatura eletrônica de documentos no Brasil.** API REST, SDKs oficiais em nove linguagens e
integrações prontas — com verificação por e-mail, WhatsApp, biometria facial com documento de identidade
e prova de vida, ou certificado digital ICP-Brasil (A1/A3), trilha de atividades e verificação pública
de documentos assinados.

*Brazilian e-signature platform with facial biometrics, identity-document verification, liveness
checks and ICP-Brasil digital certificates. REST API, official SDKs in nine languages and ready-made
integrations. [English version](#english).*

[Site](https://www.assinafy.com.br) · [Documentação da API](https://api.assinafy.com.br/v1/docs) · [Sandbox](https://sandbox.assinafy.com.br)

---

## SDKs oficiais

| Linguagem | Pacote | Instalação |
| --- | --- | --- |
| TypeScript / Node.js | [`@assinafy/sdk`](https://github.com/assinafy/typescript-sdk) | `npm install @assinafy/sdk` |
| Python | [`assinafy`](https://github.com/assinafy/python-sdk) | `pip install assinafy` |
| Go | [`assinafy/golang-sdk`](https://github.com/assinafy/golang-sdk) | `go get github.com/assinafy/golang-sdk` |
| Java | [`com.assinafy:assinafy-sdk`](https://github.com/assinafy/java-sdk) | Maven / Gradle |
| .NET | [`Assinafy.Sdk`](https://github.com/assinafy/csharp-sdk) | `dotnet add package Assinafy.Sdk` |
| PHP | [`assinafy/php-sdk`](https://github.com/assinafy/php-sdk) | `composer require assinafy/php-sdk` |
| Ruby | [`assinafy`](https://github.com/assinafy/ruby-sdk) | `gem 'assinafy'` |
| Rust | [`assinafy`](https://github.com/assinafy/rust-sdk) | `assinafy = "3"` |
| Object Pascal | [`assinafy/object-pascal-sdk`](https://github.com/assinafy/object-pascal-sdk) | Clone o repositório e adicione `src` aos unit paths (Free Pascal / Lazarus) |

Todos autenticam por **chave de API** (`X-Api-Key`, recomendado para back-end), **token bearer** ou
**OAuth 2.1**, e trazem paginação, tratamento de erros tipado e verificação de assinatura de webhook.

## Mobile e front-end

| | |
| --- | --- |
| [Android SDK](https://github.com/assinafy/mobile-android-sdk) | `com.assinafy:assinafy-android-sdk` |
| [iOS SDK](https://github.com/assinafy/mobile-ios-sdk) | Swift Package Manager |
| [Chat SDK](https://github.com/assinafy/chat-sdk) | `@assinafy/chat-sdk` — fluxo de assinatura conversacional |
| [Webforms Java Client](https://github.com/assinafy/webforms-java-client) | `com.assinafy:webforms-java-client-sdk` |

## Ferramentas e apps

| | |
| --- | --- |
| [CLI](https://github.com/assinafy/assinafy-cli) | `npm install -g @assinafy/cli` — envie e acompanhe documentos pelo terminal |
| [MCP Server](https://github.com/assinafy/mcp-server) | `https://mcp.assinafy.com.br/mcp` — 27 ferramentas de documentos, com login OAuth 2.1 no workspace, em Claude, ChatGPT, Codex e VS Code |
| [Plugin para assistentes de IA](https://github.com/assinafy/agent-plugin) | Plugin para Claude (Claude Code, apps e Cowork), Codex e ChatGPT, e VS Code com GitHub Copilot: conecta o servidor MCP e traz uma skill com o fluxo completo de assinatura |
| [HubSpot](https://hubspot.assinafy.com.br/) | App para o HubSpot, configurado por um Super Admin: envio de modelos ou PDFs com verificação por código ou certificado ICP-Brasil (A1/A3), convite por e-mail ou WhatsApp e custo confirmado antes do envio. Acompanhamento no card de contatos, empresas, negócios e tickets, e envio de modelos por workflows com limite de créditos |
| [WordPress e WooCommerce](https://github.com/assinafy/wordpress-plugin) | Plugin para WordPress, [publicado no diretório oficial](https://wordpress.org/plugins/assinafy/). No WooCommerce, o pedido concluído envia o contrato do produto para assinatura do comprador e coloca o link de assinatura no e-mail do pedido |
| [LibreOffice](https://github.com/assinafy/libreoffice-extension) | Extensão `.oxt` para Writer, Calc, Impress e Draw |
| [Twenty CRM](https://github.com/assinafy/twenty-crm-app) | `@assinafy/twenty-app` — envio de PDFs anexados e modelos com verificação por e-mail, WhatsApp, biometria ou certificado ICP-Brasil. Custo confirmado antes do envio, status atualizado por webhooks e sincronização em segundo plano, PDFs assinados salvos no registro, ação de workflow e ferramentas para o chat de IA |

## Automação (iPaaS)

| | |
| --- | --- |
| [n8n](https://github.com/assinafy/n8n-nodes-assinafy) | `@assinafy/n8n-nodes-assinafy` — nó community para automações |
| [Activepieces](https://github.com/assinafy/activepieces) | `@assinafy/piece-assinafy` — peça para fluxos de automação: envio para assinatura, modelos, download do PDF assinado e gatilhos de eventos |
| [Zapier](https://zapier.com/developer/public-invite/242555/06c5413fab63d00faf00e0063347cd51/) | Convite para o app no Zapier — gatilhos de documentos (polling e webhook), envio para assinatura, signatários, modelos, tags e download dos artefatos |
| [Make](https://www.make.com/en/hq/app-invitation/86d76b80a1f6819b60cadeeb01895adc) | Convite para o app no Make.com — cenários de automação com a Assinafy |
| [viaSocket](https://viasocket.com/integrations/assinafy) | Integração da Assinafy no viaSocket para fluxos de automação |
| [Integrately](https://integrately.com/integrations/assinafy) | Integração da Assinafy no Integrately para fluxos de automação |
| [OttoKit](https://ottokit.com/integrations/assinafy) | Integração da Assinafy no OttoKit para fluxos de automação |
| [FlowRunner](https://flowrunner.ai/integrations/assinafy) | Integração da Assinafy no FlowRunner para fluxos de automação |
| [Pluga](https://github.com/assinafy/pluga-webhooks) | Guia de integração via Pluga Webhooks + HTTP Request: eventos de assinatura, documentos, signatários e modelos — configuração manual, sem conector nativo |

## Métodos de verificação do signatário

Definidos por signatário em `signers[].verification_method` ao criar o assignment ou atribuir os
papéis de um template:

| Método | Como funciona | Notificação permitida | Custo por signatário |
| --- | --- | --- | --- |
| `Email` *(padrão)* | Código de uso único (OTP) enviado por e-mail, exigido antes de assinar | `Email` | Gratuito |
| `Whatsapp` | Código de uso único (OTP) enviado por WhatsApp | `Whatsapp` | 0,45 crédito pela notificação; verificação gratuita |
| `DigitalCertificate` | O signatário assina com o **próprio certificado ICP-Brasil (A1/A3)** pela extensão Web PKI, produzindo uma assinatura **PAdES qualificada** | `Email` ou `Whatsapp` | 0,5 crédito + notificação |
| `IdDocumentFaceMatchBasic` | Documento de identidade, foto do signatário segurando o documento, comparação facial e prova de vida em sessão hospedada | `Email` ou `Whatsapp` | Tarifa por signatário + notificação; consulte a estimativa |

A notificação por WhatsApp está disponível apenas em planos pagos. O custo da biometria depende
da conta e da assinatura contratada; consulte a estimativa antes do envio.

Cada solicitação de assinatura usa um documento da franquia do plano; quando a franquia acaba, o
documento extra custa 1 crédito.

O método de verificação e o de notificação são **acoplados**: envie um, os dois ou nenhum — o lado
que faltar é inferido. Sem nenhum dos dois, ambos assumem `Email`.
`signers[].notification_methods` aceita **exatamente um canal** por signatário, em um array com um
elemento, conforme a tabela; combinações incompatíveis retornam `400`.

### Biometria facial e documento de identidade

`IdDocumentFaceMatchBasic` exige o recurso **ID Document + Face Match** habilitado na conta e um
**CPF válido** em `government_id` do signatário. O signatário dá consentimento explícito para o
tratamento biométrico e conclui a captura de documento, foto e prova de vida no fluxo hospedado
pela Assinafy.

Para integrar uma experiência própria, `GET /v1/signers/identity-verification` informa o estado e
`can_start`; `POST` na mesma rota, com `{"consent": true}`, inicia a sessão e devolve a URL de
captura. Ambas usam `signer-access-code`. Abra a URL completa, incluindo o fragmento, sem registrá-la
em logs nem armazená-la no navegador. Inicie a sessão somente após o consentimento e quando
`can_start` for verdadeiro.

Quando a verificação fica `InReview`, o signatário pode confirmar os dados e assinar enquanto a
conta analisa a identidade. Depois de todas as assinaturas, `pending_identity_review` indica que a
certificação aguarda a aprovação de todas as revisões. A conta consulta a revisão em
`GET /v1/documents/{documentId}/assignments/{assignmentId}/signers/{signerId}/identity-verification`
e decide com `POST` na mesma rota acrescida de `/review`, usando `decision: Approved` ou `Rejected`.
As imagens de evidência só ficam disponíveis durante a revisão. Uma rejeição cancela o documento
e notifica signatários e destinatários de cópia.

### Certificado digital ICP-Brasil

`DigitalCertificate` exige o recurso **Certificado Digital** (planos Standard e Pro), CPF ou CNPJ em
`government_id`, e que o signatário esteja **sozinho no seu passo de assinatura**. Um CPF exige o
certificado daquela pessoa (e-CPF, ou e-CNPJ que a nomeie como representante legal); um CNPJ exige um
e-CNPJ da empresa.

A assinatura é concluída no fluxo hospedado pela Assinafy, com a extensão Web PKI e o certificado
no dispositivo do signatário. O handshake de certificado usa rotas internas, fora do contrato
OpenAPI público; o endpoint comum de assinatura não substitui esse fluxo.

## Trilha de atividades e evidências

- **`GET /v1/documents/{id}/activities`** — todos os eventos registrados do documento, cada um com um
  snapshot do `payload` do evento e a `origin` da requisição (`ip`, `user-agent`).
- **Artefatos** em `GET /v1/documents/{id}/download/{artifactName}`:
  `original`, `certificated`, `certificate-page`, `pades` e `bundle` (zip com todos).
  O artefato `pades` — assinaturas ICP-Brasil dos signatários mais a caixa de certificação da
  plataforma — existe apenas em documentos que tiveram signatários por certificado digital.
- **Verificação pública** — `GET /v1/documents/{documentSignatureHash}/verify` confere um documento assinado
  pelo hash da assinatura, sem autenticação.

## Autenticação

| Esquema | Header | Uso |
| --- | --- | --- |
| `apiKeyAuth` | `X-Api-Key: <chave>` | Chave permanente — recomendada para integrações de back-end |
| `bearerAuth` | `Authorization: Bearer <jwt>` | Token de acesso obtido pelas APIs de login |
| `oauth2` | `Authorization: Bearer <token OAuth>` | OAuth 2.1 com PKCE (S256) para apps e assistentes de IA que agem no workspace de outra pessoa, com as permissões que ela aprovou — veja o *OAuth Integration Guide* na documentação |
| `signerAccessCode` | `?signer-access-code=<código>` | Código de acesso à sessão, para os endpoints voltados ao signatário |

Produção: `https://api.assinafy.com.br` · Sandbox: `https://sandbox.assinafy.com.br`

## Webhooks

Cada conta registra **1 endpoint de webhook**, ou **até 3** nos planos pagos, cada um com URL, lista de
eventos e assinatura próprias. Com `signing_enabled`, as entregas seguem o padrão
[Standard Webhooks](https://www.standardwebhooks.com): cabeçalhos `webhook-id`, `webhook-timestamp` e
`webhook-signature` (HMAC-SHA256 com o segredo `whsec_` do endpoint, que pode ser rotacionado).

Acompanhe a identidade com `signer_identity_verified`, `signer_identity_verification_failed`,
`signer_identity_review_required`, `signer_identity_review_approved` e `signer_identity_review_rejected`.
Para baixar os arquivos finais, aguarde `document_ready` e o status `certificated`; todas as
assinaturas presentes ainda podem deixar o documento aguardando revisão de identidade.

## Estimativa de custo

Antes de disparar as assinaturas, `POST /v1/documents/{id}/assignments/estimate-cost` devolve o custo
em créditos com o detalhamento por item — documento extra, notificação por WhatsApp, assinatura por
certificado digital e verificação biométrica. Há o equivalente para templates em
`POST /v1/accounts/{accountId}/templates/{templateId}/documents/estimate-cost`. As duas estimativas
aceitam `IdDocumentFaceMatchBasic`; a tarifa biométrica é cobrada por signatário na criação do
assignment, além da notificação. As estimativas não reservam créditos.

---

<a name="english"></a>

## English

**Assinafy is a Brazilian e-signature platform.** A REST API, official SDKs in nine languages
(TypeScript, Python, Go, Java, .NET, PHP, Ruby, Rust, Object Pascal) and mobile SDKs for Android and iOS.

### Tools and apps

| | |
| --- | --- |
| [CLI](https://github.com/assinafy/assinafy-cli) | `npm install -g @assinafy/cli` — send and track documents from the terminal |
| [MCP Server](https://github.com/assinafy/mcp-server) | `https://mcp.assinafy.com.br/mcp` — 27 document tools, with OAuth 2.1 workspace login, in Claude, ChatGPT, Codex and VS Code |
| [AI assistant plugin](https://github.com/assinafy/agent-plugin) | Plugin for Claude (Claude Code, apps and Cowork), Codex and ChatGPT, and VS Code with GitHub Copilot: connects the MCP server and ships a skill with the full signing flow |
| [HubSpot](https://hubspot.assinafy.com.br/) | HubSpot app, configured by a Super Admin: send templates or PDFs with code verification or ICP-Brasil A1/A3 certificates, email or WhatsApp invitations, and cost confirmation before sending. Track documents on contact, company, deal and ticket cards; send templates from workflows with a credit limit |
| [WordPress and WooCommerce](https://github.com/assinafy/wordpress-plugin) | WordPress plugin, [published in the official directory](https://wordpress.org/plugins/assinafy/). In WooCommerce, a completed order sends the product's contract to the buyer for signature and adds the signing link to the order email |
| [LibreOffice](https://github.com/assinafy/libreoffice-extension) | `.oxt` extension for Writer, Calc, Impress and Draw |
| [Twenty CRM](https://github.com/assinafy/twenty-crm-app) | `@assinafy/twenty-app` — send attached PDFs and templates with email, WhatsApp, biometric or ICP-Brasil certificate verification. Confirm costs before sending, track status through webhooks and background sync, save signed PDFs to the record, and use a workflow action and AI chat tools |

### Automation (iPaaS)

| | |
| --- | --- |
| [n8n](https://github.com/assinafy/n8n-nodes-assinafy) | `@assinafy/n8n-nodes-assinafy` — community node for automations |
| [Activepieces](https://github.com/assinafy/activepieces) | `@assinafy/piece-assinafy` — piece for automation flows: sending for signature, templates, signed PDF download and event triggers |
| [Zapier](https://zapier.com/developer/public-invite/242555/06c5413fab63d00faf00e0063347cd51/) | Invite to the Zapier app — document triggers (polling and webhook), sending for signature, signers, templates, tags and artifact downloads |
| [Make](https://www.make.com/en/hq/app-invitation/86d76b80a1f6819b60cadeeb01895adc) | Invite to the Make.com app — automation scenarios with Assinafy |
| [viaSocket](https://viasocket.com/integrations/assinafy) | Assinafy integration on viaSocket for automation flows |
| [Integrately](https://integrately.com/integrations/assinafy) | Assinafy integration on Integrately for automation flows |
| [OttoKit](https://ottokit.com/integrations/assinafy) | Assinafy integration on OttoKit for automation flows |
| [FlowRunner](https://flowrunner.ai/integrations/assinafy) | Assinafy integration on FlowRunner for automation flows |
| [Pluga](https://github.com/assinafy/pluga-webhooks) | Integration guide via Pluga Webhooks + HTTP Request: signature, document, signer and template events — manual setup, no native connector |

### Signer verification and biometrics

Signer identity is verified by **email OTP**, **WhatsApp OTP**, **identity-document verification with
facial matching and liveness**, or the signer's own **ICP-Brasil A1/A3 digital certificate** via the
Web PKI browser extension. Digital certificates produce a qualified PAdES signature and each
certificate signer must be alone in their signing step.

Biometrics use `IdDocumentFaceMatchBasic` when assigning signers to documents or template roles.
The account needs the **ID Document + Face Match** feature, and the signer needs a valid CPF in
`government_id`. The signer explicitly consents to biometric processing and completes document
photos, a photo holding the document and a liveness check in Assinafy's hosted flow.

For a custom signing experience, `GET /v1/signers/identity-verification` returns the status and
`can_start`; `POST` to the same path with `{"consent": true}` starts a session after consent. Both
use the signer access code. Open the returned capture URL unchanged, including its fragment;
never log it or store it in the browser. Start only when `can_start` is true.

Each signer has exactly one notification channel: `Email` verification uses `Email`, `Whatsapp`
uses `Whatsapp`, and certificates and biometrics allow either. WhatsApp notifications require a
paid plan. Biometrics carry a per-signer fee in addition to the notification, charged when the
assignment is created. Estimate the account's cost before sending with
`POST /v1/documents/{id}/assignments/estimate-cost` or
`POST /v1/accounts/{accountId}/templates/{templateId}/documents/estimate-cost`.

During `InReview`, signers can continue signing while the account reviews their identity. Once
everyone has signed, `pending_identity_review` holds certification until every review is approved.
The account reads the review at
`GET /v1/documents/{documentId}/assignments/{assignmentId}/signers/{signerId}/identity-verification`
and posts `decision: Approved` or `Rejected` to the same path with `/review` appended. Evidence
images are available only while the review is open. Rejecting a review cancels the document and
notifies signers and copy recipients.

Identity webhooks report verification success or failure and reviews required, approved or
rejected. Wait for `document_ready` and `certificated` before downloading final files. Documents
have an activity trail with event payloads and request origins, downloadable signed and
certification-page PDFs, and public hash-based verification. The `pades` artifact is available
only for documents signed with digital certificates.

Authenticate with an `X-Api-Key` header (recommended for back-ends), a bearer JWT, or OAuth 2.1 with
PKCE for apps and AI assistants acting in another user's workspace. Webhooks support up to 3 endpoints
on paid plans, with Standard Webhooks signatures. A free sandbox at
`https://sandbox.assinafy.com.br` supports integration testing. Certificate signing is completed
in Assinafy's hosted flow; its internal handshake is outside the public OpenAPI contract.

Start with the [API documentation](https://api.assinafy.com.br/v1/docs).

---

Os SDKs oficiais são distribuídos sob a licença **MIT**. Consulte a licença de cada integração
no respectivo repositório; o plugin WordPress usa **GPL-2.0-or-later**.
