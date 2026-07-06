# 📍 Onde a gente está — Dymani

> Arquivo vivo pra bater o olho e saber, em 1 minuto, **qual é o objetivo, o que já foi feito e o que falta**. Toda vez que mexer no projeto, atualize as caixinhas aqui embaixo.
>
> Última atualização: **04/07/2026**

---

## 🎯 O objetivo (a estrela-guia)

Criar um sistema **tão bom que ter Dymani vira obrigação** pra manicure — igual ela ter WhatsApp. Não é "mais um app", é a ferramenta que ela **não consegue mais viver sem**.

Por quê ela vai sentir isso na pele:

1. **Hoje a cliente dela é bagunça.** A manicure até tem a agenda do celular cheia de nome de mulher, grupo do WhatsApp, conversa perdida no direct — mas é tudo espalhado e desorganizado. Ela não sabe quem sumiu, quem tá na hora de voltar, quem é fiel.
2. **O Dymani organiza tudo num lugar só.** Toda cliente vira um cadastro com foto da unha, histórico, selos de fidelidade e a data que ela precisa voltar. A bagunça vira uma **rede de clientes organizada** — o patrimônio dela.
3. **E ainda traz cliente novo.** Cada unha feita vira propaganda (o Cartão da Unha que a cliente posta no status), e o lembrete "tá na hora de voltar" traz de volta quem sumiu. Mais cliente = mais dinheiro.

👉 **Se ela sentir que perder o Dymani é perder a carteira de clientes dela, os R$29/mês pagam sozinhos.** Essa é a régua: cada coisa que a gente construir tem que empurrar pra esse sentimento.

---

## 💰 O negócio em uma linha

R$29/mês por manicure · sem implantação · meta: **20 manicures = R$580/mês**.

Status comercial: **ainda sem cliente pagante** (jul/2026). O produto está pronto e no ar; falta começar a vender.

---

## 🌐 Como acessar hoje

- **Site / vitrine:** https://dymani-git-main-convitefys-projects.vercel.app
- **App da manicure:** `.../painel`
- **Portfólio público:** `.../portfolio`
- **Demo pra testar:** no painel, link `studio-demo` / senha `1234`

---

## ✅ O que já está pronto

