# Registro online — Carrinhos de Chromebooks

Sala de informática · registro online por carrinho e aula. 6 carrinhos · 40 Chromebooks cada · 240 no total (CB-001 a CB-240).

Redesign **Operate / Restrained** aplicando as 3 skills:

- **Apple Design**: topbar em material translúcido (`backdrop-filter` + conteúdo rolando por baixo), feedback no `pointer-down` (`:active scale .97`), tipografia com tracking/leading por tamanho, `prefers-reduced-motion / transparency / contrast`, enter/exit de dialogs no mesmo caminho.
- **Emil Design**: só anima o ocasional, easing custom `--ease-out: cubic-bezier(.23,1,.32,1)`, durações 160–280ms (<300ms), só `transform/opacity/filter`, nunca `scale(0)`, `@starting-style`, blur 2px p/ mascarar crossfade, stagger 40–135ms.
- **Impeccable**: sem `border-left` colorida 6px, sem emoji como ícone (SVG inline), sem hero-metric em cards idênticos (resumo em barra segmentada), raios 14–16px, browser surfaces temadas (`::selection`, scrollbar, focus, `tabular-nums`), empty state que ensina + skeleton de loading, uma família tipográfica.

## Rodar local

```bash
# só um estático — pode abrir o index.html ou servir:
npx serve .
# ou
python3 -m http.server 8000
```

## Deploy na Vercel

Framework `Other`, sem build. Rota `/` serve o `index.html`.

```bash
vercel --prod
```

## Firebase

As chaves já estão em `index.html` (`FIREBASE_CONFIG`, projeto `controle-de-chrome`, coleção `retiradas`). Regras do Firestore precisam permitir leitura/escrita da sala.
