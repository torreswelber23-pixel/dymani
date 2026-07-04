# 💅 Dymani

**Tecnologia · Conexão · Resultados**

Clube de fidelidade e agendamento em tempo real para manicures e studios de beleza.

> 📖 Contexto completo do projeto — história, visão, modelo de negócio,
> arquitetura e status atual: **[CLAUDE.md](CLAUDE.md)**

## Páginas

| Arquivo | O que é |
|---|---|
| `index.html` | Vitrine de vendas do Dymani (pública): o que é, benefícios, **preço (R$29/mês)** e botões para criar o studio ou ver a demo. É a porta de entrada para atrair manicures. |
| `portfolio.html` | Portfólio público estilo Instagram + agendamento em tempo real + link de indicação com pontos. É o link que a manicure divulga. |
| `painel.html` | **App completo da manicure** (com cara de aplicativo, navegação inferior): clientes, selos e Cartão da Unha (editor estilo Canva), agenda, serviços, horários, fotos e perfil. |

## Como funciona

- **Tudo na nuvem (multitenant):** o mesmo sistema serve várias manicures, cada uma com seu studio (slug + PIN). Clientes, selos e cartão, além de agenda/serviços/horários/fotos, moram no Supabase (plano grátis). Trocar de celular não perde nada.
- **Agendamento em tempo real:** horário ocupado aparece riscado pra todo mundo na hora, e duas clientes não conseguem marcar o mesmo horário (o banco recusa a segunda).
- **Login da manicure no painel:** nome do link (slug) + PIN — sem cadastro complicado. A cliente nunca instala nada: só recebe o cartão bonito no WhatsApp e abre o link quando quer agendar.
- **Segurança:** a chave pública (anon key) fica no HTML de propósito. Todo acesso a dado sensível passa por funções `security definer` no Postgres que validam o PIN internamente.

Studio de demonstração já cadastrado no banco: link `studio-demo`, senha `1234`.

Detalhes completos de produto, preço e estratégia de venda: **[BRIEFING.md](BRIEFING.md)**.

## Deploy

Projeto pronto para Vercel: importe este repositório sem nenhuma configuração especial
(raiz padrão, branch padrão `main`) — o `vercel.json` já habilita URLs limpas
(`/portfolio` em vez de `/portfolio.html`).
