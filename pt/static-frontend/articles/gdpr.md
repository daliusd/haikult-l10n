---
title: 'RGPD - Os Seus Direitos sobre Dados'
date: '2025-12-28'
modified: '2026-03-27'
showDate: false
---

O Haiku.lt está comprometido em proteger os seus dados pessoais e respeitar os seus direitos de privacidade ao abrigo do Regulamento Geral sobre a Proteção de Dados (RGPD). Esta página explica os seus direitos e como tratamos os seus dados.

## Os Seus Direitos sobre Dados

Ao abrigo do RGPD, tem os seguintes direitos relativos aos seus dados pessoais:

### Direito de Acesso

Tem o direito de aceder a todos os dados pessoais que detemos sobre si. Pode exportar os seus dados a qualquer momento:

- **Exportação completa da base de dados**: Descarregue a sua base de dados completa incluindo todas as faturas, configurações e registos de auditoria das configurações da sua conta.
- **Exportação de faturas**: Exporte as suas faturas em formato CSV, filtradas por intervalo de datas e nome de série.

### Direito ao Apagamento (Direito a Ser Esquecido)

Tem o direito de solicitar a eliminação dos seus dados pessoais. Pode eliminar toda a sua conta e todos os dados associados a qualquer momento através das configurações da sua conta. Esta ação é permanente e não pode ser anulada.

### Direito à Portabilidade de Dados

Pode exportar os seus dados em formatos legíveis por máquina:

- Formato de base de dados SQLite (exportação completa de dados)
- Formato CSV (exportação de dados de faturas)

Isto permite-lhe transferir os seus dados para outro serviço se o desejar.

### Direito de Retificação

Tem o direito de corrigir dados pessoais imprecisos ou incompletos. Pode editar todos os seus dados diretamente na aplicação, incluindo:

- Detalhes de faturas
- Informação de compradores e vendedores
- As suas preferências pessoais e configurações

### Direito à Limitação do Tratamento

Tem o direito de solicitar a limitação do tratamento dos seus dados pessoais em certas circunstâncias. Contacte-nos através do email abaixo para exercer este direito.

### Direito de Oposição

Tem o direito de se opor ao tratamento dos seus dados pessoais para fins específicos. Uma vez que o Haiku.lt trata os seus dados apenas para fornecer o serviço de faturação que solicitou, opor-se ao tratamento impedir-nos-ia de fornecer o serviço.

## Conservação de Dados

Os seus dados são mantidos **até que elimine a sua conta**. Não eliminamos automaticamente contas inativas. Tem controlo total sobre quando os seus dados são removidos.

Quando elimina a sua conta, todos os seus dados são permanentemente removidos dos nossos sistemas.

## Responsável pelo Tratamento de Dados

O responsável pelo tratamento de dados do Haiku.lt é:

**Dalius Dobravolskas**

Para questões relacionadas com privacidade ou para exercer os seus direitos sobre dados, contacte:
[dalius.dobravolskas@gmail.com](mailto:dalius.dobravolskas@gmail.com)

## Localização do Servidor

Todos os servidores e armazenamento de dados do Haiku.lt estão localizados na **União Europeia, especificamente na Alemanha**. Os seus dados não saem da UE a menos que autorize explicitamente integrações de terceiros (ver Subcontratantes abaixo).

## Base Legal para o Tratamento

Tratamos os seus dados pessoais com base em:

- **Execução de contrato**: Para fornecer o serviço de faturação para o qual se inscreveu
- **Interesse legítimo**: Para manter a segurança do serviço, prevenir fraudes e melhorar o serviço
- **Consentimento**: Para funcionalidades opcionais como integração com Google Drive e Gmail

## Subcontratantes

O Haiku.lt usa os seguintes serviços de terceiros para fornecer a nossa funcionalidade:

### Google LLC

**Serviços usados**: Autenticação OAuth 2.0, API do Google Drive, API do Gmail, API do Google Calendar

