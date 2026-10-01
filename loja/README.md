# Loja GAIA

## Vitrine contínua

A coleção repete os produtos do filtro ativo conforme o visitante rola para baixo. O controle “Pausar rolagem infinita” permanece acessível durante a navegação, e o atalho de personalização permite sair da vitrine. Os cartões usam perspectiva de olho de peixe conforme sua posição na tela e aumentam 30% ao passar o mouse em dispositivos com ponteiro preciso. A preferência de movimento reduzido desativa essas transformações.

Execute `npm run test:collection` com o servidor local na porta 4173 para verificar zoom, rolagem, filtros, sacola, pausa e comportamento mobile.

O efeito de bolha aparece somente durante a rolagem. Após 160 ms sem movimento, os cartões retornam suavemente ao formato normal em 320 ms; o zoom ao passar o mouse continua independente.

Loja estática em português, sem etapa de compilação. Abra `index.html` ou sirva esta pasta com `python -m http.server 4173`.

## Entrega

- Catálogo de chaveiros personalizados, adesivos e kit de carrinho Arduino.
- Carrossel manual com botões, teclado e gesto de deslizar; sem reprodução automática.
- Filtros, sacola persistente, controle de quantidade e remoção.
- Temas claro/escuro, preferência salva e padrão do sistema.
- Formulário de pedido e consulta de personalização.
- Links do blog, patrocínio e Instagram.

## E-mail e preços

Destino confirmado: **gaia.robotica.uftm@gmail.com**.

O checkout usa `mailto:`: prepara a mensagem no aplicativo do visitante, que precisa confirmar o envio. Há uma mensagem copiável se o aplicativo não abrir. O site não declara que o pedido foi enviado e não apaga a sacola. Não há envio automático, cobrança, reserva de estoque ou gravação de dados pessoais em servidor. Envio automático exige um serviço de e-mail/backend configurado; nunca inclua senhas SMTP no JavaScript público.

Preços, composição do kit, produção e entrega estão **sob consulta**. Os chaveiros e adesivos usam ilustrações CSS com a marca oficial; a foto dos carrinhos vem do blog e é referência, não fotografia de um kit comercial confirmado.

O catálogo desta versão fica em `js/store.js`. A loja não depende de Firebase. Os arquivos antigos `admin.html`, `js/admin.js`, `js/firebase-init.js` e `css/style.css` foram preservados, mas não são usados pela nova vitrine; o painel antigo não administra este catálogo.

## Integração do blog

Uma cópia pronta para publicação está em `../../gaiarobotica-new.github.io-main/loja/`. A navegação das páginas do blog e o portal têm links para essa pasta. O gerador `scripts/sync_site.py` também conserva a entrada Loja e a URL no sitemap.

Para publicar, revise e publique o repositório do blog pelo fluxo habitual do GitHub Pages. Nenhum deploy ou push foi executado. A URL prevista é `https://gaiarobotca.github.io/gaiarobotica-new.github.io/loja/`.

Após editar a loja, execute `python scripts/sync_blog.py` para atualizar os seis arquivos públicos na cópia do blog. Esse script não altera o menu do blog nem copia o painel antigo.

## Verificação

Os fluxos foram verificados no Edge/Playwright, com revisão de acessibilidade axe nos dois temas. Para repetir: `npm install`, `npm run test:browser`. Mantenha esta loja em `http://127.0.0.1:4173/` ou defina `GAIA_TEST_URL` para a URL da cópia integrada. Se necessário, defina `GAIA_BROWSER_PATH` para o executável Chromium/Edge local. Os testes apenas preparam mensagens; não enviam e-mails.