- [x] As 3 telas construídas (vitrine, painel/app da manicure, portfólio público)
- [x] Cadastro de clientes com foto da unha, histórico e selos de fidelidade
- [x] Editor do Cartão da Unha estilo Canva (logo arrastável, temas, frase)
- [x] Alerta "quem está na hora de voltar" no topo do painel
- [x] Agendamento em tempo real (horário ocupado risca pra todo mundo, sem choque de horário)
- [x] Multitenant na nuvem (Supabase) — cada manicure com seu studio (slug + PIN); trocar de celular não perde nada
- [x] Publicado no ar (Vercel) e repositório público
- [x] Testado ponta a ponta (Playwright, 0 erros de JS)
- [x] **QR code de agendamento no cartão** (gerador próprio, offline — abre o portfólio; testado lendo em leitor de QR nos 4 layouts)
- [x] **4 layouts de cartão**: Foto inteira, Clássico, Polaroid e Moderno
- [x] **Câmera dentro do navegador** com molde pra enquadrar a unha (+ botão trocar frente/trás; cai no seletor de arquivo se falhar)
- [x] **Subir foto da galeria** no atendimento e trocar a foto do cartão no editor
- [x] Selos de fidelidade agora são **estrelas** (na lista, na ficha e no cartão) no lugar dos pontinhos
- [x] Corrigido: o menu de baixo não tapa mais os botões (salvar imagem etc.)
- [x] 🧪 **Experimento "Cartão ao Vivo"** (`camera.html`, página de teste 100% separada — não mexe no app): a câmera abre já com o layout premium do cartão por cima (nome, selos dourados, logo, QR), tipo filtro do Instagram; a foto sai pronta pra postar. Testado com Playwright (0 erros, QR lendo)
- [x] 🔬 **Provador Virtual — ETAPA 1** (`provador.html`, página de teste separada): abre a câmera e desenha ao vivo os 21 pontos da mão + a **zona da unha** de cada dedo, usando **MediaPipe Hand Landmarker** (roda no próprio celular, grátis, sem servidor). Refinado (a pedido do dono): foca em **1 dedo só** (o mais apresentado, com histerese pra não pular) e desenha **só o contorno da unha** (formato amêndoa acompanhando a inclinação, com suavização anti-tremor). Modos: Só a unha / Ver a mão; contador e FPS; trocar câmera. Objetivo: validar a precisão do encaixe antes da etapa 2 (trocar o contorno por uma unha realista / 3D). Smoke-testado com Playwright (modelo inicializa, loop roda, 0 erros); a precisão real quem valida é o dono apontando pra própria mão. Lib via CDN (jsdelivr+googleapis) — funciona no celular; no sandbox o jsdelivr é bloqueado, testei com a lib baixada via npm
- [x] 💳 **Carteirinha da Cliente** (`carteirinha.html`, página pública leve — `?s=slug&c=id`): a cliente vê os selos dela juntando (animados), a barra de progresso, o álbum das unhas dela, "faltam X pra unha grátis" (confete quando completa), e botões de **Agendar de novo** e **Indicar amiga** (link de indicação dela). Sem instalar nada. Nova função `cu_carteirinha` (security definer, sem PIN, só dados seguros). No painel, botão "Enviar carteirinha" na ficha da cliente manda o link pelo WhatsApp dela. Cliente demo criada no studio-demo (Gabriela, id 7). Testado E2E: 0 erros
- [x] 📊 **Relatório do Mês** (no painel, entrada na tela de Clientes): resumo automático do mês — valor que passou pela agenda (≈ R$, estimado pelos preços dos serviços), atendimentos, clientes que voltaram, cartões postados, indicações e clientes novas. Anti-churn (a manicure *sente* o valor). Calculado no próprio painel a partir do histórico já carregado + agenda; botão "Compartilhar meu mês". Testado E2E: números conferidos, 0 erros
- [x] 💎 **Os 5 layouts de cartão viraram premium** (só o Premium era bonito): Glam (foto cheia, temável por cor), Realeza (emoldurado simétrico), Marfim (creme claro), Art Déco (ousado). Kit de ornamentos desenhados à mão (flores, gemas/diamantes, moedas com relevo, molduras douradas, selo da marca) — QR e logo em posições diferentes em cada, fonte Playfair, **zero emoji**. Guard de geração no desenho evita resíduo ao trocar tema rápido. Testado: render dos 5 + câmera ao vivo, 0 erros
- [x] 📸 **Cadastro de cliente em etapas + Câmera ao Vivo dentro do painel**: o "Novo atendimento" virou um fluxo de 3 passos (Cliente → Serviço → Cartão). No passo do cartão, a câmera abre com o cartão desenhado POR CIMA ao vivo e uma **fita de temas embaixo estilo filtro do Instagram** (✨ Premium + Rosa/Dourado/Vermelho/Lilás) — escolhe o tema vendo o resultado ao vivo, bate a foto e cai na tela "Ficou linda!" com **Compartilhar / Tirar outra / Ajustar tema**. Salva sozinho (cria cliente + atendimento + selo). Testado E2E com câmera falsa: 0 erros
- [x] 🎠 **Portfólio virou site de conversão**: carrossel-herói com as fotos passando sozinhas (crossfade + zoom lento, arrastável), serviços em **cards com FOTO** + preço + botão que já pré-seleciona no agendamento, barra fixa de conversão com resumo da escolha ("Alongamento · 06/07 às 09:00 — só confirmar!"), seção "como funciona", animações de entrada ao rolar. No painel, cada serviço agora pode ter foto (caixinha 📷 na tela de serviços — salva no mesmo jsonb, sem migração). Testado E2E com Playwright: fluxo completo até o agendamento confirmado, 0 erros
- [x] ✨ **Estilo "Premium" no editor do painel** (5º estilo, agora o padrão pra quem nunca escolheu): moldura dourada, fonte Playfair Display, moedas de selo com relevo, bokeh, logo do studio da manicure num selo redondo (ou monograma se não tiver logo), QR creme "Agende seu horário". Multitenant de verdade — cada studio com a marca dele. Testado com Playwright: 0 erros, QR lendo, os 4 estilos antigos intactos

---

## ⏳ O que falta (pendências)

### Produto
- [ ] Deixar o endereço bonito de divulgar (domínio `dymani.vercel.app` grátis ou `dymani.com.br` ~R$40/ano)
- [ ] Importar contatos que a manicure já tem (pra ela não digitar cliente por cliente — tirar a preguiça de começar)
- [ ] Lembrete automático de volta caindo no WhatsApp da cliente na hora certa
- [ ] Deixar o Cartão da Unha ainda mais "digno de status" (é o motor da propaganda)

### Marca / jurídico
- [ ] Conferir domínio no Registro.br
- [ ] Busca prévia da marca "Dymani" no INPI antes de gastar com material

### Vendas (o gargalo real agora)
- [ ] Fechar a **1ª manicure** usando de verdade (nem que seja de graça no começo, pra provar valor)
- [ ] Pegar depoimento + print de resultado dela pra vender pras próximas
- [ ] Definir como abordar (mandar o Cartão da Unha pronto dela como isca?)

---

## 🧭 Próximo passo sugerido

Escolher UM foco de cada vez. A ordem que faz mais sentido:

1. **Domínio bonito** (rápido, deixa apresentável) →
2. **Fechar a 1ª manicure de teste** (mesmo grátis) pra descobrir o que falta de verdade →
3. **Importar contatos + lembrete automático** (o que tira a preguiça dela de migrar e o que a prende no sistema).

---

## 📚 Onde está o resto da história

- `CLAUDE.md` — contexto técnico completo (ler antes de mexer no código)
- `BRIEFING.md` — estratégia de marca, produto e venda
- `README.md` — resumo das páginas e do deploy
