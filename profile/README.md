# Assinafy

**Assinatura eletrônica de documentos no Brasil.** API REST, SDKs oficiais em oito linguagens e
integrações prontas — com verificação por e-mail, WhatsApp ou certificado digital ICP-Brasil (A1/A3),
trilha de atividades e verificação pública de documentos assinados.

*Brazilian e-signature platform: REST API, official SDKs in eight languages and ready-made
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
| Rust | [`assinafy`](https://github.com/assinafy/rust-sdk) | `assinafy = "2"` |

Todos autenticam por **chave de API** (`X-Api-Key`, recomendado para back-end) ou **token bearer**, e
trazem paginação, tratamento de erros tipado e verificação de assinatura de webhook.

## Mobile e front-end

| | |
| --- | --- |
| [Android SDK](https://github.com/assinafy/mobile-android-sdk) | `com.assinafy:assinafy-android-sdk` |
| [iOS SDK](https://github.com/assinafy/mobile-ios-sdk) | Swift Package Manager |
| [Chat SDK](https://github.com/assinafy/chat-sdk) | `@assinafy/chat-sdk` — fluxo de assinatura conversacional |
| [Webforms Java Client](https://github.com/assinafy/webforms-java-client) | `com.assinafy:webforms-java-client-sdk` |

## Ferramentas e integrações

| | |
| --- | --- |
| [CLI](https://github.com/assinafy/assinafy-cli) | `npm install -g @assinafy/cli` — envie e acompanhe documentos pelo terminal |
| [MCP Server](https://github.com/assinafy/mcp-server) | 11 ferramentas para 24 operações de documentos em clientes MCP (Claude, Cursor, Claude Code) |
| [n8n](https://github.com/assinafy/n8n-nodes-assinafy) | `@assinafy/n8n-nodes-assinafy` — nó community para automações |
| [Activepieces](https://github.com/assinafy/activepieces) | `@assinafy/piece-assinafy` — peça para fluxos de automação: envio para assinatura, modelos, download do PDF assinado e gatilhos de eventos |
| [Zapier](https://zapier.com/developer/public-invite/242555/06c5413fab63d00faf00e0063347cd51/) | Convite para o app no Zapier — gatilhos de documentos (polling e webhook), envio para assinatura, signatários, modelos, tags e download dos artefatos |
| [Make](https://www.make.com/en/hq/app-invitation/86d76b80a1f6819b60cadeeb01895adc) | Convite para o app no Make.com — cenários de automação com a Assinafy |
| [Pluga](https://github.com/assinafy/pluga-webhooks) | Guia de integração via Pluga Webhooks + HTTP Request: eventos de assinatura, documentos, signatários e modelos — configuração manual, sem conector nativo |
| [HubSpot](https://hubspot.assinafy.com.br/) | App para o HubSpot, instalado por um Super Admin: envio para assinatura de modelos ou PDFs dos registros do CRM, por e-mail ou certificado digital (A1/A3), com o custo em créditos confirmado antes do envio e acompanhamento no card da Assinafy em contatos, empresas e negócios |
| [WordPress](https://github.com/assinafy/wordpress-plugin) | Plugin para WordPress |
| [LibreOffice](https://github.com/assinafy/libreoffice-extension) | Extensão `.oxt` para Writer, Calc, Impress e Draw |
| [Twenty CRM](https://github.com/assinafy/twenty-crm-app) | `@assinafy/twenty-app` — app para o marketplace do Twenty: envio para assinatura de PDFs anexados aos registros e de modelos, com o custo exibido e confirmado antes do envio, acompanhamento das assinaturas no Twenty (sincronização de status em segundo plano e PDF assinado salvo no registro), ação de workflow e ferramentas para o chat de IA |

## Métodos de verificação do signatário

Definidos por signatário em `signers[].verification_method` ao criar o assignment:

| Método | Como funciona | Custo por signatário |
| --- | --- | --- |
| `Email` *(padrão)* | Código de uso único (OTP) enviado por e-mail, exigido antes de assinar | Gratuito |
| `Whatsapp` | Código de uso único (OTP) enviado por WhatsApp | Gratuito¹ |
| `DigitalCertificate` | O signatário assina com o **próprio certificado ICP-Brasil (A1/A3)**, do dispositivo dele, pela extensão de navegador Web PKI — produzindo uma assinatura **PAdES qualificada** no documento | 2 créditos |

¹ A verificação é gratuita; a *notificação* por WhatsApp custa 0,45 crédito e está disponível apenas
em planos pagos.

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
- **Verificação pública** — `GET /v1/{documentSignatureHash}/verify` confere um documento assinado
  pelo hash da assinatura, sem autenticação.

## Autenticação

| Esquema | Header | Uso |
| --- | --- | --- |
| `apiKeyAuth` | `X-Api-Key: <chave>` | Chave permanente — recomendada para integrações de back-end |
| `bearerAuth` | `Authorization: Bearer <jwt>` | Token de acesso obtido pelas APIs de login |
| `signerAccessCode` | `?signer-access-code=<código>` | Código de uso único, para os endpoints voltados ao signatário |

Produção: `https://api.assinafy.com.br` · Sandbox: `https://sandbox.assinafy.com.br`

## Estimativa de custo

Antes de disparar as assinaturas, `POST /v1/documents/{id}/assignments/estimate-cost` devolve o custo
em créditos com o detalhamento por item — documento extra, notificação por WhatsApp, assinatura por
certificado digital. Há o equivalente para templates em
`POST /v1/accounts/{accountId}/templates/{templateId}/documents/estimate-cost`.

---

<a name="english"></a>

## English

**Assinafy is a Brazilian e-signature platform.** A REST API, official SDKs in eight languages
(TypeScript, Python, Go, Java, .NET, PHP, Ruby, Rust), mobile SDKs for Android and iOS, a CLI, an MCP
server, an n8n community node, apps for
[Zapier](https://zapier.com/developer/public-invite/242555/06c5413fab63d00faf00e0063347cd51/),
[Make](https://www.make.com/en/hq/app-invitation/86d76b80a1f6819b60cadeeb01895adc) and
[HubSpot](https://hubspot.assinafy.com.br/), an
[Activepieces piece](https://github.com/assinafy/activepieces)
(`@assinafy/piece-assinafy`), a [WordPress plugin](https://github.com/assinafy/wordpress-plugin), a
[LibreOffice extension](https://github.com/assinafy/libreoffice-extension), a
[Pluga Webhooks + HTTP Request guide](https://github.com/assinafy/pluga-webhooks) for manual integration
and a [Twenty CRM app](https://github.com/assinafy/twenty-crm-app) (`@assinafy/twenty-app`).

Signer identity is verified by **email OTP**, **WhatsApp OTP**, or the signer's own **ICP-Brasil A1/A3
digital certificate** via the Web PKI browser extension — the last producing a qualified PAdES
signature. Every document carries a full activity trail (each event with its payload snapshot and
request origin), downloadable artifacts including the PAdES and certification-page PDFs, and public
hash-based verification.

Authenticate with an `X-Api-Key` header (recommended for back-ends) or a bearer JWT. A free sandbox at
`https://sandbox.assinafy.com.br` mirrors production for end-to-end integration testing.

Start with the [API documentation](https://api.assinafy.com.br/v1/docs).

---

Todos os SDKs e integrações oficiais são distribuídos sob a licença **MIT**.
