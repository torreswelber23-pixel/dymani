# 💅 DYMANI — Briefing & Estratégia

> **Tecnologia · Conexão · Resultados**

## 0. Arquitetura da marca (decisão do fundador)

- **Dymani** → a empresa (tecnologia para negócios de beleza)
- **Dymani Clube** → fidelidade (o app de selos/cartão — `index.html`)
- **Dymani Link** → portfólio público (`portfolio.html`)
- **Dymani Agenda** → agendamento em tempo real (dentro do Link + `painel.html`)
- **Dymani Post** → os cartões compartilháveis pro WhatsApp

O nome com **Y** é distintivo, curto, soa internacional e não prende a marca ao nicho de unhas — amanhã cabe cabeleireira, sobrancelha, estética. Logo oficial: `dymani.jpg` (fundo escuro, para o app) e `dymani-clara.jpg` (fundo claro, para WhatsApp/impressos).

⚠️ **Antes de investir pesado na marca:** conferir disponibilidade de domínio (ex: dymani.com.br no Registro.br, ~R$40/ano) e busca prévia no INPI (gov.br/inpi) pra registro de marca. Nome inventado tem boa chance de estar livre, mas confirme antes de gastar com material.

## 1. O produto em uma frase

> Sistema de bolso para manicures que transforma cada unha feita em propaganda (o Cartão da Unha que a cliente exibe) e cada cliente em cliente fiel (selos + lembrete de retorno no dia certo).

## 2. Identidade

