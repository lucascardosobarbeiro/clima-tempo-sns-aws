Notificação de Clima com AWS Lambda, SNS e OpenWeatherMap
Este projeto foi desenvolvido para enviar notificações sobre o clima atual de uma cidade por e-mail. A função Lambda busca as condições climáticas utilizando a API OpenWeatherMap e envia as informações por meio do Amazon SNS (Simple Notification Service). Além disso, utilizamos o Amazon EventBridge para agendar a execução automática da função em intervalos regulares.

Recursos Utilizados
AWS Lambda: Serviço de computação serverless da AWS, usado para rodar a função que busca os dados climáticos e envia as notificações.
Amazon SNS: Serviço de mensagens da AWS, responsável por enviar as notificações por e-mail.
Amazon EventBridge: Serviço da AWS que orquestra e agendou a execução automática da função Lambda em intervalos específicos.
OpenWeatherMap API: API gratuita que fornece informações sobre o clima em tempo real para qualquer cidade do mundo.
Python 3.x: Linguagem de programação utilizada para desenvolver o código da função Lambda.
Pré-Requisitos
Antes de começar, você precisará de:

Uma conta na AWS.
Uma chave de API da OpenWeatherMap. Cadastre-se aqui para obter a chave.
Acesso à AWS SNS para criar um tópico de e-mail para enviar notificações.
Permissões adequadas no IAM para configurar o Lambda, SNS e EventBridge.
Como Configurar o Projeto
Passo 1: Obter a Chave da API do OpenWeatherMap
Crie uma conta no OpenWeatherMap.
Após se cadastrar, gere uma chave de API que será utilizada para consultar as condições climáticas.
Passo 2: Criar um Tópico no SNS
Acesse o AWS Management Console e navegue até o Amazon SNS.
Crie um novo tópico (por exemplo, "Notificações de Clima").
No tópico, adicione os endereços de e-mail que devem receber as notificações.
Copie o ARN do tópico SNS, que será utilizado na função Lambda.
Passo 3: Configurar a Função Lambda
No Console da AWS, vá até AWS Lambda.
Crie uma nova função Lambda com o runtime Python 3.9.
No código da função, substitua as variáveis API_KEY pela sua chave do OpenWeatherMap e ARN_DO_TOPICO pelo ARN do seu tópico SNS.
Passo 4: Configurar o EventBridge
Acesse o Amazon EventBridge no Console AWS.
Crie uma nova regra para agendar a execução da função Lambda. Você pode configurar a frequência, como por exemplo, "a cada 1 hora" ou "diariamente".
Na configuração da regra, defina a função Lambda como destino da regra para que ela seja executada automaticamente conforme a programação.
Passo 5: Testar a Função Lambda
Crie um evento de teste para disparar a função Lambda manualmente.
Verifique se o e-mail com as condições climáticas é enviado corretamente.
