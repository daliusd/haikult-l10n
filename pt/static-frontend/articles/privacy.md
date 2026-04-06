---
title: 'Política de Privacidade'
date: '2021-04-02'
modified: '2026-03-27'
showDate: false
---

Esta Política de Privacidade descreve como o Haiku.lt recolhe e usa dados.

## Dados que Recolhemos

- Endereço IP, data e hora, informação do navegador.

- Endereço de email.

- Dados que insere no sistema ao usá-lo.

## Cookies e Armazenamento do Navegador

Usamos cookies e armazenamento do navegador para fornecer funcionalidade essencial:

### Cookies

- **Cookie de Autenticação (auth_token)**: Um cookie seguro, HTTP-only usado para manter a sua sessão de login. Este cookie é essencial para o serviço funcionar e expira após aproximadamente 2 meses. Sem este cookie, não pode usar o Haiku.lt.

### Armazenamento Local do Navegador

Armazenamos os seguintes dados no armazenamento local do seu navegador:

- **Preferência de Idioma**: O idioma de interface selecionado (Inglês ou Lituano) para fornecer renderização imediata da interface.

- **Rejeição de Notificação**: Regista se rejeitou certas notificações para evitar mostrá-las repetidamente.

- **Sincronização de Mudança de Conta**: Dados temporários (eliminados após 1 segundo) usados para sincronizar a mudança de conta entre múltiplos separadores do navegador.

### Armazenamento de Sessão do Navegador

- **Rastreamento de Visita**: Um sinalizador apenas de sessão para prevenir ciclos de redirecionamento na página de destino. Estes dados são eliminados quando fecha o seu navegador.

### Sem Rastreamento de Terceiros

Não usamos quaisquer cookies de análise, publicidade ou rastreamento de terceiros. Todos os cookies e armazenamento são estritamente necessários para o serviço funcionar.

## Serviços de Terceiros

- **Serviços Google**: Integramos com serviços Google quando se conecta via OAuth do Google:

  - **Google Drive** (opcional): Se conceder permissão ao Google Drive, acedemos:
    - **O que acedemos**: Ficheiros criados pelo Haiku.lt no seu Google Drive. Usamos o âmbito `drive.file` que fornece acesso apenas a ficheiros criados pela nossa aplicação - não podemos ver ou aceder a quaisquer outros ficheiros no seu Drive.
    - **Como o usamos**: Para guardar PDFs de faturas no seu Google Drive numa estrutura de pastas organizada (Haiku.lt/Invoices/Year). Quando usa a funcionalidade "Guardar no Drive", criamos ou atualizamos ficheiros PDF.
    - **Como o armazenamos**: Armazenamos o ID do ficheiro do Google Drive na nossa base de dados para rastrear quais faturas foram guardadas e para permitir atualizações a ficheiros existentes. O conteúdo PDF real não é armazenado nos nossos servidores - existe apenas no seu Google Drive.
    - **Como o partilhamos**: IDs de ficheiros do Google Drive nunca são partilhados com terceiros, nunca são vendidos a corretores de dados e nunca são usados para publicidade, marketing, treino de IA ou qualquer finalidade que não seja gerir os seus PDFs de faturas no seu Drive.
    - **Como controlá-lo**: Pode gerir permissões do Drive através das suas [permissões da Conta Google](https://myaccount.google.com/permissions). Os ficheiros permanecem no seu Drive sob o seu controlo. Pode eliminá-los a qualquer momento. Revogar o acesso impede a nossa capacidade de criar novos ficheiros ou atualizar os existentes.
  
  - **Gmail** (opcional): Se conceder permissão ao Gmail, acedemos:
    - **O que acedemos**: Permissão para enviar emails através da sua conta Gmail. Usamos o âmbito `gmail.send` que permite enviar emails em seu nome. Não lemos os seus emails existentes nem acedemos à sua caixa de entrada.
    - **Como o usamos**: Para enviar emails de faturas aos seus compradores quando usa a funcionalidade "Enviar Fatura". Os emails incluem o PDF da fatura como anexo e anexos adicionais opcionais (como XML CII para faturação eletrónica).
    - **Como o armazenamos**: Não armazenamos conteúdo de email ou dados de mensagens enviadas. Emails enviados aparecem na sua pasta "Enviados" do Gmail sob o seu controlo.
    - **Como o partilhamos**: A capacidade de envio de email nunca é partilhada com terceiros, nunca é vendida e nunca é usada para publicidade, marketing, spam ou qualquer finalidade que não seja enviar faturas que escolhe explicitamente enviar.
    - **Como controlá-lo**: Pode gerir permissões do Gmail através das suas [permissões da Conta Google](https://myaccount.google.com/permissions). Emails enviados permanecem na sua conta Gmail. Revogar o acesso impede a nossa capacidade de enviar emails em seu nome.
  
  - **Google Calendar** (opcional, apenas leitura): Se conceder permissão de calendário, acedemos:
    - **O que acedemos**: Os nomes dos seus calendários, títulos de eventos, datas/horas de eventos e estado de presença (para filtrar eventos recusados). Usamos o âmbito da API do Google Calendar `calendar.readonly` que fornece acesso apenas de leitura.
    - **Como o usamos**: Exclusivamente para ajudá-lo a criar faturas baseadas em eventos de calendário através da funcionalidade "Criar a partir do Calendário". Títulos de eventos tornam-se descrições de itens de linha de fatura, e datas de eventos ajudam a definir intervalos de datas de faturas.
    - **Como o armazenamos**: Dados de calendário **não são armazenados permanentemente** nas nossas bases de dados. São obtidos a pedido apenas quando usa a funcionalidade de fatura de calendário e existem temporariamente na memória do seu navegador durante o processo de criação de fatura.
    - **Como o partilhamos**: Dados de calendário **nunca são partilhados** com terceiros, **nunca são vendidos** a corretores de dados e **nunca são usados** para publicidade, marketing, treino de IA ou qualquer finalidade que não seja criar faturas para si.
    - **Como controlá-lo**: Pode gerir permissões de calendário independentemente através das suas [permissões da Conta Google](https://myaccount.google.com/permissions). Revogar o acesso impede o acesso a dados imediatamente. Também pode desconectar toda a sua conta Google através das configurações do Haiku.lt.
    
  Todas as permissões OAuth do Google requerem a sua autorização explícita. Controla quais permissões conceder e pode revogá-las a qualquer momento.

- **Stripe**: Usamos a Stripe para processamento de pagamentos de subscrições premium. A Stripe trata toda a informação de pagamento de forma segura de acordo com a sua política de privacidade. Apenas recebemos confirmação de pagamentos bem-sucedidos.

- **Brevo (Sendinblue)**: Usamos a Brevo para entregar emails transacionais, incluindo emails de login por link mágico e emails de faturas. A Brevo recebe o endereço de email do destinatário e o conteúdo do email necessário para entregar estas mensagens. A Brevo está localizada na UE (França). Consulte a sua [Política de Privacidade](https://www.brevo.com/legal/privacypolicy/).

## Proteção de Dados

Para proteger os dados recolhidos, tomamos as seguintes medidas:

- Atualizar o software do servidor tão frequentemente quanto possível.

- Atualizar o software do Haiku.lt tão frequentemente quanto possível.

- Configurar adequadamente os servidores.

## Os Seus Direitos

Para informação detalhada sobre os seus direitos de dados ao abrigo do RGPD, incluindo o direito de aceder, eliminar e exportar os seus dados, consulte a nossa [página RGPD](/pt/gdpr).
