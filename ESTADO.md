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
