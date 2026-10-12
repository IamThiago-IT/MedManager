# MedManager 💊

App mobile (Android, iOS e web) para gerenciamento de medicamentos, construído com [Expo](https://docs.expo.dev/versions/v57.0.0/) e `expo-router`.

> Status: base inicial — template Expo 57 com navegação por abas, suporte a tema claro/escuro e componentes tematizados. As funcionalidades de domínio (medicamentos, lembretes, etc.) ainda serão implementadas.

## Stack

| Camada | Versão |
|---|---|
| Expo SDK | `~57.0.11` (CLI `57.0.13`) |
| React / React DOM | `19.2.3` |
| React Native | `0.86.2` |
| expo-router | `~57.0.11` (file-based routing) |
| TypeScript | `~6.0.3` (`strict`) |
| Animações | `react-native-reanimated 4.5.1` + `worklets` |
| Navegação nativa | `react-native-screens`, `safe-area-context`, `gesture-handler` |

Docs de referência: https://docs.expo.dev/versions/v57.0.0/

## Pré-requisitos

- Node.js LTS (testado com `v24.14.1`) + npm (`11.11.0`)
- App **Expo Go** no celular (para teste rápido) ou emulador Android / simulador iOS
- Conta Expo (só necessária para builds EAS, não para rodar local)

## Como rodar

```bash
npm install
npm run dev        # abre o Expo Dev Tools (QR code + atalhos)
```

Com o servidor no ar:

| Tecla | Ação |
|---|---|
| `a` | abrir no Android (emulador/dispositivo) |
| `i` | abrir no iOS (simulador) |
| `w` | abrir no navegador (web) |
| `m` | abrir o dev menu no dispositivo (ou chacoalhar o aparelho) |

Scripts disponíveis:

```bash
npm run dev       # expo start
npm run android   # expo start --android
npm run ios       # expo start --ios
npm run web       # expo start --web
npm run lint      # expo lint
npm run reset-project  # move o template atual e cria um app em branco (irreversível sem git)
```

## Estrutura

```
src/
├── app/               # rotas (expo-router)
│   ├── _layout.tsx    # ThemeProvider + splash + tabs
│   ├── index.tsx      # tela inicial
│   └── explore.tsx    # tela de exemplos do template
├── components/        # app-tabs, themed-text/view, animated-icon,
│   └── ui/            # collapsible, external-link, hint-row, web-badge
├── constants/theme.ts # cores light/dark, Spacing, Fonts
├── hooks/             # use-color-scheme, use-theme
└── global.css         # fontes/variáveis para web
assets/                # ícones, splash, imagens
scripts/               # reset-project.js
app.json               # config Expo (slug medmanager, scheme medmanager)
```

Alias de import: `@/*` → `src/*` (ver `tsconfig.json`).

## Temas e plataformas

- Tema claro/escuro automático via `useColorScheme` + `ThemeProvider` do `expo-router`
- Tokens em `src/constants/theme.ts` (`Colors`, `Spacing`, `Fonts`, `BottomTabInset`, `MaxContentWidth`)
- Componentes com variante `.web.tsx` onde o comportamento difere no navegador

## Próximos passos

- [ ] Definir modelo de dados (medicamento, dose, horário)
- [ ] Telas de domínio (lista, detalhe, cadastro)
- [ ] Lembretes/notificações locais (`expo-notifications`)
- [ ] Persistência local
- [ ] Testes (`jest-expo`) e CI

## Licença

Ver [LICENSE](./LICENSE).
