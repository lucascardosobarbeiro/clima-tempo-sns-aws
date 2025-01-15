#Notificação de Clima com AWS Lambda, SNS e OpenWeatherMap
Este projeto envia notificações por e-mail sobre o clima atual de uma cidade. Utilizando a API OpenWeatherMap, a AWS Lambda busca as condições climáticas e envia as informações para os destinatários através do Amazon SNS (Simple Notification Service). A execução automática da função Lambda é agendada com Amazon EventBridge.

#🚀 Recursos Utilizados
AWS Lambda: Serviço serverless da AWS para executar a função que obtém os dados climáticos e envia as notificações.
Amazon SNS (Simple Notification Service): Serviço de mensagens da AWS que envia as notificações por e-mail.
Amazon EventBridge: Serviço da AWS que agenda a execução automática da função Lambda.
OpenWeatherMap API: API que fornece informações sobre o clima em tempo real para qualquer cidade do mundo.
Python 3.x: Linguagem utilizada para desenvolver a função Lambda.

#📝 Pré-Requisitos
Antes de começar, você precisará de:

Uma conta na AWS.
Uma chave de API do OpenWeatherMap (se ainda não tiver, cadastre-se aqui).
Permissões adequadas no IAM para configurar o Lambda, SNS e EventBridge.
⚙️ Como Configurar o Projeto
Passo 1: Obter a Chave da API do OpenWeatherMap
Acesse o OpenWeatherMap e crie uma conta.
Após o cadastro, gere uma chave de API que será usada para consultar as condições climáticas de uma cidade.
Passo 2: Criar um Tópico no SNS
Acesse o Console da AWS e navegue até Amazon SNS.
Crie um novo tópico (por exemplo, "Notificações de Clima").
No tópico, adicione os e-mails que devem receber as notificações.
Copie o ARN do tópico SNS. Este ARN será utilizado na função Lambda para enviar as notificações.
Passo 3: Configurar a Função Lambda
No Console da AWS, vá até AWS Lambda e crie uma nova função com o runtime Python 3.9.
No código da função, substitua as variáveis:
API_KEY: Sua chave de API do OpenWeatherMap.
ARN_DO_TOPICO: O ARN do seu tópico SNS copiado no passo anterior.

Passo 4: Configurar o EventBridge
Acesse o Amazon EventBridge no Console da AWS.
Crie uma nova regra para agendar a execução da função Lambda. Defina a frequência para a execução, como, por exemplo, "a cada 1 hora" ou "diariamente".
Na configuração da regra, defina a função Lambda como destino da regra para que ela seja executada automaticamente conforme a programação.
Passo 5: Testar a Função Lambda
Crie um evento de teste no Console do Lambda para disparar a função manualmente.
Verifique se o e-mail com as condições climáticas é enviado corretamente.
🌐 Conclusão
Agora, sua função Lambda está configurada para enviar notificações de clima por e-mail, com a execução automática programada através do Amazon EventBridge.

💡 Melhorias Possíveis
Adicionar mais cidades para monitoramento.
Implementar mensagens personalizadas de alerta, dependendo das condições climáticas (ex: alertas de chuva, calor intenso).
Integrar a função com outros serviços de comunicação, como SMS ou Slack.
📑 Licença
Este projeto está sob a licença MIT License. Veja o arquivo LICENSE para mais detalhes.

