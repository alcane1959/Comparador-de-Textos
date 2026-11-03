# Comparador de Textos

Aplicação web executada diretamente no navegador para comparar duas versões de um texto, caractere por caractere. O projeto permite colar, editar ou importar documentos e destaca automaticamente inclusões, alterações e remoções.

## Funcionalidades

- Comparação de textos em tempo real.
- Destaque visual de trechos incluídos, alterados e removidos.
- Contagem de inclusões, remoções e blocos alterados.
- Importação de arquivos nos formatos `DOCX`, `PDF` e `TXT`.
- Edição direta do texto alterado.
- Botões para colar, limpar e inverter os textos.
- Exportação do texto alterado ou da comparação por meio da janela de impressão do navegador.
- Layout responsivo para computadores e dispositivos móveis.
- Suporte automático aos temas claro e escuro do sistema.
- Recursos básicos de acessibilidade, incluindo mensagens de status e navegação por controles nativos.

## Tecnologias utilizadas

- HTML5
- CSS3
- JavaScript
- [jsdiff](https://github.com/kpdecker/jsdiff) para comparação caractere por caractere
- [Mammoth.js](https://github.com/mwilliamson/mammoth.js) para extração de texto de arquivos DOCX
- [PDF.js](https://mozilla.github.io/pdf.js/) para extração de texto de arquivos PDF

## Como executar

1. Baixe ou clone este repositório.
2. Mantenha o arquivo `index.html` na pasta do projeto.
3. Abra o arquivo `index.html` em um navegador moderno.

Também é possível executar o projeto com um servidor local. Por exemplo, se você tiver Python instalado:

```bash
python -m http.server 8000
```

Depois, acesse `http://localhost:8000` no navegador.

> O carregamento das bibliotecas externas depende de uma conexão com a internet.

## Como usar

1. Insira o conteúdo de referência no campo **Texto original**.
2. Insira ou edite a nova versão no campo **Texto alterado, editável**.
3. Consulte o resultado na seção **Comparação em tempo real**.
4. Use os indicadores para verificar a quantidade de inclusões, remoções e blocos alterados.
5. Para gerar um PDF, selecione uma das opções de exportação e escolha **Salvar como PDF** na janela de impressão.

### Legenda da comparação

- **Amarelo:** conteúdo incluído ou alterado.
- **Vermelho e riscado:** conteúdo removido.

## Importação de arquivos

### TXT

O conteúdo é lido diretamente pelo navegador.

### DOCX

O texto é extraído com Mammoth.js. A importação prioriza o conteúdo textual, portanto elementos avançados de formatação podem não ser preservados.

### PDF

O texto é extraído com PDF.js. O aplicativo tenta reconstruir recuos, quebras de linha, parágrafos e linhas em branco com base na posição dos elementos internos do PDF.

> PDFs digitalizados como imagem precisam passar por OCR antes da importação, pois o projeto não realiza reconhecimento óptico de caracteres.

## Exportação para PDF

O projeto oferece duas opções:

- **Exportar PDF - texto editável:** imprime somente a versão alterada.
- **Exportar PDF - comparação:** imprime o resultado com os destaques das diferenças.

A exportação utiliza o recurso de impressão do navegador. Na janela exibida, selecione **Salvar como PDF**.

## Estrutura do projeto

```text
.
├── index.html
└── README.md
```

Toda a interface, os estilos e a lógica da aplicação estão concentrados no arquivo `index.html`.

## Dependências externas

As dependências são carregadas por CDN:

- jsdiff 5.2.0
- Mammoth.js 1.13.0
- PDF.js 3.11.174

Para uso totalmente offline, baixe essas bibliotecas, armazene-as no projeto e atualize os caminhos das tags `<script>` no arquivo `index.html`.

## Compatibilidade

Recomenda-se utilizar uma versão atualizada de navegadores como Microsoft Edge, Google Chrome, Mozilla Firefox ou Safari. A função **Colar** pode depender das permissões de acesso à área de transferência concedidas pelo navegador.

## Limitações conhecidas

- A qualidade da extração de PDFs varia conforme a estrutura interna do documento.
- PDFs compostos apenas por imagens não são processados sem OCR prévio.
- A importação de DOCX extrai o texto, mas não reproduz toda a formatação original.
- Arquivos muito grandes podem levar mais tempo para importar e comparar.
- As bibliotecas externas não serão carregadas sem internet, a menos que sejam instaladas localmente.

## Privacidade

O processamento dos textos e arquivos ocorre no navegador. Este projeto não contém código próprio para enviar os documentos a um servidor. As bibliotecas de terceiros são carregadas por CDN durante a abertura da página.

## Licença

Este projeto ainda não possui uma licença definida. Para permitir reutilização, modificação e distribuição, adicione um arquivo `LICENSE` e informe nesta seção a licença escolhida.

## Autor

Desenvolvido por Alberto de Campos Neto.
