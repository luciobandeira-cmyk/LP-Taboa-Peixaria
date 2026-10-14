# Taboa Peixaria · Landing page

Landing page da Taboa Peixaria (Manaus/AM), com conversão para WhatsApp. HTML, CSS e JS puros, sem build e sem dependências externas.

## Publicar no GitHub Pages

1. Crie um repositório (ex.: `taboa-lp`) e envie **todo o conteúdo desta pasta** para a raiz, incluindo o arquivo `.nojekyll`.
2. No repositório: **Settings → Pages → Build and deployment → Source: Deploy from a branch**, branch `main`, pasta `/ (root)` → **Save**.
3. Em 1–2 minutos a página fica em `https://SEU-USUARIO.github.io/taboa-lp/`.

## Estrutura

```
index.html   página completa (estilos e scripts inline)
img/         fotos, logos, grafismos, og.jpg (compartilhamento) e ícones
fonts/       Gugi, Caveat Brush e Roboto (hospedadas localmente)
.nojekyll    evita processamento do Jekyll no GitHub Pages
```

## Configurações rápidas (no fim do `index.html`, bloco `CONFIGURAÇÃO`)

- `WHATSAPP`: número com DDI + DDD, só dígitos. Atual: `5592991972112`.
- `IFOOD`: link direto da loja no iFood (vazio = usa o Linktree).
- Mensagens pré-preenchidas do WhatsApp: objeto `MSGS`.
- Parâmetros `utm_campaign` / `utm_source` da URL são repassados na mensagem do WhatsApp.

## Medição

Todo clique em WhatsApp envia `{event: "whatsapp_click", cta_secao, cta_texto}` para o `dataLayer` e, se existirem, dispara `fbq('track','Contact')` e `gtag('event','whatsapp_click')`. Basta instalar o GTM / Pixel / GA4 no `<head>`.

## Antes de ir para o domínio final

Esta versão é de **apresentação** e está com `noindex` (não aparece no Google). No domínio definitivo:

- Remova a linha `<meta name="robots" content="noindex, nofollow">`.
- Adicione `<link rel="canonical" href="https://DOMINIO/">` e `<meta property="og:url" content="https://DOMINIO/">`.
- Troque `og:image` para o endereço completo: `https://DOMINIO/img/og.jpg`.
- Troque os `./img/...` do bloco JSON-LD (`application/ld+json`) pelo domínio completo.

## Pendências com a cliente

- Link do iFood.
- Confirmar o número do WhatsApp (o letreiro mostra 991197-2112; o cardápio, 99197-2112).
- Confirmar o nome e a foto da fundadora, a vigência da 5ª Temporada Icamiabas e o símbolo Muiraquitã no cardápio novo.
