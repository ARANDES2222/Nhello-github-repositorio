# NEWSKMUSIC — pacote de desenvolvimento para GitHub

**Versão do pacote:** 0.3.0  
**Estado:** base de frontend demonstrativa + identidade visual oficial + configuração inicial PWA/Capacitor + documentação de execução por IA.

Este repositório reúne os materiais enviados, o starter de interface já criado e um plano de implementação faseado. Ele está organizado para ser enviado ao GitHub e usado como base de desenvolvimento por uma IA especialista ou equipe técnica.

> **Importante:** não é correto chamar o produto de aplicativo completo ainda. A interface atual tem interações locais no navegador. Backend, login real, mensagens, marketplace, pagamentos, VIP, moderação real e painel administrativo protegido ainda precisam ser implementados, configurados e testados. Consulte `STATUS_DO_PROJETO.md`.

## Conteúdo
- `src/`: frontend React + TypeScript.
- `public/assets/brand/`: logo e wallpaper oficiais.
- `public/assets/icons/`: ícones derivados iniciais para web/PWA.
- `supabase/`: estrutura inicial para backend e migrações.
- `docs/ESPECIFICACAO_COMPLETA_NEWSKMUSIC_SEM_CREDENCIAIS.txt`: especificação integral fornecida, com credenciais removidas para segurança.
- `docs/GUIA_MESTRE_PARA_IA_ESPECIALISTA.txt`: instruções para a IA implementar o produto etapa por etapa.
- `docs/PASSO_A_PASSO_GITHUB_E_APLICATIVOS.txt`: tutorial simples para GitHub, PWA, Android e iOS.
- `docs/PROMPTS_POR_ETAPA/`: prompts independentes para cada fase.
- `docs/ADMIN_SETUP.md`: provisionamento seguro das duas administradoras.
- `docs/SECURITY.md`: requisitos de segurança.
- `STATUS_DO_PROJETO.md`: funcionalidades existentes, pendentes e limitações.

## Requisitos para desenvolver
- Node.js LTS atual (recomendado Node 22 ou superior).
- npm e Git.
- GitHub.
- Para Android: Android Studio + Android SDK.
- Para iOS: Mac + Xcode + conta Apple Developer.
- Para backend: projeto Supabase ou serviço equivalente.
- Para publicação web/PWA: hospedagem com HTTPS.

## Rodar no computador
```bash
npm install
cp .env.example .env.local
npm run dev
```
No Windows PowerShell, se `cp` não funcionar:
```powershell
Copy-Item .env.example .env.local
```

## Verificar e gerar build web
```bash
npm run typecheck
npm run build
npm run preview
```
O resultado web é gerado em `dist/`.

## PWA
A configuração inicial do manifesto e service worker está em `vite.config.ts`. Para instalar a PWA em ambiente público, publique o site em domínio com HTTPS e teste no Chrome/Edge/Android. O iOS tem regras próprias de instalação pela opção “Adicionar à Tela de Início”.

## Android
```bash
npm install
npm run build
npx cap add android
npx cap sync android
npx cap open android
```
No Android Studio, configure nome, ícone, splash screen, permissões, assinatura e gere APK de teste ou AAB de publicação. Não coloque keystore/senha no GitHub.

## iOS
Em um Mac com Xcode:
```bash
npm install
npm run build
npx cap add ios
npx cap sync ios
npx cap open ios
```
A compilação, assinatura, TestFlight e App Store exigem ferramentas e credenciais Apple. Não é possível concluir esse processo apenas pelo GitHub ou em um ambiente sem macOS/Xcode.

## Enviar para GitHub
Siga integralmente `docs/PASSO_A_PASSO_GITHUB_E_APLICATIVOS.txt`. Antes de publicar, faça uma busca por senhas, tokens, `.env`, certificados e dados privados. Este repositório foi preparado para ser público; credenciais reais não devem entrar nele.

## Próxima etapa recomendada
Abra `docs/GUIA_MESTRE_PARA_IA_ESPECIALISTA.txt` em uma IA capaz de editar arquivos do projeto. Peça que ela trabalhe uma etapa por vez, execute testes e devolva o ZIP atualizado e a lista de alterações. Não permita que a IA apenas escreva explicações: ela deve modificar os arquivos, testar e relatar limitações.
