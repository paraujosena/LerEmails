# LerEmails
projeto para ler emails com UiPath


é necessário habilitar gmail para permitir APPS menos seguros.

https://docs.uipath.com/activities/docs/get-imap-mail-messages

Configurar atividade:"GetIMAPMailMessages" para ler mensagens do email.

Configurar filtros de busca dentro da pasta indicada no email.

MailFolder:"Inbox"
Porta:993
Server:"imap.gmail.com"
FilterExpressionCharacterSet:"UTF-8"
MarkAsRead:1(marca)
OnlyUnreadMessages: 0(desmarca) 
Top:30

//para ler as 30 primeiras messagens, estando lidas ou não, e marcar como lida caso seja possível.

Query 
Traduzido
Filter Expression

All mail messages that contain "Welcome" in the subject 
Todas as mensagens de e-mail que contenham "Bem-vindo" no assunto
"SUBJECT ""Bem-vindo"""

All mail messages that contain "Welcome" in the subject and are from "john.smith@example.com" 
Todas as mensagens de e-mail que contêm "Bem-vindo" no assunto e são de "john.smith@example.com"
"SUBJECT ""Bem-vindo"" FROM john.smith@example.com"

All mail messages that contain "Welcome" in the subject and are not from "john.smith@example.com" 
Todas as mensagens de e-mail que contêm "Bem-vindo" no assunto e não são de "john.smith@example.com"
"SUBJECT ""Bem-vindo"" NOT FROM john.smith@example.com"

All mail messages that contain "Please review" in the body 
Todas as mensagens de e-mail que contenham "Por favor, revise"
"BODY ""Por favor, revise"""

All flagged mail messages (i.e. \Flagged flag set) 
Todas as mensagens de e-mail sinalizadas
"FLAGGED"

All mail messages since 02/23/2021 
Todas as mensagens de correio desde 23/02/2021
"SINCE 23-Feb-2021"

All non-delivery report mail messages received on 02/23/2021 or 01/23/2021
Todas as mensagens de e-mail de relatório de não entrega recebidas em 23/02/2021 ou 23/01/2021
"OR (ON 23-Feb-2021 FROM postmaster@outlook.com) (ON 23-Jan-2021 FROM postmaster@outlook.com)"

All mail messages unanswered today and from an email address that contains "examples.com" 
Todas as mensagens de e-mail não respondidas hoje e de um endereço de e-mail que contém "examples.com" 
"UNANSWERED ON " + DateTime.Today.ToString("dd-MMM-yyyy") + " FROM examples.com"
