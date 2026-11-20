# Baillart Academia de Dança | Link da bio

## Estrutura
- `index.html`: página
- `img/`: fotos, logo, ícones, imagem de compartilhamento (`og-image.jpg`)
- `fonts/`: fontes da página
- `img/depoimentos/`: prints dos comentários (01.jpg, 02.jpg...)
- `apps-script/Codigo.gs`: código da planilha

## 1. Planilha (Apps Script)
1. Abra a planilha > Extensões > Apps Script.
2. Apague o conteúdo, cole o `apps-script/Codigo.gs` e salve.
3. Na barra do editor, selecione a função `configurarPlanilha` e clique em Executar. Autorize com a conta dona da planilha (se aparecer "app não verificado": Avançado > Acessar projeto).
   Resultado: aba "Aulas experimentais" com faixa rosa, cabeçalho preto, linhas zebradas, status com cores e filtro, e aba "Painel" com resumo e gráfico.
4. Opcional: selecione `teste` e execute para ver uma linha de exemplo. Depois apague a linha.
5. Implantar > Nova implantação > engrenagem > App da Web. Executar como: Eu. Quem pode acessar: Qualquer pessoa. Implantar.
6. A URL do App da Web já está no `index.html` (SCRIPT_URL). Se criar uma implantação nova, troque por ela.
7. O aviso por e-mail já vai para agenciafolks1@gmail.com (constante `EMAIL_AVISO`). Na primeira execução o Google pede permissão para enviar e-mails: aceite.
8. Se mexer no código depois: Implantar > Gerenciar implantações > lápis > Versão: Nova versão > Implantar (a URL continua a mesma).

Status disponíveis na coluna J: Novo, Contatado, Aula agendada, Compareceu, Matriculado, Sem resposta.

## 2. GitHub
1. Entre em github.com > New repository > nome `baillartacademia` > Create.
2. Clique em "uploading an existing file" e arraste TODO o conteúdo desta pasta (index.html, img, fonts, apps-script, LEIA-ME.md). Não arraste a pasta em si, só o que está dentro.
3. Commit changes.

## 3. Vercel
1. vercel.com > Add New > Project > Import no repositório `baillartacademia`.
2. Framework Preset: Other. Não precisa de build. Deploy.
3. Settings > Domains: deixe `baillartacademia.vercel.app` (ou o domínio próprio da academia).
4. Se o endereço final for diferente de `https://baillartacademia.vercel.app`, troque esse endereço nas linhas `og:url`, `og:image`, `twitter:image` e `canonical` do `index.html`. Sem isso a prévia do WhatsApp não aparece.
5. Toda alteração enviada ao GitHub publica sozinha na Vercel.

## 4. Prévia no WhatsApp
- O WhatsApp guarda a prévia em cache. Teste o link pela primeira vez já com a versão final.
- Para conferir: https://developers.facebook.com/tools/debug/ > cole o link > "Scrape Again".

## 5. Depoimentos
Salve os prints em `img/depoimentos/` (01.jpg, 02.jpg...) e preencha no `index.html`:
```
const DEPOIMENTOS = [
  { img: 'img/depoimentos/01.jpg', alt: 'Comentário de @usuario' },
];
```
A seção só aparece quando a lista tem itens.

## 6. Instagram
Coloque o link da Vercel na bio. Para saber de onde veio cada cadastro, use variações com `?utm_source=`, por exemplo `...vercel.app/?utm_source=bio` e `...vercel.app/?utm_source=stories`. Aparece na coluna Origem.
