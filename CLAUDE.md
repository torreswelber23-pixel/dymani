# Dymani — contexto completo do projeto

> Este arquivo existe para que qualquer IA (ou humano) que abra este repositório
> entenda em 5 minutos tudo que uma longa conversa construiu: de onde isso veio,
> por que existe, o que já está pronto, e para onde vai. Se você é uma IA lendo
> isto para continuar o trabalho: leia inteiro antes de tocar em código.

## 1. Quem é o dono e por que isso existe

Welber Torres é programador, usa IA para desenvolver, e **só tem o celular** —
sem computador, trabalhando pelo Termux (terminal Linux no Android). O gatilho
do projeto foi urgência financeira real: precisava de dinheiro para comer e
tinha acabado de alugar uma residência por R$250 (15 dias), sem ter como pagar.
A pergunta inicial foi literalmente "como ganho dinheiro programando, só com
celular, agora".

Isso importa porque toda decisão técnica deste projeto respeita uma restrição:
**zero custo de infraestrutura, zero necessidade de computador, tudo operável
pelo dono direto do celular.** Não é escolha de estilo — é a única forma de o
negócio existir.

## 2. A jornada (como chegamos até aqui)

1. **Vitrine Digital** — primeiro produto: sites simples para pequenos negócios
   locais (R$97→147), hospedados de graça no GitHub Pages, vendidos porta a
   porta / WhatsApp. Existe em outro contexto (repositório `bb`), não faz mais
   parte deste repo.
2. **Estratégia de vendas** — descobrimos junto que "vender site" é commodity;
   a virada foi vender *resultado* ("pare de perder cliente no WhatsApp"),
   com personas simuladas (pizzaria, marmitaria, barbearia, manicure) e um
   funil de conversão detalhado (escada de micro-sins, follow-up de 4 toques,
   proteção do número de WhatsApp contra banimento).
3. **RifaFácil** — segundo produto, também fora deste repo: app de rifas pelo
   WhatsApp sem servidor.
4. **A virada para manicures** — o dono pediu algo pensado especificamente
   para manicures que querem fidelizar cliente, com um "algo genial" que faria
   as próprias clientes perguntarem às suas manicures "por que você não tem
   isso?". Nasceu o conceito: transformar o **momento de exibição da unha
   pronta** (toda mulher ama mostrar a unha nova) na própria máquina de
   retorno da manicure. Esse é o produto que virou **Dymani**, e é o que este
   repositório contém.
5. **Evolução do produto**, tudo por pedido explícito do dono, nesta ordem:
   - Cartão da Unha compartilhável com selos de fidelidade
   - Editor **estilo Canva**: logo do studio arrastável com o dedo sobre a
     foto, temas de cor, estilos de layout, frase personalizável
   - Ponto/selo por **postar** o cartão (não só por fazer a unha) — o motor
     viral: a cliente é recompensada por divulgar
   - Portfólio público **estilo Instagram** (grade de fotos, perfil, bio)
   - **Agendamento em tempo real** (Supabase): horário ocupado risca pra todo
     mundo na hora; duas clientes não conseguem marcar o mesmo horário
   - **Link de indicação**: cliente gera seu link pessoal; quem agenda por
     ele dá ponto pra quem indicou também ("vocês duas ganham pontos")
   - **Painel da manicure**: login simples (link + PIN), agenda com nome e
     WhatsApp de quem marcou, edição de serviços/horários/fotos/perfil
   - Confete 🎊 ao concluir agendamento; mensagens sempre em tom carinhoso
6. **A marca Dymani** — o dono gerou duas artes de logo (mesma arte, fundo
   claro e escuro) com o nome "DYMANI" e pediu para eu decidir/aplicar. O "Y"
   foi escolhido por soar mais moderno/internacional que "Dimany" e por não
   prender a marca só ao nicho de unhas. Arquitetura de marca definida pelo
   próprio dono: **Dymani** (empresa) → **Dymani Clube** (fidelidade) →
   **Dymani Link** (portfólio) → **Dymani Agenda** (agendamento) →
   **Dymani Post** (os cartões). Ver `BRIEFING.md` para o detalhe completo.
