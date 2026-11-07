# BakeBum! — página de login

Página pública de login do **BakeBum!** (GitHub Pages), no mesmo
desenho dos outros jogos do Daniel (Mescla Pokémon / Mescla
Elemental):

**https://danieldss90.github.io/bakebum-login/**

## Como funciona

1. O jogo abre esta página com `?code=<uuid>` (botão ENTRAR).
2. A página faz login pelo **Supabase Auth** — Google (OAuth) ou
   e-mail/senha (cadastro sem confirmação de e-mail).
3. Ao logar, a página grava o perfil (nome, foto, e-mail)
   amarrado ao código na tabela compartilhada `player_profiles`
   e avisa: "Pronto! Pode voltar ao BakeBum!".
4. O jogo busca o perfil pela RPC `get_login_profile` em polling
   (~3 s, até ~2 min) e passa a exibir o chip do jogador.

Aberta sem código, a página só orienta a abrir pelo jogo.

- `index.html` — a página de login (a publishable key do Supabase
  é pública por design; nenhuma chave secreta mora aqui).
- `privacy.html` — política de privacidade própria do BakeBum!
  (exigida pela tela de consentimento do Google).

O desenho completo (tabelas, RPCs e o checklist de painel) está
em `docs/LOGIN_E_PLACAR.md` no repositório do jogo
(`Danieldss90/bakebum`).
