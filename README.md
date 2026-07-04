# 💅 Dymani

**Tecnologia · Conexão · Resultados**

Clube de fidelidade e agendamento em tempo real para manicures e studios de beleza.

## Páginas

| Arquivo | O que é |
|---|---|
| `index.html` | App de selos e Cartão da Unha (editor estilo Canva, funciona offline no celular da manicure) |
| `portfolio.html` | Portfólio público estilo Instagram + agendamento em tempo real + link de indicação com pontos |
| `painel.html` | Painel da manicure: agenda com nome/contato de quem agendou, serviços, horários, fotos e perfil |

## Como funciona

- `index.html` guarda os dados no próprio celular (localStorage) — sem servidor, sem custo.
- `portfolio.html` e `painel.html` conectam num banco Supabase (plano grátis) para agendamento em tempo real: horário ocupado aparece riscado pra todo mundo na hora, e duas clientes não conseguem marcar o mesmo horário.
- Login da manicure no painel: nome do link (slug) + PIN — sem cadastro complicado.

Studio de demonstração já cadastrado no banco: link `studio-demo`, senha `1234`.

Detalhes completos de produto, preço e estratégia de venda: **[BRIEFING.md](BRIEFING.md)**.

## Deploy

Projeto pronto para Vercel: importe este repositório sem nenhuma configuração especial
(raiz padrão, branch padrão `main`) — o `vercel.json` já habilita URLs limpas
(`/portfolio` em vez de `/portfolio.html`).
