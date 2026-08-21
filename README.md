# Sequence Image to PDF
 
Página HTML única (sem instalação, sem backend) para colar imagens da área de transferência e gerar um PDF com elas, na mesma ordem em que foram adicionadas.
https://paralhama.github.io/Sequence-Images-to-PDF/
 
## Funcionalidades
 
- **Colar (Ctrl+V / Cmd+V)** uma imagem da área de transferência em qualquer lugar da página
- **Arrastar e soltar** arquivos de imagem
- **Selecionar arquivos** pela pasta (clicando na área de upload)
- Pré-visualização das imagens em ordem, numeradas
- **Reordenar** arrastando um card sobre outro
- **Remover** uma imagem individual ou limpar tudo
- Geração do PDF em dois modos:
  - **Ajustar à imagem** — cada página do PDF nasce na mesma proporção da imagem (retrato/paisagem automático), sem cortes e sem faixas brancas
  - **Papel A4** — páginas em A4 padrão, com orientação **Automática**, **Retrato** ou **Paisagem** (força a mesma orientação em todas as páginas)
## Como usar
 
1. Abra o arquivo `colar-imagens-pdf.html` em qualquer navegador moderno (Chrome, Edge, Firefox)
2. Cole, arraste ou selecione as imagens na ordem desejada
3. (Opcional) Arraste os cards para reordenar, ou remova alguma imagem
4. Escolha o modo de página no rodapé (Ajustar à imagem / Papel A4)
5. Clique em **Gerar PDF** — o download começa automaticamente
## Requisitos
 
- Navegador moderno com suporte a `Clipboard`, `Canvas` e `File API`
- Conexão com a internet na primeira execução, para carregar a biblioteca [jsPDF](https://github.com/parallax/jsPDF) via CDN (`cdnjs.cloudflare.com`)
## Como funciona (resumo técnico)
 
- Cada imagem colada/arrastada é desenhada em um `<canvas>` com fundo branco (para achatar transparência) e convertida em JPEG (`toDataURL`)
- A geração do PDF é feita 100% no navegador com **jsPDF**, sem enviar nenhuma imagem para servidor algum
- Nenhum dado é salvo — ao recarregar a página, a lista de imagens é perdida
## Estrutura do projeto
 
```
colar-imagens-pdf.html   # tudo em um único arquivo (HTML + CSS + JS)
README.md                # este arquivo
```
 
## Limitações conhecidas
 
- Não há persistência entre sessões (recarregar a página apaga as imagens adicionadas)
- Requer internet para carregar o jsPDF via CDN na primeira vez
- Testado em navegadores desktop; em mobile o "colar" depende do suporte do navegador ao evento de paste
## Possíveis melhorias futuras
 
- Permitir nomear o arquivo PDF antes de gerar