**Dados partilhados**: Endereço de email, nome, tokens OAuth (apenas quando autoriza a integração com Google)

**Finalidade**: Para permitir que:
- **Autentique** com a sua conta Google usando OAuth 2.0
- **Google Drive** (âmbito: `drive.file`): Guarde PDFs de faturas no seu Drive em pastas organizadas (Haiku.lt/Invoices/Year). Só podemos aceder a ficheiros criados pela nossa aplicação, não aos seus outros ficheiros do Drive. Armazenamos IDs de ficheiros do Drive para rastrear faturas guardadas.
- **Gmail** (âmbito: `gmail.send`): Envie emails de faturas para compradores em seu nome. Não lemos a sua caixa de entrada ou emails existentes. Emails enviados aparecem na sua pasta "Enviados" do Gmail.
- **Google Calendar** (âmbito: `calendar.readonly`, opcional): Leia títulos de eventos do calendário, datas, horas e estado de presença para ajudar a criar faturas. Estes dados são obtidos temporariamente e não são armazenados permanentemente.

**Conservação de Dados**: 
- IDs de ficheiros do Drive: Armazenados na nossa base de dados até eliminar a fatura ou desconectar a sua conta Google
- Dados do calendário: Não armazenados (obtidos apenas a pedido)
- Dados do Gmail: Não armazenados (emails permanecem na sua conta Gmail)
- Tokens OAuth: Encriptados e armazenados até desconectar a sua conta

**Política de Privacidade**: [https://policies.google.com/privacy](https://policies.google.com/privacy)

**Localização**: Estados Unidos (com conformidade do Quadro de Privacidade de Dados UE-EUA)

### Stripe, Inc.

**Serviços usados**: Processamento de pagamentos para subscrições

**Dados partilhados**: Endereço de email, informação de pagamento (tratada diretamente pela Stripe)

**Finalidade**: Para processar pagamentos de subscrições para funcionalidades premium

**Política de Privacidade**: [https://stripe.com/privacy](https://stripe.com/privacy)

**Localização**: Estados Unidos (com conformidade do Quadro de Privacidade de Dados UE-EUA)

### Brevo (Sendinblue)

**Serviços usados**: Entrega de emails transacionais

**Dados partilhados**: Endereço de email do destinatário, conteúdo do email (tokens de link mágico para login; detalhes de fatura ao enviar faturas via Brevo)

**Finalidade**: Para entregar emails de autenticação (login por link mágico) e emails de faturas aos compradores

**Conservação de Dados**: A Brevo pode reter registos de emails enviados por um período limitado de acordo com a sua política. Não armazenamos conteúdo de email nos nossos servidores além do necessário para o enviar.

**Política de Privacidade**: [https://www.brevo.com/legal/privacypolicy/](https://www.brevo.com/legal/privacypolicy/)

**Localização**: União Europeia (França)

## Segurança de Dados

Tomamos medidas técnicas e organizacionais apropriadas para proteger os seus dados pessoais:

- Encriptação de dados sensíveis (tokens OAuth, tokens de atualização)
- Ligações HTTPS seguras
- Cookies de autenticação HTTP-only e seguros
- Atualizações regulares de software
- Isolamento de base de dados por utilizador
- Registo de auditoria para rastreamento de acesso à conta

## Notificação de Violação de Dados

No caso improvável de uma violação de dados que represente um risco para os seus direitos e liberdades, notificá-lo-emos a si e à autoridade de supervisão relevante dentro de 72 horas, conforme exigido pelo RGPD.

## Autoridade de Supervisão

Se tiver preocupações sobre como tratamos os seus dados pessoais, tem o direito de apresentar uma queixa à sua autoridade de supervisão de proteção de dados local.

## Atualizações a Esta Política

Podemos atualizar esta página de informação do RGPD de tempos a tempos. A data "modificado" no topo desta página indica quando foi atualizada pela última vez.

Para informação geral sobre privacidade, consulte a nossa [Política de Privacidade](/pt/privacy).
