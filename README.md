# 🚀 TikTok Shop Affiliate AutoBot

Sistema automatizado em formato de Web App (Streamlit) projetado para gerenciar contas de afiliados do TikTok Shop. O robô minera de forma 100% autônoma os produtos mais vendidos e virais da plataforma, gera roteiros persuasivos com Inteligência Artificial, renderiza vídeos verticais com transições dinâmicas e publica os conteúdos vinculando automaticamente o carrinho amarelo de comissão, disparando alertas de vendas direto no seu celular via Telegram.

---

## 🛠️ Como Configurar a Conta de Desenvolvedor do TikTok Shop

Para que o robô tenha permissão para buscar produtos e postar em seu perfil com o carrinho amarrado, você precisa obter as credenciais oficiais. Siga as etapas abaixo:

### 1. Registro no Portal de Desenvolvedores
1. Acesse o [TikTok Developer Portal](https://tiktok.com) e crie ou faça login na sua conta.
2. No menu principal, clique em **Manage Apps** e depois em **Create App**.
3. Selecione o tipo de integração comercial/plataforma e dê um nome ao seu projeto (ex: `AutoBot_Afiliado`).

### 2. Configuração de Escopos de Permissão (Scopes)
Para o robô funcionar sem bloqueios, seu aplicativo precisa ter aprovação para os seguintes escopos de dados. Ative-os na aba de permissões:
* `video.upload`: Permite que o robô envie os vídeos renderizados para a sua conta.
* `video.publish`: Permite a postagem direta dos conteúdos.
* `commerce.affiliate.product`: Permite varrer a API em busca de preços, imagens e taxas de comissão.
* `commerce.affiliate.orders` (Opcional): Permite que o webhook leia as vendas faturadas em tempo real.

### 3. Coleta de chaves e Geração do Access Token
1. Assim que o aplicativo for criado, copie a sua **Client Key** e o **Client Secret**.
2. Realize o processo de autenticação OAuth 2.0 padrão do TikTok para autorizar o aplicativo a gerenciar o seu perfil de afiliado.
3. Isso gerará o seu **Access Token permanente** (ou Refresh Token). Guarde esse código, pois ele é a chave de acesso do robô.

---

## 📱 Configuração do Bot de Alertas no Telegram

O robô envia mensagens instantâneas no seu celular sempre que realiza uma postagem ou quando uma venda é computada.

1. No Telegram, procure por **@BotFather** e envie o comando `/newbot`.
2. Siga as instruções para escolher um nome e copie o **HTTP API Token** gerado.
3. Procure por **@userinfobot** e envie qualquer mensagem para obter o seu número de **Chat ID**.

---

## 🚀 Como Colocar o Site Online (Streamlit Community Cloud)

1. Crie um repositório **privado** no seu GitHub e suba os 3 arquivos do projeto (`app.py`, `motor.py`, `requirements.txt`).
2. Acesse o [Streamlit Community Cloud](https://streamlit.io) e conecte sua conta do GitHub.
3. Clique em **New App**, selecione o seu repositório e o arquivo principal `app.py`. Clique em **Deploy**.
4. Assim que o site carregar, clique nos três pontinhos no canto superior direito da tela do Streamlit, vá em **Settings** e acesse a aba **Secrets**.
5. Cole o bloco abaixo preenchendo com as chaves que você coletou nos passos anteriores:

```toml
TIKTOK_ACCESS_TOKEN = "COLE_AQUI_O_SEU_ACCESS_TOKEN_DO_TIKTOK"
OPENAI_API_KEY = "COLE_AQUI_A_SUA_CHAVE_DA_OPENAI"
ELEVENLABS_API_KEY = "COLE_AQUI_A_SUA_CHAVE_DA_ELEVENLABS"
TELEGRAM_BOT_TOKEN = "COLE_AQUI_O_TOKEN_DO_BOT_TELEGRAM"
TELEGRAM_CHAT_ID = "COLE_AQUI_O_SEU_CHAT_ID_NUMERICO"
```

6. Clique em **Save**. O site irá reiniciar e seu Piloto Automático estará pronto para rodar 24h por dia!

---

## 📈 Janelas de Postagem Automática
O robô está programado de forma nativa para disparar o motor de edição e postagem nos horários de maior pico de entrega orgânica e consumo no Brasil:
* **12:00h** (Horário de almoço)
* **18:00h** (Saída do trabalho/escola)
* **21:00h** (Pico de navegação noturna)
