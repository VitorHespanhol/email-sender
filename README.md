# 📧 Email Service
Solução para um antigo *coding challenge da Uber*, focado em criar um serviço de envio de emails.

Este projeto foi desenvolvido para testar habilidades em:

- Abstração de serviços externos  
- Boas práticas de arquitetura e clean code  
- Integração com APIs reais (SendGrid, Mailgun, SparkPost, Amazon SES)

---

## 🧩 Objetivo do Desafio  
Criar um serviço capaz de:

1. **Receber requisições para envio de email** contendo:  
   - `to`  
   - `subject`  
   - `body`  

2. **Enviar o email usando um provedor de email** (SendGrid, Mailgun, SparkPost, Amazon SES).

3. A implementação deve permitir **incluir novos provedores facilmente** e manter a lógica desacoplada.

---

## 🏗 Arquitetura da Solução  

### 🔌 1. Email Provider Interface  
Todos os provedores implementam a mesma interface:

sendEmail(to, subject, body)

##Pontos de Destaque
###✔ Abstração Total

Todos os provedores implementam a mesma interface, deixando o core desacoplado das APIs externas.

###✔ Extensível

Adicionar um novo provider leva apenas 1 classe + configuração.

###✔ Resiliente

Tratamento de exceções, timeouts e respostas HTTP inválidas.

###✔ Clean Code / SOLID

ISP: cada provedor implementa apenas o que precisa

DIP: o core depende de abstrações, não implementações

OCP: novos provedores entram sem modificar código existente
