# Assinafy

**Assinatura eletrônica de documentos no Brasil.** API REST, SDKs oficiais em nove linguagens e
integrações prontas — com verificação por e-mail, WhatsApp ou certificado digital ICP-Brasil (A1/A3),
trilha de atividades e verificação pública de documentos assinados.

*Brazilian e-signature platform: REST API, official SDKs in nine languages and ready-made
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
| [MCP Server](https://github.com/assinafy/mcp-server) | `https://mcp.assinafy.com.br/mcp` — 14 ferramentas para 27 operações de documentos, com login OAuth 2.1 no workspace, em Claude, ChatGPT, Codex e VS Code |
| [Plugin para assistentes de IA](https://github.com/assinafy/agent-plugin) | Plugin para Claude (Claude Code, apps e Cowork), Codex e ChatGPT, e VS Code com GitHub Copilot: conecta o servidor MCP e traz uma skill com o fluxo completo de assinatura |
| [HubSpot](https://hubspot.assinafy.com.br/) | App para o HubSpot, instalado por um Super Admin: envio para assinatura de modelos ou PDFs dos registros do CRM, por e-mail ou certificado digital (A1/A3), com o custo em créditos confirmado antes do envio e acompanhamento no card da Assinafy em contatos, empresas e negócios |
| [WordPress e WooCommerce](https://github.com/assinafy/wordpress-plugin) | Plugin para WordPress, [publicado no diretório oficial](https://wordpress.org/plugins/assinafy/). No WooCommerce, o pedido concluído envia o contrato do produto para assinatura do comprador e coloca o link de assinatura no e-mail do pedido |
| [LibreOffice](https://github.com/assinafy/libreoffice-extension) | Extensão `.oxt` para Writer, Calc, Impress e Draw |
| [Twenty CRM](https://github.com/assinafy/twenty-crm-app) | `@assinafy/twenty-app` — app para o marketplace do Twenty: envio para assinatura de PDFs anexados aos registros e de modelos, com o custo exibido e confirmado antes do envio, acompanhamento das assinaturas no Twenty (sincronização de status em segundo plano e PDF assinado salvo no registro), ação de workflow e ferramentas para o chat de IA |

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

Definidos por signatário em `signers[].verification_method` ao criar o assignment:

| Método | Como funciona | Custo por signatário |
| --- | --- | --- |
| `Email` *(padrão)* | Código de uso único (OTP) enviado por e-mail, exigido antes de assinar | Gratuito |
| `Whatsapp` | Código de uso único (OTP) enviado por WhatsApp | Gratuito¹ |
| `DigitalCertificate` | O signatário assina com o **próprio certificado ICP-Brasil (A1/A3)**, do dispositivo dele, pela extensão de navegador Web PKI — produzindo uma assinatura **PAdES qualificada** no documento | 0,5 crédito + notificação |

¹ A verificação é gratuita; a *notificação* por WhatsApp custa 0,45 crédito e está disponível apenas
em planos pagos.

Cada solicitação de assinatura usa um documento da franquia do plano; quando a franquia acaba, o
documento extra custa 1 crédito.

O método de verificação e o de notificação são **acoplados**: envie um, os dois ou nenhum — o lado
que faltar é inferido. Sem nenhum dos dois, ambos assumem `Email`.

### Certificado digital ICP-Brasil

`DigitalCertificate` exige o recurso **Certificado Digital** (planos Standard e Pro), CPF ou CNPJ em
`government_id`, e que o signatário esteja **sozinho no seu passo de assinatura**. Um CPF exige o
certificado daquela pessoa (e-CPF, ou e-CNPJ que a nomeie como representante legal); um CNPJ exige um
e-CNPJ da empresa.

A assinatura em si é um handshake de dois passos com a extensão Web PKI, não um envio de campos:

```
POST /v1/signers/certificate/start     → data.token   (token da operação Web PKI)
        ↓  o navegador assina o token com o certificado do signatário
POST /v1/signers/certificate/complete  → data.signerName
```

> Ambas as rotas são extensões implantadas **somente em produção**: o sandbox não as expõe e elas não
> constam do documento OpenAPI publicado.

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
| `signerAccessCode` | `?signer-access-code=<código>` | Código de uso único, para os endpoints voltados ao signatário |

Produção: `https://api.assinafy.com.br` · Sandbox: `https://sandbox.assinafy.com.br`

## Webhooks

Cada conta registra **1 endpoint de webhook**, ou **até 3** nos planos pagos, cada um com URL, lista de
eventos e assinatura próprias. Com `signing_enabled`, as entregas seguem o padrão
[Standard Webhooks](https://www.standardwebhooks.com): cabeçalhos `webhook-id`, `webhook-timestamp` e
`webhook-signature` (HMAC-SHA256 com o segredo `whsec_` do endpoint, que pode ser rotacionado).

## Estimativa de custo

Antes de disparar as assinaturas, `POST /v1/documents/{id}/assignments/estimate-cost` devolve o custo
em créditos com o detalhamento por item — documento extra, notificação por WhatsApp, assinatura por
certificado digital. Há o equivalente para templates em
`POST /v1/accounts/{accountId}/templates/{templateId}/documents/estimate-cost`.

---

<a name="english"></a>

## English

**Assinafy is a Brazilian e-signature platform.** A REST API, official SDKs in nine languages
(TypeScript, Python, Go, Java, .NET, PHP, Ruby, Rust, Object Pascal) and mobile SDKs for Android and iOS.

### Tools and apps

| | |
| --- | --- |
| [CLI](https://github.com/assinafy/assinafy-cli) | `npm install -g @assinafy/cli` — send and track documents from the terminal |
| [MCP Server](https://github.com/assinafy/mcp-server) | `https://mcp.assinafy.com.br/mcp` — 14 tools for 27 document operations, with OAuth 2.1 workspace login, in Claude, ChatGPT, Codex and VS Code |
| [AI assistant plugin](https://github.com/assinafy/agent-plugin) | Plugin for Claude (Claude Code, apps and Cowork), Codex and ChatGPT, and VS Code with GitHub Copilot: connects the MCP server and ships a skill with the full signing flow |
| [HubSpot](https://hubspot.assinafy.com.br/) | HubSpot app, installed by a Super Admin: send templates or PDFs from CRM records for signature by email or digital certificate (A1/A3), with the credit cost confirmed before sending and tracking on the Assinafy card on contacts, companies and deals |
| [WordPress and WooCommerce](https://github.com/assinafy/wordpress-plugin) | WordPress plugin, [published in the official directory](https://wordpress.org/plugins/assinafy/). In WooCommerce, a completed order sends the product's contract to the buyer for signature and adds the signing link to the order email |
| [LibreOffice](https://github.com/assinafy/libreoffice-extension) | `.oxt` extension for Writer, Calc, Impress and Draw |
| [Twenty CRM](https://github.com/assinafy/twenty-crm-app) | `@assinafy/twenty-app` — app for the Twenty marketplace: send attached PDFs and templates for signature with the cost shown and confirmed before sending, track signatures in Twenty (background status sync and signed PDF saved to the record), workflow action and AI chat tools |

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

Signer identity is verified by **email OTP**, **WhatsApp OTP**, or the signer's own **ICP-Brasil A1/A3
digital certificate** via the Web PKI browser extension — the last producing a qualified PAdES
signature. Every document carries a full activity trail (each event with its payload snapshot and
request origin), downloadable artifacts including the PAdES and certification-page PDFs, and public
hash-based verification.

Authenticate with an `X-Api-Key` header (recommended for back-ends), a bearer JWT, or OAuth 2.1 with
PKCE for apps and AI assistants acting in another user's workspace. Webhooks support up to 3 endpoints
on paid plans, with Standard Webhooks signatures. A free sandbox at
`https://sandbox.assinafy.com.br` supports integration testing. The signer certificate handshake
endpoints are available only in production.

Start with the [API documentation](https://api.assinafy.com.br/v1/docs).

---

Os SDKs oficiais são distribuídos sob a licença **MIT**. Consulte a licença de cada integração
no respectivo repositório; o plugin WordPress usa **GPL-2.0-or-later**.