- **Nome:** Clube da Unha — "clube" cria pertencimento; a cliente não é freguesa, é sócia.
- **Cores:** rosa vibrante (#ec4899) + roxo profundo (#7c3aed) sobre fundo escuro elegante, dourado nos selos. Visual de "convite chique", não de planilha.
- **Tom de voz:** carinhoso e cúmplice ("suas unhas estão pedindo socorro 💅"), nunca corporativo.
- **Regra de design:** TUDO que a cliente vê tem que ser digno de status do WhatsApp. O produto É bonito ou não é o produto.

## 3. Quem usa

- **Usuária principal (quem paga):** a manicure/nail designer. Atende 30–80 clientes/mês, agenda no caderno ou direct, vive de retorno. Celular Android intermediário.
- **Usuária secundária (quem espalha):** a cliente. Não instala nada, não cadastra nada — só RECEBE coisas bonitas (o cartão) e mensagens na hora certa.

**Decisão estratégica:** só a manicure usa o app. A cliente ter que instalar algo mataria a viralidade — o cartão viaja como IMAGEM pelo WhatsApp, que todo mundo já tem.

## 4. As telas (o app da manicure)

### Tela 0 — Boas-vindas (1ª vez)
Configura em 1 minuto: nome do studio, WhatsApp, dias pro lembrete (padrão 12). Sem cadastro, sem senha, sem e-mail. Fica tudo no celular dela.

### Tela 1 — Início "Minhas clientes"
- Cartão de alerta no topo: **"💅 4 clientes na hora de voltar — chamar agora"** (o coração do produto sempre visível)
- Lista de clientes com busca: nome, selos (ex.: ●●●●●○○○○○ 5/10), dias desde a última unha
- Botão grande: **➕ Novo atendimento**

### Tela 2 — Novo atendimento (usada no fim de cada unha, em 30 segundos)
1. Escolhe a cliente (ou cadastra na hora: nome + WhatsApp)
2. Escreve o serviço/cor ("Alongamento fibra + Vermelho Rubi")
3. **Tira a foto da unha** 📸
4. Salvar → ganha selo automático → vai direto pro Cartão

### Tela 3 — O EDITOR do Cartão ⭐ (a alma do produto, estilo Canva)
A manicure monta o cartão do jeito DELA, em cima da foto da unha:
- **Logo do studio sobre a foto, arrastável com o dedo** — ela posiciona onde quiser, ajusta o tamanho no controle deslizante. A logo fica salva e aparece em todos os cartões seguintes
- **4 temas de cor** (Rosa, Dourado, Vermelho, Lilás) — um toque e o cartão inteiro muda
- **2 estilos:** "Foto inteira" (a unha cobre o cartão todo, textos por cima — o mais bonito pro status) e "Clássico" (moldura com janela de foto)
- **Frase do studio** personalizável ("Unhas feitas com amor ✨")
- Nome da cliente + serviço + data + régua de selos dourados + WhatsApp de agendamento
- Botões: **Enviar pra cliente**, **Salvar imagem** e **⭐ Ela postou! (+1 selo)**

As escolhas ficam salvas: a manicure configura o visual uma vez e depois cada cartão sai pronto em 2 toques.

### 💫 O selo de postagem (o motor viral — ideia do fundador)
A cliente ganha selo de DOIS jeitos:
1. **Fez a unha** → +1 selo (automático)
2. **Postou o cartão no status/Instagram** → +1 selo extra (a manicure confere e toca no ⭐)

Ou seja: a cliente é **recompensada por divulgar o studio**. Ela quer o brinde, posta correndo; a manicure vira assunto nas redes da cidade sem pagar anúncio. O brinde é configurável: 5 ou 10 selos = 1 unha grátis.

### Tela 4 — Quem chamar hoje 🔔
Lista automática: clientes com 12+ dias desde a última unha, mais atrasadas primeiro. Cada uma com botão que abre o WhatsApp com a mensagem pronta:
> "Oi Maria! 💅 Suas unhas já estão pedindo socorro… quer teu horário de sempre, quinta às 14h?"
Um toque por cliente. 5 minutos de manhã = agenda cheia.

### Tela 5 — Ficha da cliente
Histórico visual (as fotos de todas as unhas — o "álbum"), selos, horário de costume, botão de chamar de volta. Na 10ª unha: 🎁 UNHA GRÁTIS estampada no cartão (a manicure dá o brinde, o sistema zera e recomeça).

### Tela 7 — O Painel do Studio 🛠️ (`painel.html` — EM TEMPO REAL via Supabase)
Onde a manicure administra tudo, com login simples (nome do link + PIN):
- **📅 Agenda:** todos os agendamentos por dia, com NOME e WHATSAPP de quem agendou, aviso de indicação ("veio pela Ana — dá o ponto pra ela!"), botão de chamar no zap e de cancelar (horário volta a ficar livre na hora)
- **💅 Serviços:** adiciona/remove serviços e preços
- **⏰ Horários:** define os horários de cada dia da semana
- **📸 Fotos:** sobe as fotos do portfólio com legenda (comprimidas automaticamente)
- **⚙️ Perfil:** nome, bio, WhatsApp, logo e a meta de pontos do brinde
- Mostra o link do portfólio pronto pra copiar e divulgar

**Tempo real de verdade:** os dados moram no Supabase (plano grátis). Horário agendado aparece riscado pra TODO MUNDO na hora; duas clientes não conseguem pegar o mesmo horário (o banco recusa a segunda). Criar studio novo = 1 minuto no próprio painel.html — cada manicure nova é só mandar o link.

### Tela 6 — O Portfólio público 🌐 (`portfolio.html` — ideia do fundador)
A página que a CLIENTE compartilha e o mundo vê (estilo Instagram):
- Perfil com logo, bio e contador de trabalhos
- **Grade de fotos 3 colunas** — toca e expande com legenda + botão "Quero igual — agendar"
- Lista de serviços com preços
- **Agendamento em 3 passos:** serviço → dia (só os dias que ela atende) → horário (ocupados riscados) → mensagem pronta no WhatsApp da manicure
- **Link de indicação:** o botão "⭐ Divulgar e ganhar selos" gera o link pessoal da cliente (`?ind=Maria`). Quem agendar por ele chega dizendo *"Vim pela Maria! (dá o selo pra ela rs)"* — a manicure toca em "💖 Trouxe uma amiga (+1 selo)" na ficha. **Rastreio de indicação sem servidor.**

O ciclo completo: cliente posta o link → amiga vê o portfólio → agenda → quem indicou ganha selo → todas têm motivo pra divulgar. Cada manicure ganha seu `portfolio.html` personalizado (parte do pacote R$29/mês — é você quem configura, fotos e horários).

## 5. Arquitetura

- **Vitrine (`index.html`):** página pública de vendas com o preço — atrai manicures novas e leva pro painel/demo.
- **Painel (`painel.html`):** o app completo da manicure (visual de aplicativo, navegação inferior) — clientes, selos e Cartão da Unha, agenda, serviços, horários, fotos e perfil. **Tudo na nuvem, multitenant** (mesmo sistema serve várias manicures; login = slug + PIN).
- **Portfólio (`portfolio.html`):** a página pública que a cliente compartilha — trabalhos, serviços e agendamento em tempo real.
- **Supabase (plano grátis):** agendamento em tempo real, agenda com contatos, fidelidade e tudo protegido por PIN (tabelas `cu_*`, funções `security definer`). Trocar de celular não perde nada.
- Custo de infraestrutura: **R$0**. Sua margem nos R$29/mês é 100%.
- Experiência: confete 🎊 no agendamento, mensagem de pontos pra quem agenda ("Agendou, pontuou!") e pra quem indica ("vocês duas ganham").

## 6. Preço e oferta

- **Oferta de entrada: R$29/mês, sem taxa de implantação** — barreira mínima, fácil de dizer sim ("menos que um atendimento seu paga 2 meses"). Você configura junto com ela na hora (logo, meta de selos, 10 primeiras clientes) como cortesia.
- Quando tiver casos e depoimentos: R$39/mês ou R$97 de implantação + R$29/mês.
- 20 manicures × R$29 = **R$580/mês recorrentes**. 50 = R$1.450/mês. Essa é a conta que paga aluguel pra sempre.
- **Gatilho de venda:** a conta na frente dela: "40 clientes voltando 5 dias mais cedo = ~20 atendimentos extras por ano. Quanto é teu atendimento? R$45? São R$900 a mais."

## 7. Go-to-market (como vender)

1. **Primeira manicure grátis** — a mais movimentada/seguida do bairro, em troca de depoimento + 3 indicações + poder citar o nome.
2. A abordagem é pela DOR DE RETORNO, nunca por "tecnologia": *"Quantas clientes tuas sumiram há mais de 20 dias? O sistema te mostra quem e te dá o botão pra chamar."*
3. **Demo teatral:** na frente dela, cadastre ELA como cliente, tire foto da unha DELA e gere o cartão com o nome do studio dela. Ver o próprio nome no cartão chique fecha a venda.
4. Manicures se conhecem: comissão de R$30 por indicação fechada.
5. Onde achar: Instagram (`#unhas[cidade]`, `#naildesigner[cidade]`), grupos femininos da cidade, e o Maps (studios de unha com avaliação alta).

## 8. Roadmap (só depois de 10 pagantes)

- **v2:** backend (Supabase) → lembrete 100% automático sem a manicure abrir o app, agendamento online pela cliente
- **v3:** provador virtual de esmalte com IA ("vê a cor na TUA mão") — o wow que vira marketing nacional
- **v4:** rede: perfil público da manicure com álbum de trabalhos = o "iFood da unha" da cidade

## 9. Métricas de validação (primeiras 4 semanas)

- 3 manicures usando ≥ 3x/semana? → produto pegou
- Clientes postando o cartão no status? → viralidade confirmada
- Alguma manicure PERGUNTANDO se pode pagar antes de você cobrar? → aumenta o preço