7. **Este repositório separado** — o produto nasceu dentro do repositório
   `bb` (pasta `clubedaunha/`, branch `claude/mobile-programming-income-6dg5hz`),
   que por sua vez tinha OUTRO projeto do dono (não relacionado — um "Site de
   Promoções" e um conceito chamado "WozOS") na branch padrão. Isso criava
   ambiguidade na hora de publicar no Vercel (o importador só lê a branch
   padrão do repositório). Em vez de misturar os dois negócios, criamos este
   repositório dedicado (`torreswelber23-pixel/dymani`), com o código do
   Dymani direto na raiz, sem pasta e sem branch especial — decisão do
   próprio dono ("bora passar isso pra outra pasta no Git, outro projeto").

## 3. Visão do produto — por que ele é bom

A dor real: **manicure vive de retorno**, mas não tem tempo nem jeito de
cobrar volta, e cliente ama mostrar a unha nova mas isso nunca virou trabalho
de divulgação organizado pra quem fez o serviço. O Dymani junta as duas
pontas: o **Cartão da Unha** dá à cliente algo bonito o suficiente pra ela
*querer* postar (vaidade genuína, não favor), e cada postagem/agendamento gera
pontos — pra quem faz a unha e pra quem indica. A manicure ganha divulgação
grátis a cada atendimento e uma lista automática de "quem chamar hoje".

Diferencial deliberado: **só a manicure "usa" um app** (`painel.html`). A
cliente nunca instala nada — ela só recebe imagens bonitas no WhatsApp e abre
um link quando quer agendar. Isso é o que permite a viralidade: fricção zero
para quem divulga.

## 4. Modelo de negócio

- Entrada: **R$29/mês, sem taxa de implantação** (o dono configura junto com
  a manicure na primeira vez, como cortesia) — decisão do dono para baixar a
  barreira de entrada.
- Evolução prevista: R$39/mês ou R$97 de implantação + R$29/mês, uma vez que
  existam casos reais e depoimentos.
- Meta: 20 manicures = R$580/mês recorrentes; 50 = R$1.450/mês.
- Go-to-market: primeira manicure de graça (a mais visível do bairro) em
  troca de depoimento + indicações; demo teatral (cadastrar a própria
  manicure na frente dela, ver o cartão com o nome dela, fecha a venda).
  Detalhe completo em `BRIEFING.md`.

## 5. Arquitetura técnica

| Arquivo | Função | Onde vivem os dados |
|---|---|---|
| `index.html` | App de selos / Cartão da Unha (editor estilo Canva) | `localStorage` do celular da manicure — sem servidor |
| `portfolio.html` | Página pública (estilo Instagram) + agendamento | Supabase (tempo real) |
| `painel.html` | Painel administrativo da manicure | Supabase (tempo real) |

**Backend (Supabase, plano grátis, projeto `rhveqvlldliccalfsuea`, o mesmo
projeto onde mora o "Site de Promoções" do dono — projetos diferentes,
mesmo banco, tabelas isoladas por prefixo `cu_`):**

- Tabelas: `cu_studios` (perfil, PIN, serviços, horários, fotos, meta de
  pontos), `cu_agendamentos` (studio, serviço, dia, hora, nome, zap,
  indicou — com `unique(studio, dia, hora)` que impede double-booking)
- RLS habilitado, **sem policies diretas** — todo acesso passa por funções
  `security definer`: `cu_studio_publico` (perfil sem o PIN),
  `cu_ocupados` (horários do dia), `cu_agendar` (cria agendamento, devolve
  `'ocupado'` se o horário já foi tomado), `cu_agenda` (lista completa,
  exige PIN certo), `cu_salvar_studio` (cria/atualiza, exige PIN),
  `cu_cancelar` (exige PIN)
- Login da manicure = **slug do link + PIN numérico**, sem cadastro/e-mail
- Chave pública (`anon key`) embutida no HTML — isso é esperado e seguro:
  toda escrita sensível passa pelas funções acima, que validam o PIN
  internamente no Postgres

**Hosting:** Vercel, projeto de nome `dymani` (conta "convitefy's projects",
que é a conta real de freelancer do dono com ~20 outros projetos). `vercel.json`
habilita URLs limpas (`/portfolio` em vez de `/portfolio.html`).

Studio de demonstração já existe no banco: slug `studio-demo`, PIN `1234`.

## 6. Limitações de plataforma descobertas (importante para não repetir tentativas)

Durante o desenvolvimento, ficou provado por tentativa real (não suposição)
que a integração de IA disponível **não consegue**:
- Fazer login em Vercel/GitHub por conta do usuário (exige sessão dele)
- Criar projeto novo no Vercel via API/MCP, nem mudar Production Branch ou
  Root Directory de um projeto existente (só ferramentas de leitura: listar
  projetos, ver deployments, ver logs — confirmado mesmo depois do usuário
  liberar permissões extras)
- Criar repositório novo no GitHub via API (403 "Resource not accessible by
  integration") nem mudar visibilidade (privado/público) de um repositório
  existente
- Instalar/autenticar a CLI do Vercel no sandbox (sem token disponível)

Essas ações continuam precisando de **2-3 toques manuais do dono** no
navegador. Não vale tentar de novo sem uma mudança real de permissões — já
foi verificado exaustivamente.

## 7. Status atual (no momento em que este arquivo foi escrito)

- ✅ Código completo e testado (Playwright, sem erros de JS) nas 3 páginas
- ✅ Marca Dymani aplicada (logos, nomenclatura)
- ✅ Backend Supabase criado, testado via SQL direto (criar studio, agendar,
  conflito de horário, PIN certo/errado — tudo validado)
- ✅ Repositório próprio criado e com o primeiro push feito
- ⏳ Repositório está **privado** — precisa virar público (o dono faz manualmente,
  ver Settings → Danger Zone → Change visibility)
- ⏳ Projeto Vercel `dymani` foi criado a partir do repositório ERRADO (`bb`,
  branch/pasta trocadas) — o dono precisa apagar esse projeto e reimportar
  apontando para este repositório (`torreswelber23-pixel/dymani`), que não
  precisa de nenhuma configuração especial (tudo já está na raiz, branch
  `main` padrão)
- ⏳ Ainda não vendido para nenhuma manicure de verdade

## 8. Próximos passos / meta

1. Terminar a publicação (repo público + Vercel apontando certo)
2. Validar com 1-3 manicures reais (de graça/barato, em troca de depoimento)
3. Confirmar sinais de tração: manicure usando ≥3x/semana, cliente postando
   o cartão no status, alguém perguntando se pode pagar antes de cobrar
4. Se validar: subir preço, cobrar manutenção recorrente, buscar domínio
   próprio (checar antes disponibilidade no INPI e em registradores —
   `dymani.com`/`dymani.com.br` já estão ocupados por terceiros; `dymani.app`
   estava disponível)
5. Roadmap de produto (só depois de ter pagantes, nunca antes):
   provador virtual de esmalte com IA, perfil público agregando várias
   manicures da cidade

## 9. Como continuar (se você é uma IA retomando este projeto)

- O dono se comunica em português informal, muitas vezes por voz
  (fala/digita corrido — interprete o sentido, não só a gramática literal)
- Ele prefere que eu **decida e aja**, não que eu só liste opções — mas pausa
  e pergunta antes de qualquer ação irreversível ou que mexa em outro projeto
  dele
- Sempre que possível, **construa e teste de verdade** (Playwright/Chromium)
  antes de reportar algo como pronto — é assim que este projeto inteiro foi
  construído, nunca "no papel"
- Este repositório é autocontido: não depende mais do repositório `bb`
- Antes de qualquer mudança de infraestrutura (Vercel, domínio, banco),
  releia a seção 6 para não repetir tentativas já sabidamente impossíveis
