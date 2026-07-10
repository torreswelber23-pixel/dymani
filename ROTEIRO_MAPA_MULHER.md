# 🗺️ Mapa Mulher + Dymani — Roteiro de Construção e Vendas

> Manual vivo. A ideia grande: **um marketplace de manicures divulgado por QR nos carros de app**, rodando em cima do Dymani que já existe. Sem sorteio de dinheiro (isso é ilegal sem licença federal). A gamificação é o **clube de selos** que o Dymani já tem.
>
> Última atualização: **07/07/2026**

---

## 🎯 A ideia em uma frase

A passageira escaneia um QR no encosto do banco → cai no **Mapa Mulher** (vitrine com **todas** as manicures da cidade) → filtra por bairro → escolhe uma → vê os trabalhos e **agenda na hora**. O motorista que trouxe a cliente ganha comissão. A manicure paga uma assinatura pra aparecer.

Três peças, e **todas já existem ou são baratas**:

1. **A vitrine de cada manicure** → `portfolio.html` (pronto)
2. **O marketplace que junta todas** → `mapa.html` (feito agora)
3. **O canal de divulgação** → banner de QR no carro (só imprimir)

---

## ⚖️ O que NÃO fazer (pra não virar caso de polícia)

- ❌ **Sorteio de dinheiro amarrado à Loteria Federal.** Isso é "promoção comercial" e exige autorização da SECAP/Ministério da Fazenda. Sem licença = contravenção penal. **Fora.**
- ❌ **Prêmio em dinheiro** de qualquer tipo por sorteio.
- ✅ **O que pode:** clube de fidelidade por **selos** (a cliente junta X unhas e ganha **uma unha grátis** — brinde do próprio serviço, não dinheiro). Isso o Dymani já faz e é 100% legal.
- ✅ Cupom de parceiro (pizzaria etc.) **pode**, desde que seja desconto direto do parceiro e não sorteio. Cuidado com disparo em massa no WhatsApp (risco de banir o número).

---

## ✅ O que já está pronto (hoje)

- [x] Vitrine individual da manicure com agendamento em tempo real (`portfolio.html`)
- [x] Painel completo da manicure — clientes, selos, cartão da unha, agenda (`painel.html`)
- [x] **Marketplace `mapa.html`** — lista todos os salões, busca por nome, **filtro por bairro**, e carrega o `?carro=` pra atribuir o motorista
- [x] Banco preparado: campos **bairro/cidade** no studio + função `cu_studios_listar` (lista leve, sem PIN, sem foto pesada)
- [x] Campo de **bairro e cidade** no perfil do painel (a manicure preenche e já entra no filtro)

---

## 🧭 As fases (uma de cada vez)

### Fase 0 — Base técnica ✅ (feita)
Marketplace no ar, lendo os salões do banco. Cada manicure nova cai na vitrine sozinha.

### Fase 1 — Encher a oferta 🔥 (é AQUI que está o gargalo)
Marketplace vazio não vende. **Antes de imprimir 1 banner**, cadastre manicure de verdade.
- Meta mínima pra ligar o carro: **8–10 manicures ativas** numa mesma cidade (Macapá/Santana).
- Ferramenta: o próprio painel. Você cadastra junto com ela em 5 min (demo teatral — ver abaixo).
- Primeiro mês **grátis** pra alimentar a base. Cada uma preenche bairro, fotos e horários.

### Fase 2 — Ligar o canal do carro 🚗
- Manda imprimir banner de acrílico/adesivo com o QR do `mapa.html?carro=NOME_DO_MOTORISTA`.
- 5–15 motoristas parceiros no começo. Cada um com **seu** código no QR.
- O QR aponta pro marketplace, não pra um salão só — a passageira vê todas as opções do bairro dela.

### Fase 3 — Comissão do motorista (manual primeiro) 🤝
- O `?carro=` já viaja do marketplace até o agendamento. Você **vê** quem trouxe a cliente.
- No começo, **paga o motorista na mão** (Pix seu, olhando a lista). Zero sistema.
- Só automatiza quando tiver volume que justifique.

### Fase 4 — Pagamento dentro da plataforma 💳 (POR ÚLTIMO)
Só depois de ter manicures usando e clientes agendando de verdade.
- Pix (Copia e Cola / QR dinâmico) via gateway (Mercado Pago, Asaas ou OpenPix).
- Split automático (parte plataforma / parte motorista) — exige cadastro/KYC de cada recebedor. **É a parte mais chata; deixe pro fim de propósito.**
- Webhook confirma pagamento → libera o agendamento.
- **Não construa isso agora.** Sinal de que chegou a hora: manicure pedindo "como recebo antecipado?" e cliente perguntando "posso pagar por aqui?".

