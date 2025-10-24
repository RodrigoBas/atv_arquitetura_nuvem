# Proposta da Aplicação: Dashboard de Monitoramento de Webhooks de Terceiros

1. Propósito do Software

O objetivo deste projeto é desenvolver um dashboard em tempo real para monitorar eventos recebidos de um software de terceiros. Por exemplo, podemos monitorar "Novas Vendas" de uma loja Shopify ou "Novos Pagamentos" de um sistema como o Stripe, exibindo-os no dashboard no exato segundo em que acontecem.

A aplicação será construída usando uma arquitetura "serveless" e gratuita, demonstrando como processar e visualizar dados de webhooks instantaneamente.

2. Ferramentas e Tecnologias em Nuvem ("Stack Gratuito")

Ingestão de Dados (Webhook API): Vercel Serveless Function. Será nosso endpoint de API (ex: /api/webhook) que receberá os dados (JSON) enviados pelo software de terceiro.

Banco de Dados (Real-Time): Supabase (PostgreSQL). A Vercel Function irá salvar os dados recebidos do webhook na tabela do Supabase. O serviço de "Real-Time" do Supabase será ativado nesta tabela.

Front-End (Dashboard): React hospedado na Vercel. O dashboard usará a biblioteca do Supabase para "se inscrever" (subscribe) na tabela. Assim que a Vercel Function inserir um novo dado, o Supabase o enviará (via WebSocket) para o dashboard, que se atualizará ao vivo.

Código e Documentação (API): GitHub e GitHub Pages (para o swagger.yml que documenta nosso endpoint de webhook).


<img width="463" height="601" alt="image" src="https://github.com/user-attachments/assets/e27205bd-f962-40f3-849e-7f506bd64ba7" />

