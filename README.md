Bot de WhatsApp

Funcionalidades:

	•	Exibição da lista de comandos
	•	Exibição do ID do chat atual
	•	Exibição da hora atual do servidor onde o bot está rodando
	•	Exibição do seu nome
	•	Envio de arquivos de diferentes formatos (PDF, jpg, doc, mp3, etc.)
	•	Envio de mensagens de voz pré-gravadas
	•	Envio de coordenadas geográficas (localizações)
	•	Configuração de uma conferência (grupo)

Atenção: Para que o bot funcione completamente, por favor, mantenha seu telefone sempre online. Seu telefone não deve ser usado para o WhatsApp Web ao mesmo tempo.

Início

Primeiro, vamos conectar o WhatsApp com nosso script para que possamos verificar como o código funciona enquanto o escrevemos. Para fazer isso, vamos acessar nossa conta e obter um código QR. Em seguida, abra o WhatsApp no seu celular, vá para Configurações → WhatsApp Web → Escanear o código QR.

Neste ponto, a URL do WebHook deve ser fornecida para que o servidor acione nosso script para mensagens recebidas. A URL do WebHook é um link para o qual os dados JSON contendo informações sobre mensagens recebidas ou notificações serão enviados usando o método POST. Portanto, precisamos de um servidor para fazer o bot funcionar e este servidor aceitará e processará essas informações. Enquanto escrevia este artigo, implantamos o servidor usando o microframework FLASK. O servidor FLASK nos permite responder convenientemente às solicitações recebidas e processá-las.

	pip install flask

Em seguida, clone o repositório para você. Depois, vá para o arquivo wabot.py e altere as variáveis APIUrl e token para as suas do seu gabinete pessoal https://app.chat-api.com/instance/

Construtor de classe, o padrão que aceitará JSON, que conterá informações sobre mensagens recebidas (será recebido pelo WebHook e encaminhado para a classe). Para ver como o JSON recebido ficará, você pode entrar na seção de Testes, disponível no seu gabinete. Você também pode testar as solicitações do WebHook nele. https://app.chat-api.com/testing

Você pode visualizar a estrutura do JSON na seção de testes do item “Check WebHook”. É necessário executar a verificação e enviar mensagens para o seu chat do WhatsApp. Você verá o JSON enviado ao WebHook na tela.

Copie este JSON e execute nosso servidor local FLASK com a ajuda de um depurador no editor de código ou através do

	flask run

Para emular a solicitação ao servidor, precisamos enviar uma solicitação POST do JSON, que copiamos na etapa anterior. A solicitação é enviada para o endereço do seu localhost onde o flask está sendo executado. Assim, podemos emular as ações do WebHook e testar a funcionalidade do bot.