---

## 💰 Preço e divisão (proposta)

- **Assinatura da manicure:** R$ 29 a R$ 60/mês (começa em 29 pra baixar a barreira; sobe quando tiver prova de resultado).
- **Taxa por agendamento pago (só na Fase 4):** algo simbólico (ex: R$ 2–3), com uma parte indo pro motorista.
- **Regra de ouro:** a assinatura é o negócio de verdade e o que paga a conta. A taxa e a comissão são o combustível do canal do carro, não a fonte principal.

---

## 🗣️ BASE DE VENDAS — argumentos por pessoa

### Para a MANICURE (quem paga)
A dor dela: cliente some, agenda é bagunça no WhatsApp, e ela depende de indicação boca a boca.

- **"Você aparece pra quem tá passando na sua região agora."** O carro leva sua vitrine pra passageira que nem te conhece.
- **"Suas clientes voltam sozinhas."** O clube de selos faz a cliente querer juntar pra ganhar a unha grátis, e o sistema te avisa quem sumiu.
- **"Cada unha vira propaganda."** O Cartão da Unha que a cliente posta no status marca seu studio — divulgação de graça.
- **"Sem instalar nada, tudo pelo celular, e o primeiro mês é grátis."**

**Frase de fechamento:** *"Você não paga por um sistema. Você paga pra parar de perder cliente. Se em um mês não trouxer nada, cancela e não me deve nada."*

### Para o MOTORISTA (o afiliado que divulga)
A dor dele: tempo parado no trânsito e renda só da corrida.

- **"Você ganha sem fazer nada além de colar um adesivo."** A passageira escaneia, agenda, você recebe comissão.
- **"É renda extra em cima de um assento que já tá aí."**
- **"O código é seu. Toda cliente que vier do seu carro conta pra você."**

### Para a CLIENTE/PASSAGEIRA (quem usa)
A dor dela: tá presa no trânsito, sem tempo, e queria arrumar a unha.

- **"Enquanto você vai pro trabalho, já deixa sua unha marcada."**
- **"Vê os trabalhos de verdade antes de escolher."**
- **"Agenda, junta selo e ganha unha grátis."**

---

## 🎭 Roteiro de abordagem da manicure (demo teatral)

O que mais fecha venda: **cadastrar ela na sua frente e mostrar o resultado com o nome dela.**

1. Abre o painel e cria o studio dela ali na hora (nome, bairro, 1 serviço, 1 foto do trabalho dela).
2. Mostra o **portfólio público** dela pronto, com o link.
3. Abre o **Mapa Mulher** e mostra ela aparecendo na vitrine, no bairro dela.
4. Faz um cartão da unha de brincadeira com o nome de uma cliente → "é isso que sua cliente vai postar no status".
5. Fecha: *"Deixo você um mês pra testar de graça. Só me manda uma foto de trabalho por dia pra encher seu perfil."*

---

## 🛡️ Respostas pras objeções

- **"Não tenho tempo pra mexer em sistema."** → *"Você só tira a foto e manda pro WhatsApp da cliente, igual já faz. O resto o sistema faz."*
- **"Minha cliente não vai usar app."** → *"Ela não instala nada. Só recebe a foto bonita e clica num link quando quer marcar."*
- **"Já tenho agenda no caderno."** → *"Ótimo — esse aqui te avisa quem sumiu e traz cliente nova. O caderno não faz isso."*
- **"E se não der certo?"** → *"Primeiro mês grátis. Zero risco pra você."*

---

## 🚦 Próximo passo (o único que importa agora)

**Sair e cadastrar as 3 primeiras manicures reais em Macapá/Santana** — de graça, com a demo teatral acima. Cada uma que entra já aparece no Mapa Mulher.

O sistema já está pronto pra receber. O que falta não é código — é **oferta**.

---

## 📁 Arquivos do projeto

- `index.html` — vitrine de vendas do Dymani (página que vende o sistema pra manicure)
- `mapa.html` — **marketplace Mapa Mulher** (todas as manicures + filtro por bairro + `?carro=`)
- `portfolio.html` — vitrine pública de UMA manicure + agendamento
- `painel.html` — app da manicure (clientes, selos, cartão, agenda, perfil c/ bairro)
- `CLAUDE.md` / `ESTADO.md` — contexto técnico e estado do projeto
