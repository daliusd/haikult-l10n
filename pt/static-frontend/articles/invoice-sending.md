---
title: 'Enviar Faturas'
date: '2021-04-15'
modified: '2026-03-28'
---

Depois de criar uma fatura, precisa de a entregar ao comprador. Um método conveniente é enviar o PDF por email, e o Haiku.lt pode ajudar com isto.

O Haiku.lt suporta duas formas de enviar emails:

## 1. Escolher um Método de Envio de Email

### Gmail (OAuth)

Se iniciou sessão com o Google, o Haiku.lt pode enviar emails diretamente
da sua conta Gmail usando OAuth seguro — não é necessário partilhar a palavra-passe.
Ao iniciar sessão, deve conceder permissão para enviar emails em seu nome.
Se não fez isto inicialmente, termine sessão e inicie sessão novamente.

### SMTP

Também pode enviar emails através de qualquer servidor SMTP. Isto funciona com qualquer
fornecedor de email e é a única opção para utilizadores que não usam Gmail.

Para configurar SMTP, aceda a [Configurações → Configurações do fornecedor de email](/app/settings/email-provider):

1. Se usa o login do Gmail, selecione **SMTP** como método de envio.
2. Escolha uma **predefinição de fornecedor** para preencher automaticamente as configurações do servidor:
   - Gmail, Yahoo Mail, Outlook/Hotmail, Office 365, SendGrid, Mailgun ou Personalizado
3. Preencha os detalhes SMTP:
   - **Host** — endereço do servidor SMTP (por ex., `smtp.gmail.com`)
   - **Porta** — tipicamente 587 (STARTTLS) ou 465 (SSL/TLS)
   - **Segurança** — STARTTLS atualiza uma ligação não cifrada para cifrada; SSL/TLS está cifrado desde o início
   - **Nome de utilizador** — o seu endereço de email
   - **Palavra-passe** — a sua palavra-passe de email ou palavra-passe específica da aplicação
   - **Endereço de remetente** — o endereço do remetente mostrado aos destinatários (por ex., `Nome da empresa <você@example.com>`)
4. Clique em **Testar ligação** para verificar as suas configurações antes de guardar.
5. Clique em **Guardar configurações SMTP**.

## 2. Configurações de Email

Em [Configurações](/app/settings) pode configurar:

### Assunto do Email

Personalize a linha de assunto do email para se adequar às suas necessidades. Pode usar estas variáveis:
- `{{invoiceNo}}` - número da fatura (por exemplo, INV/001)
- `{{buyer}}` - nome do comprador
- `{{seller}}` - nome do vendedor
- `{{price}}` - valor da fatura com moeda
- `{{invoiceDate}}` - data da fatura

### Modelos de Email

Escolha entre estes modelos:

**Texto simples** - formato de texto simples que funciona perfeitamente em todos os clientes de email.

**HTML simples** - email lindamente formatado em HTML usando tecnologia [MJML](https://mjml.io/).

**Com logótipo** - modelo HTML com o logótipo da sua empresa no topo.

**Com logótipo e preço** - adicionalmente exibe o valor da fatura no email.

**Com logótipo, preço e informação adicional** - também exibe informação adicional.

**Com logótipo, preço e nota de email** - inclui uma nota opcional que pode escrever antes de enviar.

**Com linhas de artigo** - apresenta uma tabela completa das linhas da fatura (nome, quantidade, preço unitário, total) juntamente com o total geral.

Os modelos HTML usam o formato [MJML](https://mjml.io/), que assegura que os emails têm ótimo aspeto em todos os clientes de email. Se quiser criar o seu próprio modelo ou modificar um existente, pode pedir ajuda à IA - descreva apenas como quer que o seu email se apresente, e a IA pode gerar o código MJML para si.

### Variáveis de Modelo

Em todos os modelos pode usar estes valores:

**Informação básica:**
- `{{issuer}}` - pessoa que criou a fatura
- `{{invoiceNo}}` - número da fatura
- `{{buyer}}` - comprador
- `{{seller}}` - vendedor
- `{{price}}` - valor da fatura
- `{{extra}}` - informação adicional
- `{{userNote}}` - a sua nota
- `{{emailNote}}` - nota no email (inserida durante o envio)
- `{{email}}` - email do comprador

**Datas:**
- `{{invoiceDate}}` - data da fatura
- `{{created}}` - data de criação da fatura (igual a invoiceDate)

**Detalhes da fatura:**
- `{{seriesName}}` - nome da série da fatura (por exemplo, "INV")
- `{{seriesId}}` - número na série (por exemplo, "001")
- `{{language}}` - idioma da fatura ("lt" ou "en")

**Logótipo:**
- `{{logoUrl}}` - URL do logótipo

**Cores da marca:**
- `{{brandPrimary}}` - cor primária
- `{{brandSecondary}}` - cor secundária
- `{{brandText}}` - cor do texto
- `{{brandTextSecondary}}` - cor do texto secundária
- `{{brandBackground}}` - cor de fundo
- `{{bodyBackground}}` - cor de fundo da página
- `{{backgroundSecondary}}` - cor de fundo secundária

### Linhas de Artigo

Pode iterar sobre as linhas da fatura usando Handlebars `{{#each lineItems}}`:

```
{{#each lineItems}}
  {{name}} — {{amount}} {{unitSymbol}} × {{unitPrice}} = {{formattedPrice}}
{{/each}}
```

Cada linha de artigo expõe:
- `{{name}}` - nome do artigo
- `{{amount}}` - quantidade
- `{{unit}}` - código de unidade UN/ECE em bruto (por ex., `H87`)
- `{{unitName}}` - forma longa da unidade, localizada (por ex., "peça", "quilograma")
- `{{unitSymbol}}` - forma curta da unidade, localizada (por ex., "pç", "kg")
- `{{unitPrice}}` - preço formatado por unidade (por ex., "€10,00")
- `{{formattedPrice}}` - total da linha formatado — quantidade × preço unitário (por ex., "€30,00")
- `{{vat}}` - percentagem de IVA (se definida)
- `{{vatcode}}` - código de IVA (se definido)

### Modelos Condicionais

Pode usar condições Handlebars para mostrar conteúdo apenas quando um valor existe:

```
{{#if extra}}
  <mj-text>Informação adicional: {{extra}}</mj-text>
{{/if}}
```

Isto é especialmente útil quando quer exibir um bloco de informação adicional apenas quando está realmente preenchido.

### Cores da Marca e Logótipo

Nas configurações também pode:
- Carregar o seu logótipo
- Alterar cores da marca

## 3. Enviar a Fatura

1. Especifique o endereço de email do comprador na fatura
2. Clique no botão "Enviar fatura"
3. A fatura será marcada como bloqueada e enviada

A fatura será enviada da sua conta Gmail usando o modelo selecionado.
