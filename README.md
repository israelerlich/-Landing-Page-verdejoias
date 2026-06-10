# Verde Joias — Landing Page (Eternização)

Landing page da Verde Joias para o serviço de **Eternização**: transformar flores, buquês e memórias afetivas em peças únicas. É uma página estática (HTML, CSS e JavaScript puro, tudo em um arquivo), sem build.

## Estrutura

```
index.html     A página inteira (HTML + CSS + JS)
images/        Imagens usadas pela página
serve.ps1      Servidor local simples para pré-visualizar (PowerShell)
README.txt     Notas do projeto
```

## Rodar localmente

Abra o `index.html` com dois cliques, ou rode um servidor local:

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File serve.ps1
```

Depois acesse `http://localhost:5500`. (A fonte Montserrat vem do Google Fonts, então precisa de internet para a tipografia correta.)

## Formulário de contato

Os botões "Falar pelo WhatsApp" abrem um formulário com **nome, WhatsApp e e-mail**. Ao enviar, acontecem duas coisas:

1. O lead é gravado no banco de dados (**Supabase**, tabela `leads`).
2. A pessoa é direcionada ao WhatsApp da loja com a mensagem já pronta.

A chave do Supabase presente no `index.html` é uma *publishable key* (pública por design). Ela só permite **inserir** leads, protegida por Row Level Security. Não dá acesso de leitura, edição ou exclusão dos dados.

## Publicar

Por ser estática, basta subir `index.html` + a pasta `images/` em qualquer hospedagem estática (Netlify, Vercel, GitHub Pages, etc.). Mantenha `index.html` e `images/` juntos (caminhos relativos).
