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
| [MCP Server](https://github.com/assinafy/mcp-server) | 13 ferramentas para assinar por linguagem natural em clientes MCP (Claude, Cursor, Claude Code) |
| [n8n](https://github.com/assinafy/n8n-nodes-assinafy) | `@assinafy/n8n-nodes-assinafy` — nó community para automações |
| [WordPress](https://github.com/assinafy/wordpress-plugin) | Plugin para WordPress |

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
server, an n8n community node and a [WordPress plugin](https://github.com/assinafy/wordpress-plugin).

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
