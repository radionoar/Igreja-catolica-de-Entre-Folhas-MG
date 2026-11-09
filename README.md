# Igreja Católica — Transmissão Ao Vivo
## PWA para GitHub Pages | Personalização da Nativa FM V1.9.4

O aplicativo preserva o funcionamento da versão original: instalação PWA, reprodução automática quando aberto pelo ícone instalado (sujeita às políticas do navegador), reconexão automática, controles liga/desliga, visualizador circular multicolorido **baseado no áudio real**, metadados Zeno, compatibilidade mobile e desktop e interface sem rolagem.

### Informações personalizadas

- **Nome:** Igreja Católica
- **Slogan:** Transmissão Ao Vivo
- **Stream:** `https://stream.zeno.fm/7dmkbtzfy6nuv`
- **Metadados:** `https://api.zeno.fm/mounts/metadata/subscribe/7dmkbtzfy6nuv`
- **WhatsApp:** +55 (33) 3324-6263 (`553333246263` no formato `wa.me`). É necessário que esse número esteja cadastrado no WhatsApp para a conversa abrir.
- **Contato:** um único botão, `ENTRAR EM CONTATO`.
- **Compartilhar:** botão ao lado do liga/desliga; abre o WhatsApp com convite contendo nome da rádio e endereço da instalação.
- **Tema:** Ciano Neon `#32E9E9` em substituição ao verde. O equalizador permanece multicolorido.
- **Logotipo e ícones PWA:** gerados da imagem fornecida (igreja).

### Endereço de instalação/compartilhamento

Não foi informado endereço definitivo. Por isso o aplicativo usa **automaticamente o endereço onde estiver publicado**: se publicado em `https://usuario.github.io/igreja-catolica/`, compartilhará essa mesma URL. **Não precisa alterar nada depois de publicar no GitHub Pages**, desde que o endereço esteja correto e a PWA seja aberta pelo ícone instalado.

Para usar outro endereço (por exemplo, um domínio próprio), edite **somente** `config.js` e preencha `shareInstallUrl` com o URL HTTPS completo:

```js
shareInstallUrl: 'https://seu-dominio.com/'
```

O número do WhatsApp, nome, slogan, URL de stream e identificador Zeno também são mantidos em `config.js` para futuras adaptações.

### Como publicar no GitHub Pages

1. No GitHub, crie um repositório, por exemplo `igreja-catolica`.
2. Envie os arquivos **de dentro do ZIP** para a **raiz** do repositório (`index.html` na raiz, não em subpasta).
3. No repositório abra **Settings → Pages → Build and deployment**, selecione **Deploy from a branch**, branch **main** e pasta **/(root)**.
4. Acesse a URL HTTPS do GitHub Pages e instale o app usando `INSTALAR APLICATIVO` ou o menu do navegador quando o navegador exigir.
5. Abra o app instalado, teste áudio, metadados, VU-meter, reconexão, WhatsApp e compartilhamento em dispositivos reais.

### Limites do navegador e streaming

- O fluxo da Zeno pode tocar mesmo quando as regras **CORS** do streaming impedem a análise de frequências. A V1.9.4 já possui rotina de fallback para a reprodução; a existência de VU-meter real depende de CORS do servidor Zeno. O visualizador não utiliza uma animação falsa.
- O áudio automático está sujeito a permissões de autoplay, principalmente em iOS.
- O URL da Zeno foi configurado conforme fornecido, sem afirmação de que a transmissão esteja online neste momento.
- Alguns navegadores exigem instalação por menu/compartilhamento em vez do prompt nativo.

### Arquivos necessários

Somente `index.html`, `config.js`, `app.js`, `landing.js`, `gate.js`, `styles.css`, `sw.js`, `manifest.webmanifest`, `.nojekyll`, `assets/` e `icons/` precisam ser publicados. O `README.md` é opcional e serve como manual.

**Base de reprodução mantida:** V1.9.4; nenhuma modificação na lógica de áudio, temporização de reconexão ou cálculo das 24 bandas do visualizador, exceto textos de identidade e cor do aro. **Nenhuma dependência de Node ou servidor próprio.**
