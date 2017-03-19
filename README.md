<br>

![vim-galore](https://raw.githubusercontent.com/mhinz/vim-galore/master/contents/images/logo-vim-galore.png)

<br>

[![Build Status](https://travis-ci.org/mhinz/vim-galore.svg?branch=master)](https://travis-ci.org/mhinz/vim-galore)
[![badge-original-version](https://img.shields.io/badge/Version-Original-blue.svg)](https://github.com/mhinz/vim-galore)
[![badge-translation-japanese](https://img.shields.io/badge/Translation-Japanese-lightgrey.svg)](http://postd.cc/?s=vim-galore)
[![vim-galore](https://cdn.rawgit.com/mhinz/vim-galore/master/contents/images/badge-awesome.svg)](https://github.com/sindresorhus/awesome)

## [Introdução](#introdução-1)

- [O que é o Vim?](#o-que-é-o-vim)
- [A filosofia do Vim](#a-filosofia-do-vim)
- [Primeiros passos](#primeiros-passos)
- [Vimrc mínimo](#vimrc-mínimo)
- [Que tipo de Vim eu estou rodando?](#que-tipo-de-vim-eu-estou-rodando)
- [Planilhas de cola](#planilhas-de-cola)

## [O básico](#o-básico-1)

- [Buffers, janelas, abas](#buffers-janelas-abas)
- [Buffer ativos, carregados, listados e nomeados](#buffer-ativos-carregados-listados-e-nomeado)
- [Lista de argumentos](#lista-de-argumento)
- [Mapeamentos](#mapeamentos)
- [A tecla líder](#a-tecla-líder)
- [Registradores](#registradores)
- [Alcances](#alcances)
- [Marcadores](#marcadores)
- [Autocomplementação](#autocomplementação)
- [Movimentos, operadores, objetos de texto](#Movimentos-operadores-objetos-de-texto)
- [Autocmds](#autocmds)
- [Lista de alterações, lista de pulos](#lista-de-alterações-lista-de-pulos)
- [Árvore do desfazer](#árvore-do-desfazer)
- [Listas de conserto rápido e de localização](#listas-de-conserto-rápido-e-de-localização)
- [Macros](#macros)
- [Esquemas de cores](#esquemas-de-cores)
- [Dobraduras](#dobraduras)
- [Sessões](#sessões)
- [Localidade](#localiade)

## [Utilização](#Utilização-1)

- [Conseguir ajuda desconectado](#conseguir-ajuda-desconectado)
- [Conseguir ajuda desconectado (alternativa)](#conseguir-ajuda-desconectado-alternativa)
- [Conseguindo ajuda conectado](#Conseguindo ajuda conectado)
- [Autocmds in practice](#autocmds-in-practice)
  - [User events](#user-events)
  - [Nested autocmds](#nested-autocmds)
- [Clipboard](#clipboard)
  - [Clipboard usage (Windows, OSX)](#clipboard-usage-windows-osx)
  - [Clipboard usage (Linux, BSD, ...)](#clipboard-usage-linux-bsd-)
- [Restore cursor position when opening file](#restore-cursor-position-when-opening-file)
- [Manipulando os arquivos de backup, swap, undo, e viminfo](#manipulando-os-arquivos-de-backup-swap-undo-e-viminfo)
- [Editing remote files](#editing-remote-files)
- [Managing plugins](#managing-plugins)
- [Block insert](#block-insert)
- [Running external programs and using filters](#running-external-programs-and-using-filters)
- [Cscope](#cscope)
- [MatchIt](#matchit)

## [Tips](#tips-1)

- [Saner behavior of n and N](#saner-behavior-of-n-and-n)
- [Saner command-line history](#saner-command-line-history)
- [Saner CTRL-L](#saner-ctrl-l)
- [Disable audible and visual bells](#disable-audible-and-visual-bells)
- [Quickly move current line](#quickly-move-current-line)
- [Quickly add empty lines](#quickly-add-empty-lines)
- [Edite seus macros rapidamente](#edite-seus-macros-rapidamente)
- [Quickly jump to header or source file](#quickly-jump-to-header-or-source-file)
- [Quickly change font size in GUI](#quickly-change-font-size-in-gui)
- [Change cursor style dependent on mode](#change-cursor-style-dependent-on-mode)
- [Don't lose selection when shifting sidewards](#dont-lose-selection-when-shifting-sidewards)
- [Reload a file on saving](#reload-a-file-on-saving)
- [Smarter cursorline](#smarter-cursorline)
- [Faster keyword completion](#faster-keyword-completion)
- [Alterações cosméticas a esquemas de cores](#alterações-cosméticas-a-esquemas-de-cores)

## [Commands](#commands-1)

- [:global and :vglobal](#global-and-vglobal) - Execute a command on all matching lines.
- [:normal and :execute](#normal-and-execute) - The scripting dream team.
- [:redir](#redir) - Redirect messages.

## [Debugging](#debugging-1)

- [General tips](#general-tips)
- [Verbosity](#verbosity)
- [Profiling startup time](#profiling-startup-time)
- [Profiling at runtime](#profiling-at-runtime)
- [Debugging Vim scripts](#debugging-vim-scripts)
- [Debugging syntax files](#debugging-syntax-files)

## [Miscellaneous](#miscellaneous-1)

- [Additional resources](#additional-resources)
- [Vim distributions](#vim-distributions)
- [Standard plugins](#standard-plugins)
- [Map CapsLock to Control](#map-capslock-to-control)
- [Easter eggs](#easter-eggs)
- [Why hjkl for navigation?](#why-hjkl-for-navigation)

## [Common problems](#common-problems-1)

- [Editing small files is slow](#editing-small-files-is-slow)
- [Editing huge files is slow](#editing-huge-files-is-slow)
- [Colar entre parenteses (ou por que preciso configurar 'paste' o tempo todo?)](#colar-entre-parenteses-ou-por-que-preciso-configurar-paste-o-tempo-todo)
- [Delays when using escape key in terminal](#delays-when-using-escape-key-in-terminal)
- [Function search undo](#function-search-undo)

## [Technical quirks](#technical-quirks-1)

- [Newline used for NUL](#newline-used-for-nul)

## [Lista de esquemas de cores](#lista-de-esquemas-de-cores-1)

## [List of plugins](contents/plugins.md)

---

# Introdução

## O que é o Vim?

[Vim](http://www.vim.org) é um editor de texto com uma longa linha de ancestrais
que vem desde o [qed](https://en.wikipedia.org/wiki/QED_(text_editor)). [Bram
Moolenaar](https://en.wikipedia.org/wiki/Bram_Moolenaar) lançou o Vim em 1991.

O projeto está hospedado na rede em [vim.org](http://www.vim.org/index.php).

Para o Vim: use o seu gerenciador de pacotes preferido ou visite a [página para baixar](http://www.vim.org/download.php) direto da vim.org.

Discussões e questões da usuária são melhores se feitas na lista de correio
eletrônico [vim_use](https://groups.google.com/forum/#!forum/vim_use) (*em inglês*) ou usando o IRC ([Freenode](https://freenode.net)) no canal `#vim` (*em inglês*).

O desenvolvimento acontece no [Github](https://github.com/vim/vim), discussões
na lista de correio eletrônico [vim_dev](https://groups.google.com/forum/#!forum/vim_dev).

Leia [Why, oh WHY, do those #?@! nutheads use
vi?](http://www.viemu.com/a-why-vi-vim.html) (*em inglês*) para ver equívocos
comuns sobre o Vim explicados.

## A filosofia do Vim

O Vim adere a filosofia de de edição modal. Isso quer dizer que ele provem
múltiplos modos e a função/significado das teclas muda de acordo com o modo.
Você navega pelos arquivos no _modo normal_, você insere texto no _modo de
inserção_, você seleciona linhas no _modo visual_, você acessa comando no _modo
de linha de comando_ e assim por diante. Isso pode até parecer complicado à
primeira vista, mas tem uma grande vantagem: você não precisa entortar os dedos
segurando várias teclas ao mesmo tempo, na maioria das vezes você
simplesmente pressiona uma tecla após a outra. Quanto mais comum for a tarefa
menos teclas são necessárias.

Um conceito relacionado que funciona bem com a edição modal são operadores e
movimentos.
_Operadores_ começam uma certa ação, por exemplo mudando, removendo ou
selecionando texto. Logo em seguida você especifíca a região do texto onde a
ação deve ocorrer usando um _movimento_. Para mudar tudo entre os parênteses,
ese `ci(` (leia como "mudar dentro dos parênteses", em inglês: _change inner
parentheses_). Para remover todo um parágrafo de texto de uma vez, use `dap`
(leia como "deletar em volta do parágrafo", em inglês: _delete around
paragraph_).

Se você ver usuárias avançadas do Vim trabalhando, você irá reparar que elas
falam a _língua do Vim_ da mesma forma que pianistas tratam seus instrumentos.
Operações complexas são feitas usando apenas alguns pressionamentos de teclas.
Elas nem sequer pensam mais sobre isso já que a [memória muscular](https://en.wikipedia.org/wiki/Muscle_memory) tomou conta. Isso reduz o [esforço cognitivo
](https://en.wikipedia.org/wiki/Cognitive_load) e ajuda a focar na tarefa atual.

## Primeiros passos

O pacote do Vim inclui um tutorial interativo que ensina as coisas mais básicas
que você precisa saber a respeito. Você pode iniciar o tutorial direto do
shell:

```
$ vimtutor
```

Não fique adiando o tutorial só porque parece chato, vá e trabalhe através dos
exercícios. Os editores ou IDEs que você já usou antes eram todos provavelmente
não-modais, então trabalhar mudando de modo vai ser um pouco esquisito a
princípio, mas quanto mais você usar o Vim, mais isso vai virar [memória muscular](https://en.wikipedia.org/wiki/Muscle_memory).

O Vim partiu do [Stevie](https://en.wikipedia.org/wiki/Stevie_(text_editor)), 
um clone do [vi](https://pt.wikipedia.org/wiki/Vi), e suporta dois modos
"compatível" e "não-compatível". Usar o Vim em modo compatível quer dizer usar
os padrões do vi para todas as opções, ao contrário dos padrões do Vim. O modo
compátivel é assumido enquanto você ainda não tiver criado um vimrc do usuário 
ou começado o Vim com `vim -N`! Não use o Vim em modo compatível. Simplesmente
não use.


Próximos passos:

1. Crie o seu próprio [vimrc](#vimrc-minimo).
2. Tenha alguma [planilha de cola](#cheatsheets) pronta para as primeiras
   semanas.
3. Leia através da seção [basico](#basics-1) para ter uma ideia do que é
   possível. 
4. Aprenda de acordo com a necessidade! Você nunca termina de aprender o Vim. Se
   você encontrar problemas, basta procurar por ele pela rede. Seu problema já
   foi resolvido antes. O Vim vem com uma documentação ótima e saber como
   navegar por ela é uma obrigação: [conseguindo ajuda desconectado](#getting-help-offline).
5. Dê uma olhada nos [Recursos adicionais](#additional-resources).

Um último conselho: por favor aprenda a usar o Vim apropriadamente antes de
começar a adicionar tudo quanto é tipo de [plugins](#managing-plugins) extravagantes que apenas implementam funcionalidades que o Vim já suporta nativamente.

## Vimrc mínimo

O vimrc do usuário pode ser colocado em `~/.vimrc` ou só para melhor
separar/organizar as coisas em `~/.vim/vimrc`. A última opção deixa fácil
colocar toda a configuração sob controle de versão e enviar ela para onde
esteja, por exemplo no Github.

Você encontra muitos "vimrcs mínimos" por toda a rede, e talvez a minha versão
não seja tão mínima quanto deveria, mas ela provem um bom conjunto de
configurações sãs que julgo serem úteis para começar.


Então, aqui vai: [vimrc-minimo](contents/minimal-vimrc.vim)

Caso você esteja interessado, aqui está o [meu vimrc](https://github.com/mhinz/dotfiles/blob/master/.vim/vimrc).

**DICA**: A maioria dos autores de plugins mantêm vários plugins e também
publicam seus próprios vimrc no Github (com frequência em um repositório chamado
de "vim-config" ou "dotfiles"), então quando quer você entre um plugin que você
gosta, dê uma olhada na página do Github do mantenedor e olhe através dos
repositórios.

## Que tipo de Vim eu estou rodando?

Olhar em `:version` irá te dar toda a informação que você precisa saber sobre
como que a versão binária que está rodando atualmente foi compilada.

A primeira linha te diz quando que o binário foi compilado e qual a versão, por
exemplo 7.4. Uma das linhas seguintes irá dizer `Included patches: 1-1051`, que
é o nível do remendo (patch). Portanto, sua versão exata do Vim é 7.4.1051.

Uma outra linha irá colocar algo como `Tiny version without GUI` ("_versão
minúscula sem interface gráfica_") ou `Huge version with GUI` ("_versão enorme com
interface gráfica_"). A informação que tiramos disso é se o seu Vim inclui
interface gráfica ("GUI"), como por exemplo iniciar o `gvim` do shell ou rodar
`:gui` dentro do Vim em um emulador de terminal. A outra informação importante é
o `Tiny` ("_minúscula_") e `Huge` ("_enorme_"). O Vim distingue entre conjuntos 
de funções/características chamados de `tiny` ("_minúcula_"), `small`
("_pequna_"), `normal`, `big` ("_grande_"), e `huge` ("_enorme_"), todas
ativando diferentes subconjuntos de funções/características.

A maioria do resultado que aparece com o `:version` é consumida pela própria
função de listagem mesma. `+clipboard` significa que a função da área de
transferência foi compilada junto, e `-clipboard` significa que não foi compilada.

São poucas as funções que precisam ser compiladas juntamente para funcionar. Por
exemplo, para que `:prof` funcione, você precisa de um Vim com um conjunto
enorme ("_huge_") de funções/características, porque esse conjunto ativa a
função `+profile`.

Se esse não for o caso e você instalou o Vim por um gerenciador de pacotes,
tenha certeza de instalar um pacote chamado `vim-x`, `vim-x11, `vim-gtk`,
`vim-gnome` ou algo parecido, já que esses pacotes normalmente vêm com o
conjunto enorme ("_huge_") de funções.

Você também pode testar programavelmente a versão ou as funcionalidades:

```vim
" Fazer alguma coisa se rodando pelo menos a versão 7.4.42 do Vim com +profile
ativado. 
if (v:version > 704 || v:version == 704 && has('patch42')) && has('profile')
  " fazer algo
endif
```

Ajuda:

```
:h :version
:h feature-list
:h +feature-list
:h has-patch
```

## Planilhas de cola

- http://people.csail.mit.edu/vgod/vim/vim-cheat-sheet-en.png
- https://cdn.shopify.com/s/files/1/0165/4168/files/preview.png
- http://www.nathael.org/Data/vi-vim-cheat-sheet.svg
- http://michael.peopleofhonoronly.com/vim/vim_cheat_sheet_for_programmers_screen.png
- http://www.rosipov.com/images/posts/vim-movement-commands-cheatsheet.png

Ou abra rapidamente uma planilha com cola de dentro do Vim: [vim-cheat40](https://github.com/lifepillar/vim-cheat40).

# O básico

## Buffers, windows, tabs

O Vim é um editor de texto. Toda vez que um texto é mostrado, o texto é parte de
um **buffer**. Cada arquivo será aberto em seu próprio buffer. Plugins mostram
as coisas também em seus próprios buffers e etc.

Os buffers tem muito atributos, por exemplo se o texto que o buffer contém é
modificável ou se o texto está associado com um outro arquivo e portanto precisa
ser sincronizado ao disco na hora de salvar.

**Windows** ou **Janelas** são janelas de exibição _para_ o buffer. Se você
quiser ver vários arquivos ao mesmo tempo ou até mesmo diferentes partes de um
mesmo arquivo, você usa janelas.

E por favor, não as chame de _splits_ ("_divisões_" ou "_partes_"). Você pode
dividir uma janela em duas partes (dois "_splits_"), mas isso não
necessáriamente as transforma em divisões ("_splits_").

Janelas podem ser divididas vertical ou horizontalmente, e as alturas e larguras
das janelas existentes também podem ser alteradas. E é por isso que você pode
rearranjar as janelas como preferir.

Uma **tab page** ou (ou simplesmente "aba") é uma coleção/coletânea de janelas.
Por tanto se você quiser ter múltiplos arranjos de janelas, use as abas.

A propósito, a lista de buffers é global e você pode acessar qualquer buffer a
partir de qualquer aba.

## Buffer ativos, carregados, listados e nomeados

Inicie o Vim como `vim arquivo1`. O conteúdo do arquivo será carregado dentro do
buffer. Agora você tem um **buffer carregado** ("_loaded buffer_"). O conteúdo do buffer só será
sincronizado ao disco rígido (salvo no arquivo original) se você salvar de 
dentro do Vim.

Já que o buffer também é mostrado em uma janela, ele também é um **buffer
ativo** ("_active buffer_"). Agora, se você abrir um outro arquivo com 
`e: arquivo2`, o `arquivo1` vai se tornar um **buffer escondido** 
("_hidden buffer_") e o `arquivo2` será o buffer ativo.

Ambos buffers estão também **listados** ("_listed_"), portanto eles serão
listados com a saída do comando `:ls`. Os buffers dos plugins, ou os buffers de
ajuda, normalmente são marcados como não-listados ("_unlisted_"), já que eles
não arquivos regulares, que você normalmente edita com um editor de texto. Tanto
os buffers listados quanto os não-listados são mostrados pelo comando `:ls!`.

**Buffers não-nomeados** ("_unnamed buffers_"), geralmente usados por plugins,
são buffers que não tem um nome de arquivo associado a si. Por exemplo, `:enew`
irá criar um buffer não-nomeado para ser usado como rascunho. Adicione algum
texto e salve o buffer no disco com `:w /tmp/foo`, e ele irá se tornar um buffer
nomeado.

## Lista de argumentos

A [lista de buffers global](#) é uma coisa do Vim. Antes disso, no Vi, costumava
ter apenas a lista de argumentos, que também está disponível no Vim.

Todo nome de arquivo fornecido ao Vim na linha de comando do Shell, é lembrado
na lista de argumentos. Podem existir múltiplas listas de argumentos: por padrão
todos os argumentos são colocados na lista global de argumentos, mas você pode
usar `:arglocal` para criar uma nova lista de argumentos que é local a janela.

Liste os argumentos atuais com `:args`. Alterne entre os arquivos da lista de
argumentos com `:next` ("_próximo_", `:previous` ("_anterior_"), `:first`
("_primeiro_"), `:last` ("_último_") e companhia. Altere  com `:argadd` (para 
"_ad(d)_icionar"), `:argdelete` (para "_delet_ar") ou `args` uma lista de 
arquivos.

Se você deve usar a lista de buffers ou a lista de argumentos, é só uma questão
de preferência. Minha impressão é a maioria das pessoas usa exclusivamente a
lista de buffers.

Mesmo assim, existem uma forte razão para usar a lista de argumentos:
processamento em batch por meio do `:argdo`! Um exemplo simples de
reestruturamento:

```vim
:args **/*.[ch]
:argdo %s/foo/bar/ge | update
```
Isso irá substituir todas as ocorrências de "foo" por "bar" em todas as fontes e
cabeçalhos de todos os arquivos em C do diretório atual e abaixo.

Ajuda: `:h argument-list`

## Mapeamentos

Você pode definir os seus próprios mapas de teclado com a família de comandos `:map`. Cada comando dessa família define o mapeamentos para um conjunto 
específico de modos. Tecnicamente o Vim vem com a enorme quantidade de 12 modos,
e 6 deles podem ser mapeados. Adicionalmente, existem alguns comandos que agem 
em múltiplos modos ao tempo.

| Recursivo | Não-recursivo | Desmapear | Modos                             |
|-----------|---------------|-----------|---------------------------------- |
| `:map`    | `:noremap`    | `:unmap`  | normal, visual, operador-pendendo |
| `:nmap`   | `:nnoremap`   | `:nunmap` | normal                            |
| `:xmap`   | `:xnoremap`   | `:xunmap` | visual                            |
| `:cmap`   | `:cnoremap`   | `:cunmap` | linha de comando                  |
| `:omap`   | `:onoremap`   | `:ounmap` | operador-pendendo                 |
| `:imap`   | `:inoremap`   | `:iunmap` | inserção                          |

Por exemplo, isso aqui irá definir um mapeamento apenas para o modo normal:

```vim
:nmap <space> :echo "foo"<cr>
```

Desmapei novamente usando `:nunmap <space>`.

Para conferir alguns outros modos mais incomuns (ou uma combinação deles), veja
`h map-modes`.

Até agora, tudo sob controle. Mas tem um detalhe que pode ser bem confuso para
iniciantes: `:nmap` é _recursivo_! Ou seja, o lado direito (que é remapeado) 
vai levar outros mapeamentos em conta também.

Então, você definiu um mapeamento que simplesmente ecoa "Foo" ao apertar a tecla
"b":

```vim
:nmap b :echo "Foo"<cr>
```

Mas e se você quiser mapear o comportamento padrão de `b` (voltar uma palavra)
para uma outra tecla?

```vim
:nmap a b
```

Se você apertar <kbd>a</kbd>, esperamos que o cursor volte à uma palavra atrás,
mas ao contrário, "Foo" vai ser impresso de novo na linha de comando! Isso
acontece devido ao fato que a tecla `b`, que fica no lado direito do mapeamento,já tinha sido remapeada para fazer ou ação, que no caso foi a ação de ecoar 
"foo" com `:echo "Foo"<cr>`.

Para resolver esse problema de forma adequada, é preciso usar um mapeamento
_não-recursivo_:

```vim
:nnoremap a b
```
Regra de ouro: Sempre use mapeamentos não-recursivos, a não ser que realmente se
deseje um mapeamento recursivo.

Olhe os seus mapeamentos sem fornecer o lado direito do comando. Por exemplo,
`:nmap` mostra todos os mapeamentos para o modo normal, e `:nmap <leader>`
mostra todos os mapeamentos (para o modo normal) que começam com a tecla-líder.

Se você quiser desativar um mapeamento padrão, o mapei para o caractére especial
`<nop>`, como por exemplo `:noremap <left> <nop>`.

Ajuda:

    :h key-notation
    :h mapping
    :h 05.3

## A tecla-líder

A tecla-líder é uma base de suporte usada com mapeamentos personalizados e por
padrão é configurada para a tecla `\`.

```vim
nnoremap <leader>h :helpgrep<space>
```

Esse mapa é acionado por `\h`. Se você quiser usar a tecla de espaço ao invés da
barra invertida (que é o padrão)

```vim
let mapleader = ' '
nnoremap <leader>h :helpgrep<space>
```

Além disse, existe a `<localleader>` que é a contraparte local de `<leader>` e é
para ser supostamente usada para mapas que são locais ao buffer, como por exemplo plugins para tipos específicos de arquivos. Ela também é por padrão a tecla `\`.

**Nota**: Configure as teclas-líder antes de fazer algum mapeamento! Todos os
mapeamentos que já foram efetuados não mudarão só porquê a tecla-líder foi
alterada. `:nmap <leader>` irá mostrar todos os mapeamentos com a tecla líder
para o modo normal que já estão acionados, então use-o para rechecar os seus
mapeamentos.

Veja `:h mapleader` e `:h maplocalleader` para saber mais.

## Registradores

Registradores (inglês: "_registers_") são lugares que o Vim usa para registrar texto.
Copiar texto para um registrador é chamado de **yanking** e extrair texto de um
registrador é chamado de **pasting** ("_colar_"). 

O Vim provem os seguintes registradores:

| Tipo                | Charactére             | preenchido por? | Apenas de leitura? | Contém texto de? |
|---------------------|------------------------|------------|-----------|---------------------|
| Não nomeado             | `"`                    | vim        | [ ]       | Último puxão ou remoção. (`d`, `c`, `s`, `x`, `y`) |
| Numerado            | `0` to `9`             | vim        | [ ]       | Registrador `0`: último puxão. Registrador `1`: Última remoção. Registrador `2`: Seunda remoção. E assim por diante. Pense nos registradores `1`-`9` como uma [file](https://en.wikipedia.org/wiki/Queue_(abstract_data_type)) com 9 elementos apenas de leitura. |
| Pequena remoção        | `-`                    | vim        | [ ]       | Última remoção que for menor que uma linha.|
| Nomeado               | `a` até `z`, `A` até `Z` | usuário       | [ ]       | Se você empurrar para o registrador `a`, você substitui o texto dele. Se você empurrar para o registrador `A`, você acrescenta ao texto no registrador `a`. |
| apenas leitura           | `:`, `.`, `%`          | vim        | [x]       | `:`: Último comando `.`: Último texto inserido, `%`: Nome do arquivo atual. |
| Buffer alternativo    | `#`                    | vim        | [ ]       | Na maioria das vezes é o último buffer visitado na janela atual. Veja `:h alternate-file` |
| Expressão          | `=`                    | usuário       | [ ]       | Avaliação da expressão em VimL que foi puxada ("yanked"). Por exemplo, faça isso em modo de inserção: `<c-r>=5+5<cr>` e "10" será inserido no buffer. |
| Seleção           | `+`, `*`               | vim        | [ ]       | `*` e `+` são os registradores da área de transferência. [clipboard](#clipboard). |
| Soltar                | `~`                    | vim        | [x]       | Do último arrastas e soltar. |
| Buraco negro          | `_`                    | vim        | [ ]       | Se você não quiser que nenhum outro registrador seja implicitamente afetado. Por exemplo, `"_dd` deleta a linha tual sem afetar os registradores `"`, `1`, `+`, `*`. |
| Último padrão de busca | `/`                    | vim        | [ ]       | Último padrão usado com `/`, `?`, `:global`, etc. |

Cada registrador que não é apenas de leitura pod ser determinado com:

```vim
:let @/ = 'registro'
```

Em seguida <kbd>n</kbd> iria pular para a próxima ocorrência de "registro".

Há várias exceções onde os registradores são implicitamente preenchidos, então
só para ter certeza, confira `:h registers`.

Copie com `y` e cole com `p`/`P`, mas lembre-se que o Vim distingue entre
seleções visuais de caracteres e de linha. Veja `:h linewise`.


**Exemplo: com atenção lineal**

`yy` (ou apenas `Y`) copia a linha atual, mova o cursor para algum outro lugar,
use `p` para colar abaixo da linha em que esteja ou `P` para colar na linha
acima.

**Exemplo: com atenção focada em caracteres**

Copie a primeira palavra com `0yw`, mova para algum outro lugar, cole na linha
em que esteja e após o cursor com `p` e antes do cursor com `P`.

**Exemplo: nomeação explícita de registrador**

`"aY` copia a linha atual para o registrador `a`. Vá para alguma outra linha.
Use `"AY` para acrescentar a linha atual ao registrador `a`.

Sugiro que você dê uma brincada com esses registradores e constantemente olhe em
`:reg`, para que você veja em primeira mão o quê está acontecendo com os
registradores.

**Caso engraçado**: No Emacs, `yaking` quer dizer colar [ou _reinserir texto que anteriormente morto_("_reinserting previously killed text_")] e não copiar.

## Alcances

Os alcances são bem fáceis de entender, mas muitos (Vimmers) não sabem sobre o
potencial que eles possuem.

- Muitos comandos aceitam alcances.
- Um endereço denota uma certa linha.
- Um alcance pode ser tanto um único endereço quanto um par de endereços
  separados tanto por `,` quanto por `;`.
- Os alcances informam os comandos em quais linhas eles devem agir.
- Muitos comandos agem por padrão apenas na linha atual.
- Somente `:write` e `:global` agem em todas as linhas por padrão.

A utilização dos alcances é bem intuitiva, portanto aqui seguem alguns exemplos
(usando `:d` como uma abreviação de `:delete`):

| Comando | Linhas em que age |
|---------|----------------|
| `:d` | Linha atual. |
| `:.d` | Linha atual |
| `:1d` | Primeira linha. |
| `:$d` | Última linha. |
| `:1,$d` | Todas as linhas. |
| `:%d` | Todas as linhas (alívio sintático para `1,$`). |
| `:.,5d` | Da linha atual até a linha 5. |
| `:,5d` | Também a linha atual e até a linha 5. |
| `:,+3d` | Linha atual e as próximas 3 linhas. |
| `:1,+3d` | Da primeira linha até a linha atual + 3. |
| `:,-3d` | Linha atual e as últimas 3 linhas. (O Vim irá lhe perguntar, já que esse é um alcance reverso.) |
| `:3,'xdelete` | Lines 3 to the line marked by [mark](#marks) x. |
| `:/^foo/,$delete` | Da próxima linha que começa com "foo" até o final. |
| `:/^foo/+1,$delete` | Da linha após a linha que começa com "foo" até o final. |

Repare que ao invés de `,`, o `;` também pode ser usado como separador. A
diferença é como `de,para` o _para_ é relativo a linha atual, mas ao usar
`de;para`, o _para_ é relativo ao endereço do _de_! Assumindo que você está na
linha 5, `:1,+1d` deletaria as linhas de 1 a 6, ao mesmo tempo que `:1;+1d`
deletaria apenas as linhas 1 e 2.

O endereço `/` pode ser precedido com outro endereço. Isso permite que você
_empilhe_ padrões, por exemplo:

```vim
:/foo//bar//quux/d
```
Isso iria deletar a primeira linha contendo "quux" após a primeira linha
contendo "bar" depois da primeira linha contendo "foo" depois da linha atual.

As vezes o Vim automaticamente antecipa com um alcance na linha de comando. Por
exemplo, comece uma seleção visual de linha com o `V`, selecione algumas linhas
e digite `:`. A linha linha de comando será povoada com o alcance `'<,'>`, que
significa que o próximo comando irá usar as linhas previamente selecionadas como
um alcance. (Essa também é a razão pela qual as vezes você vê mapeamentos como
`:vnoremap foo :<c-u>command`. Neste caso, `<c-u>` é usado para remover o
alcance, porque o Vim irá jogar um erro quando der um alcance a um comando que
não suporta o tal alcance.).

Outro exemplo é ao usar `!!` em modo normal. Isso irá povoar a linha de comando
com `:.!`. Se seguido por um programa externo, a saída do programa iria
substituir a linha atual. Portanto, você substituiria o parágrafo atual com a
saída do comando ls usando: `:?^$?+1,/^$/-1!ls`. Chique!

Ajuda:

```
:h cmdline-ranges
:h 10.3
```

## Marcadores (marks)

Você usa marcadores para lembrar uma posição em um arquivo, ou seja; número da linha e coluna.

| Marcadores | Determinado pelo... | Uso |
|-------|----------|-------|
| `a` - `z` | Usuário | Local ao arquivo, portanto é apenas válido dentro de um arquivo. Jumping to a lowercase mark, means jumping within the current file. |
| `A` - `Z` | Usuário | Global, portanto válido entre arquivos. Também chamado de _marcador de arquivo_ ("_file marks_"). Pular para um marcador de arquivo pode significar mudar para um outro buffer. |
| `0` - `9` | viminfo | `0` É a posição onde o arquivo viminfo foi sobreescrito (salvo) pela última vez. Na prática, isso quer dizer quando o último processo do Vim foi encerrado. `1` é a posição de quando o penúltimo processo do Vim foi encerrado, e assim por diante. |

Coloque `'`/`g'` ou `` ` ``/`` g` `` na frente de um marcador para formar um
movimento ("_motion_").

Use `mm` para lembrar a posição atual com o marcador "m". Movimente-se pelo
arquivo e pule de volta via `'m` (para o primeiro caractere não-vazio), ou
`` `m `` (para a coluna exata). Marcadores minúsculos serão lembrados após 
sair do Vim apenas se você falar para o seu arquivo viminfo fazer isso, veja 
`:h viminfo-'`. 

Use `mM` para lembrar a posição atual com o marcador de arquivo "M". Mude para
outro buffer e volte de novo com `'M' ou `` `M ``.

Outros movimentos incluem:

| Movimento           | Pular para... |
|---------------------|-----------|
| `'[`, `` `[ ``      | Primeira linha ou caractere do último texto mudado ("`c`") ou puxado/copiado ("`y`"). |
| `']`, `` `] ``      | Última linha ou caractere do último texto mudado ("`c`") ou puxado/copiado ("`y`"). |
| `'<`, `` `< ``      | Começo da linha ou caractere da última seleção visual. |
| `'>`, `` `> ``      | Fim da linha ou caractere da última seleção visual. |
| `''`, ``` `` ```    | Posição antes do último pulo ("_jump_"). |
| `'"`, `` `" ``      | Posição de quando aconteceu a última saída do arquivo (buffer) atual. |
| `'^`, `` `^ ``      | Posição de onde a última inserção parou. |
| `'.`, `` `. ``      | Posição de onde a última mudança foi feita. |
| `'(`, `` `( ``      | Começo da frase atual. |
| `')`, `` `) ``      | Fim da frase atual. |
| `'{`, `` `{ ``      | Começo do parágrafo atual.  |
| `'}`, `` `} ``      | Fim do parágrafo atual. |

Marcadores também podem ser usados em um [alcançador](#Alcançadores). Você
provavelmente já viu isso antes e se perguntou o quê isso significa: Selecione
algum texto em modo visual e aperte `:`, a linha de comando será "antecipada"
com `:'<,'>`, o que significa que o comando que vier em seguida terá o alcance
encoberto pela seleção visual.

Use `:marks` para listar todos os marcadores. Leia tudo que puder em `:h
mark-motions`.

## Autocomplementação

O Vim possui vários tipos de autocomplemento em modo de inserção. Em caso de
múltiplas possibilidades, um menu flutuante irá permitir que você navegue até a
o complemento de sua escolha.

Tipos típicos de complementos são tags, funções de módulos importados ou
bibliotecas, nome de arquivos, dicionários ou simplesmente palavras do buffer
atual.

O Vim também prover um mapeamento de teclado para cada tipo de complementação e
todos eles começam com `<c-x>` (lembre-se de usá-los em modo de inserção).

| Mapeamento | Tipo | Ajuda         |
|---------|------|--------------|
| `<c-x><c-l>` | linhas inteiras | `:h i^x^l` |
| `<c-x><c-n>` | palavras chave do arquivo atual | `:h i^x^n` |
| `<c-x><c-k>` | palavras chave da opção de `dicionário` | `:h i^x^k` |
| `<c-x><c-t>` | palavras chave da opção de `'thesaurus'` | `:h i^x^t` |
| `<c-x><c-i>` | palavras chave do arquivo atual e arquivos incluídos | `:h i^x^i` |
| `<c-x><c-]>` | tags | `:h i^x^]` |
| `<c-x><c-f>` | nome de arquivos | `:h i^x^f` |
| `<c-x><c-d>` | definições ou macros | `:h i^x^d` |
| `<c-x><c-v>` | Comandos do Vim | `:h i^x^v` |
| `<c-x><c-u>` | definido pela usuária (como especificado em `'completefunc'`) | `:h i^x^u` |
| `<c-x><c-o>` | omni complementação (como especificado em `'omnifunc'`) | `:h i^x^o` |
| `<c-x>s`     | sugestões ortográficas | `:h i^Xs` |

As pessoas podem se confundir entre Autocomplementação definida pelo usuário e a
omni complementação, mas tecnicamente elas fazem a mesma coisa. Elas pegam uma
função que inspeciona a posição atual e retornam uma lista de sugestões.
Complementações definidas pela usuária são determinadas pela própria pessoa e
para uso pessoal. (Surpresa!) Pode ser qualqer coisa. A Omni Complementação tem
o propósito de ser usada para tipos específicos de arquivos, como complementando
estruturas de membros ou métodos de classes, e é normalmente determinada por
plugins de tipos de arquivo ("_filetype plugins_").

O Vim também permite a complementação de múltiplos tipos de uma vez só, bastando
ativas a opção `'complete'`. Por padrão, essa opção já inclui um bocado de
coisas por si mesma, então tenha certeza de dar uma polida para que fique ao seu
gosto. Você pode ativar essa opção de complementação usando tanto `<c-n>`
(próximo) quanto `<c-p>` (anterior), que por coincidência também são os atalhos
de teclado usados para navegar pelas opções do menu flutuante. Veja `:h i^n` e
`:h 'complete'` para saber mais sobre isso.

Aproveite e confira também `:h 'completeopt'` para configurar o comportamento do
menu flutuante. O padrão até que bem são, mas eu prefiro adicionar também "noselect" ("_nenhuma seleção_").

Ajuda:

```
:h ins-completion
:h popupmenu-keys
:h new-omni-completion
```

## Movimentos, operadores, objetos de texto

**Movimentos** movem o cursor. Todos você já sabem sobre `h`/`j`/`k`/`l`. Ou
`w` e `b`. Até `/` é um movimento. Eles também aceitam uma conta. `2?the<cr>`
pula para a anti-penúltima ocorrência de "the".

Veja `:h navigation` e tudo que estiver abaixo para todos os movimentos
disponíveis.

**Operadores** agem em uma região do texto, por exemplo `d`, `~`, `gU`, `>` para
mencionar apenas alguns. Eles são usados em dois contextos, ou em modo normal ou
em modo visual. Em modo normal, os operadores vem primeiro seguidos por um
movimento, por exemplo `>j`. Em modo visual, operadores simplesmente agem na
área selecionada, por exemplo `Vjd`.

Assim como os movimentos, os operadores também aceitam uma conta, como por
exemplo `2gUw` que transforma o resto da palavra atual e da próxima palavra em
maiúsculas. Já que movimentos e operadores aceitam contas, `2gU2w` funciona bem
e executa `gU2w` duas vezes.

Veja `:h operator` para conferir todos os operadores disponíveis. Use `:set
tildeop` para fazer com que o til (`~`) funcione como um operador. 

**Objetos de texto** agem na área que os cerca, em oposição aos movimentos que
agem em uma direção específica.  Na verdade eles funcionam em objetos, como por
exemplo uma palavra toda, uma frase inteira, tudo entre parênteses, e assim por
diante.

Objetos de texto não podem ser usados para mover o cursor em modo normal, porque
nem mesmo os cursores mais habilidores dão conta de pular em duas direções ao
mesmo tempo. Entretanto, isso funciona em modo visual, pois que um lado do texto
já está selecionado e o cursor pode simplesmente pular para o outro lado.

Objetos de texto começam ou com um `i` ou `a` seguidos por um caractere que
denota o objeto (`i` pode ser lembrado como "_i_nterno", e `a` como o que
está "_a_o redor"). Com o `i` a ação é executada apenas no objeto em si, com 
o `a` a ação é no objeto e mais os espaçoes (em branco) ao redor do objeto. 
Por exemplo, `diw` deleta a palavra atual e `ci(` altera tudo que estiver entre
os parênteses.

Objetos de texto também aceitam uma conta. Imagine `((( )))` e o cursor no meio
ou nos parênteses mais internos, então `d2a(` irá remover os dois _pares de
parênteses_ mais internos e tudo o que estiver no meio e entre eles.

Veja `:h text-objects` para conferir todos os objetos de texto disponíveis.

## Autocmds

Em muitas ocasiões o Vim emite eventos. Você engancha nesses eventos usando
Autocmds ("_auto comandos_").

Você não usaria o Vim se não houvessem os Autocmds. Eles são usados o tempo
todo, mesmo que você não perceba. Não acredita em mim? Confira `:au`, mas não
deixe que o resultado te assuste. Esses são todos os Autocmds que estão fazendo
efeito agora mesmo.

Veja `:h {event}` para uma ter uma rápida visão geral de todos os eventos
disponíveis e `:h autocmd-events-abc` para mais detalhes.

Um exemplo típico seria determinar configurações de acordo um típo específico de
arquivo:

```vim
autocmd FileType ruby setlocal shiftwidth=2 softtabstop=2 comments-=:#
```
Mas como que um buffer pode saber que ele contém um código em Ruby? Porque um
outro Autocmd detectou isso e configurou o tipo de arquivo de acordo, o que por
sua vez engatilhou o evento `FileType` ("_tipo de arquivo_").

Uma das primeiras coisas que todos adicionam aos seus vimrc é `filetype on`.
Isso simplesmente quer dizer que o `filetype.vim` é lido na inicialização, o que
determina Autocmds para quase todos os tipos de arquivo que existem sob o sol.

Se você tiver coragem, de uma olhada nisto aqui: `:e $VIMRUNTIME/filetype.vim`.
Procure por "Ruby" e você descobrirá que o Vim simplesmente usa a extensão de
arquivo `.rb` para detectar arquivos de Ruby:

**NOTA**: Autocmds do mesmo evento são executados na ordem em que foram criados.
`:au` os mostra na ordem correta.

```vim
au BufNewFile,BufRead *.rb,*.rbw  setf ruby
```

Os eventos `BufNewFile` e `BufRead` nesse caso são codificados manualmente nas
fontes (sources) em C do Vim e são emitidos a cada vez que você abre um arquivo
por meio de `:e` e comandos similares. Em seguida todas as centenas de tipos de
arquivo do `filetype.vim` são testados.

Resumindo, o Vim faz uso pesado de eventos e Autocmds mas também expõe uma
interface limpa para enganchar nesse sistema dirigido por eventos para a
customização.

Ajuda: `:h autocommand`

## Lista de alterações, lista de pulos
### Changelist, jumplist

As posições das últimas 100 alterações são mantidas na **lista de alterações**.
Várias alterações pequenas feitas na mesma linha serão fundidas, mas assim a 
posição será aquela da última mudança (caso você tenha adicionado alguma coisa
no meio da linha).

Cada vez que você pular, a posição de _antes_ do pulo será lembrada na **lista
de pulos**. A lista de pulos tem até 100 registros. Cada janela possui sua
própria lista de pulos. Quando você divide ("_split_") uma janela, a lista de
pulos será copiada.

Um pulo é um dos seguintes comandos: `'`, `` ` ``, `G`, `/`, `?`, `n`, `N`,
`%`, `(`, `)`, `[[`, `]]`, `{`, `}`, `:s`, `:tag`, `L`, `M`, `H` e comandos que
começam a edição de um novo arquivo.

| Lista       | Listar todos os registros | Ir para uma posição anterior | Ir para uma posição posterior |
|------------|------------------|----------------------|----------------------|
| lista de pulos   | `:jumps`         | `[conta]<c-o>`       | `[conta]<c-i>`       |
| lista de alterações | `:changes`       | `[conta]g;`          | `[conta]g,`          |
Quando você listar todos os registros, um marcador `>` será usado para mostrar
qual a posição atual. Normalmente isso estará abaixo da posição 1, a última
posição.

Se você quiser que ambas as listas continuem a existir mesmo após reiniciar o
Vim, você precisará utilizar o arquivo viminfo e `:h viminfo-`.

**NOTA**: A posição antes do último pulo também é mantida como um
[marcador](#marcadores) e pode ser pulada com ``` `` ``` ou `''`.

Ajuda:

```
:h changelist
:h jumplist
```

## Árvore do desfazer

As últimas mudanças do estado do texto são lembradas. Você pode usar o comando
_undo_ ("desfazer") para reverter as mudanças, e o comando _redo_ ("refazer")
para reverter mudanças.

O ponto importante para entender disso; é que a estrutura de dados que mantém as
alterações recentes não é uma
[fila](https://es.wikipedia.org/wiki/Cola_(inform%C3%A1tica)), mas sim uma
[árvore](https://pt.wikipedia.org/wiki/%C3%81rvore_(estrutura_de_dados))! Suas 
alterações são nodos/nós na árvore e cada um deles (com exceção do mais 
superior) possui um nodo antecestral/antecessor. Cada nodo mantém informação
sobre o texto e o tempo da alteração. Um galho (ou ramo) é uma série de nodos
que começam a partir de um nodo e vão até o nodo do topo. Um novo é galho é
criado quando você desfaz uma mudança e insere algo novo.

```
ifoo<esc>
obar<esc>
obaz<esc>
u
oquux<esc>
```

Agora você tem três linhas e a árvore dos desfazares fica mais ou menos assim:

```
     foo(1)
       /
    bar(2)
   /      \
baz(3)   quux(4)
```

A árvore do desfazer possui 4 mudanças. Os números representam o _tempo_ em que
os nodos foram criados.

Agora há duas formas de atravessar essa árvore, podemos dizer que uma é
_conforme o galho_ e a outra é _conforme o tempo_.

Desfazer ("_undo_" ou `u`) e refazer ("_redo_" ou `<c-r>`) funcionam conforme-o-galho. Eles vão para cime e para baixo no galho atual. O `u` irá reverter o
texto ao nodo em que "bar" se encontra. Um outro `u` a mais irá reverter o texto
ainda mais, ao ponto (nodo) em que "foo" se encontra. Agora, ao apertar `<c-r>`
irá voltar ao estado do nodo "bar", e apertar `<c-r>` mais uma vez irá levar ao
nodo "quux". (Não existe mais nenhuma forma de alcançar o nodo "baz" apenas
conforme-o-galho).

Por outro lado, `g-` e `g+` funcionam conforme-o-tempo. Portanto, `g-` não irá
reverter ao estado do nodo "bar", como o `u` faz, mas ao estado cronologicamente
anterior, que no caso é o nodo "baz". Um outro `g-` a mais irá reverter ao
estado em que o nodo "bar" se encontra, e assim por diante. Portanto, `g-` e
`g+` vão e voltam no tempo, respectivamente.

| Comando / Mapeamento | Ação |
|-------------------|--------|
| `[conta]u`, `:undo [conta]` | Desfazer [conta] mudanças. |
| `[conta]<c-r>`, `:redo` | Refazer [conta] mudanças. |
| `U` | Desfazer todas as alterações na linha desde a última mudança (a mais
recente). |
| `[conta]g-`, `:earlier [conta]?` | Ir para o estado anterior do texto tantas vezes quanto a [conta].  A "?" pode ser também "s", "m", "h", "d", ou "f". Por
exemplo, `:earlier 2d` volta o texto ao estado em que estava a 2 dias atrás. `:earlier 1f` irá ao estado em que o texto se encontrava quano foi salvo pela última vez. |
| `[conta]g+`, `:later [conta]?` | Assim como o comando acima, só que na outra
direção. (OBS: em inglês "earlier" quer dizer "_mais cedo_" e "later" quer dizer
"_mais tarde_").|

A árvore com os desfazares é mantida na memória e será perdida quando o Vim for
encerrado. Veja [Manipulando os arquivos de backup, swap, undo, e viminfo](#manipulando-os-arquivos-de-backup-swap-undo-e-viminfo) para saber como ativar permanentemente o desfazer.

Se você está confuso com a árvore do desfazer, o plugin 
[undotree](https://github.com/mbbill/undotree) faz um ótimo trabalho ajudando a
visualizar a árvore.

Ajuda:

```
:h undo.txt
:h usr_32
```

## Listas de conserto rápido e de localização
### Quickfix and location lists

Toda vez que uma ação precisar retornar uma lista de localizações, a _lista de
conserto rápido_ ou a _lista de localização_ podem ser usadas. Neste caso, uma
localição é um arquivo, o número de uma linha e opcionalmente uma coluna.

Exemplos disso seriam erros de compilador montados em uma lista de conserto
rápido, ou os resultados correspontes de ferrementa grep externa montados em uma
lista de localização.

A grande vantagem de usar essas listas ao invés de um buffer vazio é que você
obtem uma boa interface para navegar pelos resultados.

Todo o tempo, existe apenas uma lista de conserto rápido, mas cada janela pode
ter sua própria lista de localização. As duas listas _podem até_ parecerem
iguais, mas usam comandos um pouco diferentes para a navegação.

Comandos mais comuns:

| Ação         | Conserto rápido (Quickfix)     | Localização (Location)     |
|----------------|--------------|--------------|
| abrir janela    | `:copen`     | `:lopen`     |
| fechar janela   | `:cclose`    | `:lclose`    |
| próximo resultado     | `:cnext`     | `:lnext`     |
| resultado anterior | `:cprevious` | `:lprevious` |
| primeiro resultado    | `:cfirst`    | `:lfirst`    |
| resultado anterior     | `:clast`     | `:llast`     |

Veja `:h :cc` e tudo que estiver abaixo para saber todos os comandos.

**Exemplo**:

Vamos usar nosso velho amigo `grep` para pesquisar pelos arquivos do diretório
atual por uma certa informação e colocar os resultados na lista de conserto
rápido.

```vim
:let &grepprg = 'grep -Rn $* .'
:grep! foo
<grep output - hit enter>
:copen
```

Assumindo que algum dos arquivos continha alguma ocorrência de "foo", o mesmo
será mostrado na lista de conserto rápido. 

## Macros

O Vim permite que você _grave_ os caracteres digitados em um
[registrador](#registradores). É um ótimo jeito de automatizar certas tarefas
no meio do trabalho. (Para tarefas mais elaboradas, [Vim
scripting](#Vim-scripting) deve ser usado ao invés de Macros).

- Comece a gravar digitando `q` seguido por um registrador, por exemplo o `q`. (A linha de comando irá assinalar com a mensagem "recording @q".)
- Encerre a gravação digitando `q` novamente.
- Execute o macro digitando `[conta]@q`.
- Repita o último macro com `[count]@@`.

**Exemplo 1:**

Insira uma linha e repita 10 vezes:

```
qq
iabc<cr><esc>
q
10@q
```

(O mesmo poderia ser feito sem macros: `oabc<esc>10.`)

**Exemplo 2:**

Para adicionar o número da linha na frente de todas as linhas, comece na
primeira linha adicione "1. " a ela manualmente. Incremente o número sob o
cursor usando `<c-a>`, mostrado como `^A`.

```
qq
0yf jP0^A
q
1000@q
```

Aqui nós simplesmente esperamos que o arquivo não contenha mais que 1000 linhas
quando usamos `1000@q`, mas também podemos usar um _macro recursivo_, que
executa até que o macro não possa mais ser aplicado a uma linha:

```
qq
0yf jP0^A@q
q
@q
```

(O mesmo poderia ser atingido sem macros: `:%s/^/\=line('.') . '. '`)

Repare que apesar de eu mostrar como conseguir o mesmo resultado sem o uso de
macros, isso só funciona para esses tipos de exemplos simples. Para
automatizações mais complexas, macros são literalmente como uma bomba!

Veja também: [Edite seus macros rapidamente](#edite-seus-macros-rapidamente)

Ajuda:

```
:h recording
:h 'lazyredraw'
```

## Esquemas de cores

Esquemas de cores são o jeito que você pode estilizar o seu Vim. O Vim consiste de vários componentes e cada um deles pode ser customizado com diferentes cores
para o plano de frente, plano de fundo e alguns outros atributos como texto em
negrito etc. Eles podem podem ser determinados desse jeito:

```vim
:highlight Normal ctermbg=1 guibg=red
```

Isso iria colorir o plano de fundo ("_bg_") de vermelho. Veja `:h highlight`
para mais informações.

Então, esquemas de cores são basicamente coleções de comandos `:highlight`.

Na verdade, a maioria dos esquemas de cores são 2 esquemas de cores! O exemplo
acima determina as cores com `cterbg` e `guibg`. A primeira opção (`cterm`)
apenas será usada se o Vim for inicializado em um emulador de terminal, por
exemplo o xterm. A última (`gui*`) será usada em ambientes gráficos como o Gvim
ou o MacVim.

Se alguma vez ocorrer de você usar um esquema de cores no Vim em um terminal e
as cores não se parecerem com as da imagem (screenshot/printscreen),
provavelmente o esquema de cores define apenas as cores a GUI (Interface Gráfica
da Usuária). O oposto também pode acontecer, se você usar um Vim gráfico (como o
Gvim ou o MacVim) e as cores parecerem meio desajustadas, talvez o esquema de
cores esteja definindo apenas as cores para o terminal. 

O último caso pode ser "resolvido" ativando as cores verdadeiras ("_true
colors_") no Neovim ou no Vim a partir da versão 7.4.1830. Isso faz com que o
Vim use as definições de cores para o ambiente gráfico ("_GUI_"), mas isso
também requer que o emulador de terminal em si e todo programa que estiver pelo
meio do caminho (como o tmux) serem capazes de lidar com cores verdadeiras.  ([Essa gist](https://gist.github.com/XVilka/8346728) fornece uma boa visão geral sobre o assunto.)

Ajuda:

- `:h 'termguicolors'`
- [Lista de esquemas de cores](#lista-de-esquemas-de-cores)
- [Alterações cosméticas a esquemas de cores](#alterações-cosméticas-a-esquemas-de-cores)

## Dobraduras
### Folding

Todo texto (ou código fonte) possui uma certa estrutura. Se você tem uma
estrutura, isso significa que você tem regiões de texto separadas logicamente.
As dobraduras permitem que você "dobre" certa região em uma única linha e
mostrando uma descrição curta. Existem vários comandos que agem nessas regiões
chamadas de _dobras_ ("_folds_"). As dobras também podem ser aninhadas.

O Vim faz distinção entre vários tipos de métodos de dobraduras: 

| 'método de dobra' | Uso |
|--------------|-------|
| diff         | Usado em janelas de diff para dobrar texto não alterado. |
| expr         | Usa `'foldexpr'` para basicamente criar um novo método de dobra. |
| indent       | Dobra baseado na indentação. |
| manual       | Crie dobras você mesma com `zf`, `zF`, e `:fold`. |
| marker       | Dobra baseado nos marcadores no texto (com frequência nos comentários). |
| syntax       | Dobra baseado na sintáxe, como dobrar em blocos de `if`. |


**NOTA**: Dobraduras podem ser computacionalmente intensas! Se você experienciardesvantagens na performance (pequenos atrasos enquanto digita), de uma olhada no
plugin [FastFold](https://github.com/Konfekt/FastFold), que prevem que o Vim 
atualize as dobras quando isso não é necessário.

Ajuda:

```
:h usr_28
:h folds
```

## Sessões
### Sessions

Se você salvar uma **visão** ("_view_", `:h :mkview`), o estado atual da janela
(e as opções e mapeamentos) são salvos para uso posterior (`:h :loadview`).

Uma **sessão** salva as visões de todas as janelas e mais as configurações
globais. Ela basicamente 'tira um retrato' da sua instância atual do Vim e a
salva um um arquivo de sessão. Deixe-me realçar isso: ela salva o estado atual;
tudo que for feito após salvar a sessão não será parte do arquivo de sessão.
Para "atualizar" a sessão, simplesmente salve-a novamente.

Isso é perfeito para salvar os seus _projetos_ e facilita na hora de mudar entre
eles.

Tente fazer isso agora mesmo! Abra algumas janelas e abas e faça `:mksession
Foo.Vim`. Se você omitir o nome do arquivo, o Vim assumirá que é
`Session.vim`. O arquivo será salvo no diretório de trabalho atual, confira qual
o diretório com `:pwd`. Recomece o Vim e faça `:source Foo.vim` e voilà, a lista
de buffers, o leiaute das janelas, os mapeamentos, o diretório atual e etc. tudo
deve ser o mesmo que era quando você salvou a sessão. Faça um pouco mais de
trabalho e atualize a sessão sobreescrevendo o arquivo de sessão que já existe
com `:mksession! Foo.vim`.

Note que um arquivo de sessão não passa de uma coleção de comando do Vim que
supostamente vão restaurar um certo estado de uma instância do Vim, portanto
sinta-se a livre para dar uma olhada nele: `:vs Foo.vim`.

Você pode dizer ao Vim que tipo de coisas devem ser salvas em uma sessão
determinando ("_set_") as opções da sessão `'sessionoptions'`.

Com o próposito de scripts o Vim mantém o nome da última sessão originada
("_sourced_") na variável interna `v:this_session`.

Ajuda:

```
:h Session
:h 'sessionoptions'
:h v:this_session
```

## Localidade
### Locality

Muitos dos conceitos mencionados acima possuem uma contraparte _local_:

| Global | Local | Escopo | Ajuda |
|--------|-------|-------|------|
| `:set`     | `:setlocal`           | buffer ou janela | `:h local-options`    |
| `:map`     | `:map <buffer>`       | buffer           | `:h :map-local`       |
| `:autocmd` | `:autocmd * <buffer>` | buffer           | `:h autocmd-buflocal` |
| `:cd`      | `:lcd`                | janela           | `:h :lcd`             |
| `<leader>` | `<localleader>`       | buffer           | `:h maplocalleader`   |

Variáveis também suportam escopos diferentes, mas isso será explicado em [Vim scripting](#vim-scripting).

# Utilização

## Conseguir ajuda desconectado

O Vim vem com uma ótima documentação no formato de simples arquivos de texto com
um layout especial. O sistema utilizado pelo Vim para acessar certas partes
desses arquivos é baseado em marcas (tags).

Primeiramente, leia isso: `:help :help`. Isso irá abrir o arquivo 
`$VIMRUNTIME/doc/helphelp.txt` em uma nova janela e pular para a marca `:help` 
dentro desse arquivo.

Algumas regras simples:

- opções são colocadas dentro de aspas curvas simples (`'`, e não ``` ` ```),
  como em `:h 'textwidth'` 
- funções de VimL terminam em (), como em `:h reverse()`
- comandos começam com :, como em `:h :echo`

Você pode usar `<c-d>` (isso quer dizer <kbd>ctrl</kbd>+<kbd>d</kbd>) para
listar todas as marcas ("_tags_") que correspondem com o termo pesquisado em
questão. Por exemplo, `:h tab<c-d>` irá lhe mostrar uma lista de todas as marcas
desde `tab` até `'softtabstop'` e `setting-guitablabel`.

Você quer listar todas as funções de VimL? Simples: `:h ()<c-d>`. Você quer
listar todas as funções de VimL relacionadas as janelas ("_windows_")? `:h
win*()<c-d>`.

Isso rapidamente fica instintivo, mas especialmente no começo, você não sabe nem
sequer uma parte da marca que está procurando. Você apenas pode imaginar algumas
palavras chave que podem estar envolvidas. `:helpgrep` irá salvar!

```
:helpgrep backwards
```

Isso irá procurar por "backwards" em toda a documentação e irá pular para a
primeira ocorrência. As ocorrências serão agrupadas em uma lista de conserto
rápido ("_quickfix list_"). Use `:cn`/`:cp` para pular para a próxima/última 
ocorrência. Ou use `:copen` para abrir a janela de conserto rápido, navegar para
uma ocorrência e apertar `<cr>` para pular para o ocorrência em questão. Veja
`:h quickfix` para conhecer a verdade.

## Conseguindo ajuda desconectado (alternativa)

Esta lista foi compilada por @chrisbra, um dos desenvolvedores mais ativos do
Vim, e foi postada na [vim_dev](https://groups.google.com/forum/#!forum/vim_dev).

Está sendo repostada aqui com algumas poucas alterações.

---

Se você sabe o quê está procurando, é normalmente mais fácil procurar usando o
sistema de ajuda, pois os assuntos seguem um certo guia de estilo.

Outra coisa, o sistema de ajuda tem a vantagem de pertencer à sua versão em
particular do Vim, de modo que tópicos obsoletos ou tópicos que foram
adicionados mais tarde não irão aparecer.

Por isso que é importante aprender a usar o sistema de ajuda e a linguagem que
ele usa. Aqui vão alguns exemplos (não necessariamente completo, e eu devo ter
me esquecido de alguma coisa).

1. Opções são colocadas entre aspas únicas e simples. Então você usaria `:h
   'list'` para ir para o tópico de ajuda para a opção "list". Se você só sabe
   que está procurando por uma certa opção, você também pode fazer `:h
   options.txt` para abrir a página de ajuda que descreve como que todas as
   opções são tratadas, e a partir daí usar expressões regulares, como `/width`.
   Algumas opções possuem nome próprio, como `: h cpo-a`, `:h cpo-A`, `:h
   cpo-b`, e assim por diante.

2. Comandos do modo normal são apenas isso mesmo. Use `:h gt` para ir para a
   página de ajuda do comando "gt".

3. Expressões regulares ("_regexp_") sempre começam com "/", então `:h /\+` leva
   você para a página de ajuda do itém quantificador "\+" nas expressões
   regulares do Vim. Se você precisa aprender alguma coisa sobre expressões
   regulares, comece lendo em `:h pattern.txt`.

4. Combinações de teclas. Elas normalmente começam com uma única letra indicando
   o modo para o qual elas podem ser usadas. Por exemplo, `:h i_CTRL-X` irá
   levar você para a família dos comandos com CTRL-X para o modo de inserção,
   que podem ser usados para autocompletar diferentes coisas. Repare que certas
   chaves serão sempre escritas da mesma maneira, por exemplo Control sempre
   será CTRL. Atenção também para o fato de que para os comandos para o modo
   normal, o "n" é deixado de fora, como em `:h CTRL-A`. Por outro lado, `:h
   c_CTRL-R` irá descrever o quê CTRL-R faz quando estiver escrevendo comandos
   na linha de comando, e `:h g_CTRL-A` fala sobre o comando g<C-A> (portanto
   você precisa apertar "g" e em seguida <Ctrl-A>). Aqui o "g" se refere ao
   comando "g" do modo normal, que sempre espera uma segunda tecla antes de
   fazer alguma coisa, os comandos començando com "z" também agem de forma
   parecida.

5. Registradores sempre começam com "quote", portanto use `:h quote` para saber
   mais sobre o registrador especial ":".

6. Vim script (VimL) está disponível em `:h eval.txt`. Certos aspectos da língua
   estão disponíveis em `:h expr-X` onde 'X' é um caractere único, como em `:h 
   expr-!` que irá lhe levar ao tópico que descreve o (Não) operador '!' para
   VimL. Também importante, veja `:h function-list` para encontrar uma curta
   descrição de todas as funções disponíveis.
   
7. Mapeamentos são encontrados na página de ajuda `:h map.txt`. Use `:h
   mapmode-i` para descobrir mais sobre o comando `:imap`. Use também  `:h
   map-tópico` para saber mais sobre certos subtópicos sobre mapeamentos (como
   em `:h :map-local` para mapeamentos localizados/específicos a um buffer ou
   `:h map_bar` para como lidar com a '|' em mapeamentos.

8. Definições de comandos são encontradas em `:h command-*`, portanto use `:h
   command-bang` para saber sobre o argumento '!' para comandos customizados.

9. Comandos para o gerenciamento de janelas sempre começam com CTRL-W, portanto
   você encontra a ajuda correspondente em `:h CTRL-W_*` (por exemplo `:h
   CTRL-W_p` para mudar a janela acessada anteriormente). Você também pode
   acessar `:h windows.txt` e olhar tudo, caso esteja procurando por um comando
   para lidar com janelas.

10. Comandos Ex sempre começam com ":", portanto `:h :s` cobre o comando ":s".

11. Use CTRL-D após digitar um tópico e deixe o Vim completar com todos os
    tópicos disponíveis.

12. Use `:helpgrep` para fazer uma busca em todas as páginas de ajuda
    (geralmente também inclui as páginas de ajuda instaladas por plugins). Veja
    `:h :helpgrep` para saber como a usar. Uma vez que você tenha buscado por um
    tópico, todos os resultados estarão disponíveis na janela da [lista de
    conserto rápido ou de
    localização](#listas-de-conserto-rápido-e-de-localização) que podem ser
    abertas com `:copen` ou `:lopen`. Uma vez lá, você pode usar `/` para
    filtrar os resultados ainda mais. 

13. `:h helphelp` contém alguma informação sobre como usar a ajuda.

14. O manual do usuário. Ele irá descrever os tópicos de ajuda para iniciantes
    em uma maneira até amigável. Comece em `:h usr_toc.txt` para encontrar a
    tabela de conteúdo. Passe o olho por essa ajuda para encontrar certos
    tópicos, como por exemplo você encontrará uma entrada chamada "Digraphs" e
    "Entering special characters" no capítulo 24 (então use `:h usr_24.txt` para
    ir para a página de ajuda em particular).

15. Grupos de realçamentos ("_Highlighting groups_") sempre iniciam com `hl-*`.
    Por exemplo, `:h hl-WarningMsg` fala sobre o grupo "WarningMsg" de
    realçamento.

16. Realçamento de sintáxe ("_syntax highlighting_") é renomeado para
    ":syn-tópico", como em `:h :syn-conceal` que fala sobre o argumento
    "conceal" para o comando `:syn`.

17. Comandos de conserto rápido ("quickfix") geralmente começam com ":c",
    enquanto que os comandos da lista de localização geralmente começam com
    ":l".

18. A página `:h BufWinLeave` fala sobre o autocmd BufWinLeave ("_deixar a
    janela do buffer_"). Também `:h autocommands-events` fala sobre todos os
    eventos possíveis.

19. Argumentos de inicialização sempre começam com "-", então `:h -f` irá lhe
    levar a página de ajuda do comando "-f" para iniciar o Vim.

20. Funções extras compiladas sempre começam com "+", então `:h +conceal` fala
    sobre o suporte a função "conceal" compilada.

21. Códigos de erro podem ser buscados diretamente na ajuda. `:h E297` irá
    exatamente para a descrição da mensagem do erro. Entretanto algumas vezes,
    esses códigos de erro não estão descritos, mas sim listados no comando do
    Vim que os causa. Como em `:h hE128` que o levará diretamente para o comando
    `:function`.

22. A documentação para arquivos de sintáxe incluídos geralmente estão
    disponíveis em `:h ft-*-syntax`. Por exemplo, `:h ft-c-syntax` fala sobre o
    arquivo de sintáxe C e as opções que ele apresenta. Algumas vezes, seções
    adicionais para a omni autocomplementação (`:h ft-php-omni`) ou plugins de
    tipos de arquivo (`:h ft-tex-plugin`) estão disponíveis.

Também, um linque para a documentação do usuário (que por sua vez descreve
certos comandos mais da perspectiva do usuário e de forma menos detalhada)
serão mencionados no topo das páginas de ajuda caso estejam disponíveis.
Portanto, `:h pattern.txt` menciona os tópicos `:h 03.9` e `:h usr_27` do guia
do usuário.

## Conseguindo ajuda conectado

Caso tenha um problema que não consiga resolver ou precise de uma orientação
geral, veja o grupo de e-mail [vim_use](https://groups.google.com/forum/#!forum/vim_use) (em inglês).
Um outro ótimo recurso é usar o [IRC](https://pt.wikipedia.org/wiki/Internet_Relay_Chat). O canal `#vim` na [Freenode](https://freenode.net) é grande e 
geralmente cheio de gente disposta a ajudar.

Se você quiser reportar um bug no Vim, use a lista de e-mails 
[vim_dev](https://groups.google.com/forum/#!forum/vim_dev).

## Autocmds na prática

Você pode ativar qualquer evento agora mesmo com: `:doautocmd BufRead`.

### Eventos do usuário
#### User events

Especialmente para plugins, vale a pena criar os seus próprios eventos de
usuário:

```vim
function! Aleatoriedade()
  " Um monte de coisa tá acontecendo aqui.
  " E por útlimo...
  doautocmd User AleatoriedadeSaida
endfunction
```

Agora os usuários do seu plugin pode executar qualquer coisa assim que
Aleatoriedade terminar de rodar:

```vim
autocmd User AleatoriedadeSaida call AleatoriedadeCleanup()
```

A propósito, se não houver nenhum comando :autocmd para ser encontrado,
:doautocmd vai jogar uma mensagem irritado "No matching autocommands". É por
isso que muitos plugins usam `silent doautocmd ...`. Mas isso também possui
a desvantagem que você não pode simplesmente usar `echo foo` no :autocmd, você
precisa usar `unsilent echo "foo"`.

É por isso que é melhor checar se ao menos existe o recebimento de um autocmd e
não se incomodar de emitir uma mensagem em caso contrário:

```vim
if exists('#User#AleatoriedadeSaida')
  doautocmd User AleatoriedadeSaida
endif
```

Ajuda: `:h User`

### Autocmds aninhados

Por padrão, autocmds não aninham! Se um autocmd executa um comando, que em
seguida iria geralmente ativar um outro evento, isso não irá acontecer.

Vamos supor que você queira que abrir o seu vimrc automaticamente toda vez que o
Vim for inicializado:

```vim
autocmd VimEnter * edit $MYVIMRC
```

A partir de agora, quando o Vim for inicializado, o seu vimrc será aberto, mas a
primeira coisa que você irá notar é que não haverá nenhum realce que normalmente
haveria.

O problema é que `:edit` no seu autocmd não-aninhado não irá ativar o evento
"BufRead", portanto o tipo de arquivo ("_filetype_") não será configurado para
"vim" e `$VIMRUNTIME/syntax/vim.vim` nunca será originado. Veja `:au BufRead
*.vim`. Use isso ao invés:

```vim
autocmd VimEnter * nested edit $MYVIMRC
```

Ajuda: `:h autocmd-nested`

## Área de transferência
#### Clipboard

Recursos [necessários](#que-tipo-de-vim-eu-estou-rodando): `+Clipboard` e
opcionalmente `+xterm_clipboard` caso queira usar a opção `+clipboard` em um
sistema Unix com o Vim mas que não suporta interface gráfica.

Ajuda:

```
:h 'clipboard'
:h gui-clipboard
:h gui-selections
```

Veja também: [Colar entre parenteses (ou por que preciso configurar 'paste' o
tempo
todo?)](#colar-entre-parenteses-ou-por-que-preciso-configurar-paste-o-tempo-todo)

### Utilização da área de transferência (Windows, OSX)

O Windows vem com [clipboard](https://msdn.microsoft.com/en-us/library/windows/desktop/ms649012(v=vs.85).aspx)
e OSX vem com uma [pasteboard](https://developer.apple.com/library/mac/documentation/Cocoa/Conceptual/PasteboardGuide106/Introduction/Introduction.html#//apple_ref/doc/uid/TP40008100-SW1).

Ambos funcionam mais ou menos como usuários esperariam que funcionassem. Você
copia o texto selecionado com `ctrl+c`/`cmd+c` e cola em um outro aplicativo com `ctrl+v`/`cmd+v`.  

Repare que o texto copiado é naverdade transferido para a área de transferência
("_clipboard_"), e por isso você pode fechar o aplicativo onde copiou o texto
antes de colar em um outro aplicativo sem problemas.

Quando quer que isso aconteça, o registro `*` da área de transferência é
preenchido com a seleção. A partir do Vim, use `"*y"` e `"+p` para copiar e
colar para dentro ou para fora da área de transferência respectivamente.

Se você nem sequer quer ter que especificar o registrador `*` todo o tempo,
coloque isso no seu vimrc:

```vim
set clipboard=unnamed
```

Geralmente todas as operações de copiar/deletar/colocar ("_yank/delete/put_")
preencheriam o registrador `"`, mas agora o registrador `*` é usado para as
mesmas operações, e portanto, simplesmente `y` e `p` serão suficiente.

Deixe-me repetir: usar a opção acima quer dizer que todo e qualquer
copiar/colar, até mesmo quando usado apenas na mesma janela do Vim, todos irão
alterar a área de transferência. Decida por conta própria se isso é útil ou não.

Se você tem preguiça até mesmo de digitar `y`, você pode enviar cada seleção
visual para a área de transferência usando essas configurações:

```vim
set clipboard=unnamed,autoselect
set guioptions+=a
```

Ajuda:

```
:h clipboard-unnamed
:h autoselect
:h 'go_a'
```

### Utilização da área de transferência (Linux, BSD, ...)

Se o seu sistema operacional (SO) faz uso do [X](http://www.x.org/wiki), as
coisas são um pouco diferentes. O X implementa o [Protocolo de Janela de
Sistema X](http://www.x.org/releases/X11R7.7/doc/xproto/x11protocol.html) que
está em na versão principal 11 desde 1987, e por isso o X é normalmente chamado
de X11.

Antes, o X10, [cut buffers](http://www.x.org/releases/X11R7.7/doc/xorg-docs/icccm/icccm.html#Peer_to_Peer_Communication_by_Means_of_Cut_Buffers) foram introduzidos e meio que funcionaram como que uma espécie 
de _área de transferência_ já o texto copiado era na verdade mantido pelo X e
podia ser acessado a partir de outros aplicativos. Esse mecanismo ainda existe
no X, mas o seu uso foi discontinuado e a maioria dos programas não mas faz uso
dele.

Hoje em dia o dado é transferido entre aplicativos pelo meio de [seleções][selections](http://www.x.org/releases/X11R7.7/doc/xorg-docs/icccm/icccm.html#Peer_to_Peer_Communication_by_Means_of_Selections).
Dos 3 _átomos de seleção_ definos, apenas 2 estão em uso na prática: PRIMARY e
CLIPBOARD ("_primário_" e "_área de transferência_" respectivamente).

Grosseiramente falando, as seleções funcionam mais ou menos assim:

```
Programa A: <ctrl+c>
Programa A: assegura a posse da área de transferênci (CLIPBOARD)
Programa B: <ctrl+v>
Programa B: nota que a posse da área de transferência é mantida pelo Programa A
Programa B: pede dado Programa A
Programa A: responde ao pedido e envia o dado ao Programa B
Programa B: recebe dado do Programa A e o insere na janela
```

| Seleção | Quando é usado? | Como colar? | Como acessar pelo Vim? |
|-----------|------------|---------------|-------------------------|
| PRIMÁRIA ("_PRIMARY_")   | Selecionando texto              | `Clicando com o botão do meio do mouse`, `shift+insert` | Registrador `*` |
| Área de transferência ("_CLIPBOARD_") | Selecionando texto e `ctrl+c` | `ctrl+v`                       | Registrador `+` |

**NOTA**: Seleções (não, nem mesmo as seleções da Área de Transferência) não são
nunca mantidas no servidor X! Portanto, você perde o dado copiado com `ctrl+c`
quando o aplicativo é encerrado.

Use `"*p` para colar a seleção PRIMÁRIA ou `"+y1g" para copiar o arquivo inteiro
para a seleção da Área de Transferência.

Caso você se veja tendo que acessar um desses dois registradores o tempo todo,
considere usar:

```vim
set clipboard^=unnamed      " * register
" ou
set clipboard^=unnamedplus  " + register
```

(O `^=` é usado para antecipar para o valor padrão, `:h :set^=`.)

Isso irá fazer com que todo e qualquer copiar/deletar/colocar
("_yank/delete/put_") façam uso do registrador `*` ou do registrador `+`, ao
invés de usar o registrados não nomeado `"` ("_unamed register_"). Em seguida
você pode usar simplemente `y` ou `p` para acessar a seleção do X escolhida.

Ajuda:

```vim
:h clipboard-unnamed
:h clipboard-unnamedplus
```

## Restaurar posição do cursor ao abrir arquivo

Sem isso, você sempre estará na primeira linha ao abrir um arquivo. Com isso,
você estará na posição em que você estava quando partiu anteriormente.

Coloque isso no seu vimrc:

```vim
autocmd BufReadPost *
    \ if line("'\"") > 1 && line("'\"") <= line("$") |
    \   exe "normal! g`\"" |
    \ endif
```

Isso simplesmente faz `` g`" `` (pula para a posição em que você estava quando
você saiu sem alterar a lista de pulos) se a posição ainda existir (o arquivo
pode ter algumas linhas a menos desde que foi alterado por um outro programa).

Isso requer o uso do arquivo vimfile: `:h viminfo-'`.

## Handling backup, swap, undo, and viminfo files

Depending on the options, Vim creates up to 4 kinds of working files.

**Arquivos de backup**:

Você pode falar pro Vim manter um arquivo de backup do arquivo original antes de
salvar. Por padrão, Vim o mantém um backup, mas o remove imediatamente, logo
após o arquivo ser salvo com sucesso (`:set writebackup`). Caso você queira que
o último backup persista, `:set backup`. Ou você pode desativar todos os backups
de uma vez, `:set nobackup nowritebackup`.


Vejamos o quê que eu adicionei ao meu vimrc por último...

```
$ diff ~/.vim/vimrc ~/.vim/files/backup/vimrc-vimbackup
390d389
< command! -bar -nargs=* -complete=help H helpgrep <args>
```

Ajuda: `:h backup`

**Arquivos de troca (swap)**:

Você teve uma ideia para o melhor romance de ficção científica de todos os
tempos. Depois de passar horas em um bom ritmo escrevendo várias centenas de
milhares de palavras... acaba a bateria! Esse é o momento em que você se dá
conta que a última vez em que você salvou `~/wicked_alien_invaders_from_outer_space.txt` foi... bem, você nunca tinha salvado.

Mas nem toda a esperança está perdida! Ao editar um arquivo, o Vim cria um
arquivo de troca que contém mudanças que não foram salvas. Tente você mesmo,
abra qualquer arquivo e consiga o arquivo de troca atual usando `:swapname`.
Você também pode desativar arquivos de troca colocando `:set noswapfile` no seu
vimrc.

Por padrão, o arquivo de troca é criado no mesmo diretório que o arquivo editado
e chamado de algo como `.file.swp`, atualizado tanto a cada 200 caractéres ou
quando você não tenha digitado nada por 4 segundos, e deletado quando você pára
de editar o arquivo. Você pode mudar esses números com `:h 'updatecount'` e `:h
updatetime'`.

Por causa da queda de bateria, o arquivo de troca nunca foi deletado. Se você
fizer `vim ~/wicked_alien_invaders_from_outer_space.txt`, o Vim irá te perguntar
se você quer recuperar o arquivo.

Ajuda: `:h swap-file` e `:h usr_11`.

**Arquivos de desfazares (Undo files)**:

A [árvore do desfazer](#árvore-do-desfazer) é mantida em memória e será perdida
quando o Vim for encerrado. Se você quiser que ela persista, `:set undofile`.
Isso irá salvar o arquivo de desfazares para `~/foo.c` em `~/foo.ce.un~`.

Ajuda: `:h 'undofile'` e `:h undo-persistence`

**Viminfo file**:

When backup, swap, and undo files are all about text state, viminfo files are
used for saving everything else that would otherwise be lost when quitting Vim.
The viminfo file keeps histories (command line, search, input), registers,
marks, buffer list, global variables etc.

By default, the viminfo is written to `~/.viminfo`.

Help: `:h viminfo` and `:h 'viminfo'`

---

If you're anything like me, you prefer keeping all these files in the same
place, e.g. `~/.vim/files`:

```
set backup
set backupdir   =$HOME/.vim/files/backup/
set backupext   =-vimbackup
set backupskip  =
set directory   =$HOME/.vim/files/swap//
set updatecount =100
set undofile
set undodir     =$HOME/.vim/files/undo/
set viminfo     ='100,n$HOME/.vim/files/info/viminfo
```

The directory `~/.vim/files` has to be created beforehand, otherwise Vim will
spew errors. If you often work on new hosts, you might want to automate it:

```vim
if exists('*mkdir') && !isdirectory($HOME.'/.vim/files')
  call mkdir($HOME.'/.vim/files')
endif
```

NOTE: If you edit a file on a multi-user system and Vim prompts you that a swap
file already exists, it probably means that someone else is editing the file at
the moment. You lose this "feature" when you save your swap files in the home
directory.

## Editing remote files

Vim comes with the netrw plugin that enables editing remote files. Actually it
transfers the remote file to a local temporary file via scp, opens a buffer
using that file, and writes the changes back to the remote file on saving.

This is extremely useful if you want to use your local configuration opposed to
ssh'ing into a server and use whatever the admins want you to use.

```
:e scp://bram@awesome.site.com/.vimrc
```

If you have a `~/.ssh/config` set up already, this gets used automatically:

```
Host awesome
    HostName awesome.site.com
    Port 1234
    User bram
```

Assuming the above content in `~/.ssh/config`, this works just as well:

```
:e scp://awesome/.vimrc
```

Similar can be done with a `~/.netrc`, see `:h netrw-netrc`.

Make sure to read `:h netrw-ssh-hack` and `:h g:netrw_ssh_cmd`.

---

Another possibility is using [sshfs](https://wiki.archlinux.org/index.php/Sshfs)
which uses [FUSE](https://en.wikipedia.org/wiki/Filesystem_in_Userspace) to
mount a remote filesystem into your local filesystem.

## Managing plugins

[Pathogen](https://github.com/tpope/vim-pathogen) was the first popular tool for
managing plugins. Actually it just adjusts the _runtimepath_ (`:h 'rtp'`) to
include all the things put under a certain directory. You have to clone the
repositories of the plugins there yourself.

Real plugin managers expose commands that help you to install and update plugins
from within Vim. Hereinafter is a list of commonly used plugin managers:

- [dein](https://github.com/Shougo/dein.vim)
- [plug](https://github.com/junegunn/vim-plug)
- [vim-addon-manager](https://github.com/MarcWeber/vim-addon-manager)
- [vundle](https://github.com/VundleVim/Vundle.vim)

## Block insert

This is a technique to insert the same text on multiple consecutive lines at the
same time. See this
[demo](https://raw.githubusercontent.com/mhinz/vim-galore/master/contents/images/content-block_insert.gif).

Switch to visual block mode with `<c-v>`. Afterwards go down for a few lines.
Hit `I` or `A` and start entering your text.

It might be a bit confusing at first, but text is always entered for the current
line and only after finishing the current insertion, the same text will be
applied to all other lines of the prior visual selection.

So a simple example is `<c-v>3jItext<esc>`.

If you have lines of different length and want to append the same text right
after the end of each line, do this: `<c-v>3j$Atext<esc>`.

Sometime you need to place the cursor somewhere after the end of the current
line. You can't do that by default, but you can set the `virtualedit` option:

```vim
set virtualedit=all
```

Afterwards `$10l` or `90|` work even after the end of the line.

See `:h blockwise-examples` for more info. It might seem complicated at first,
but quickly becomes second nature.

If you want to get real fancy, have a look at
[multiple-cursors](https://github.com/terryma/vim-multiple-cursors).

## Running external programs and using filters

Disclaimer: Vim is single-threaded, so running an external program in the
foreground will block everything else. Sure, you can use one of Vim's
programming interfaces, e.g. Lua, and use its thread support, but during that
time the Vim process is blocked nevertheless. Neovim fixed that by adding a
proper job API.

(Apparently Bram is thinking about adding job control to Vim as well. If you
have a very recent version, see `:helpgrep startjob`.)

Use `:!` to start a job. If you want to list the files in the current working
directory, use `:!ls`. Use `|` for piping in the shell as usual, e.g. `:!ls -1 |
sort | tail -n5`.

Without a range, the output of `:!` will be shown in a scrollable window. On the
other hand, if a range is given, these lines will be
[filtered](https://en.wikipedia.org/wiki/Filter_(software)). This means they
will be piped to the
[stdin](https://en.wikipedia.org/wiki/Standard_streams#Standard_input_.28stdin.29)
of the filter program and after processing be replaced by the
[stdout](https://en.wikipedia.org/wiki/Standard_streams#Standard_output_.28stdout.29)
of the filter. E.g. for prepending numbers to the next 5 lines, use this:

    :.,+4!nl -ba -w1 -s' '

Since manually adding the range is quite burdensome, Vim also provides some
helpers for convenience. As always with ranges, you can also select lines in
visual mode and then hit `:`. There's also an operator `!` that takes a motion.
E.g. `!ip!sort` will sort the lines of the current paragraph.

A good use case for filtering is the [Go programming
language](https://golang.org). The indentation is pretty opinionated, it even
comes with a filter called `gofmt` for indenting Go source code properly. So
plugins for Go often provide helper commands called `:Fmt` that basically do
`:%!gofmt`, so they indent all lines in the file.

People often use `:r !prog` to put the output of prog below the current line,
which is fine for scripts, but when doing it on the fly, I find it easier to use
`!!ls` instead, which replaces the current line.

    :h filter
    :h :read!

## Cscope

[Cscope](http://cscope.sourceforge.net/) does more things than
[ctags](http://ctags.sourceforge.net/), but only supports C (and C++ and Java to
some extent).

Whereas a tags file only knows where a symbol was defined, a cscope database
knows much more about your data:

- Where is this symbol defined?
- Where is this symbol used?
- What is this global symbol's definition?
- Where did this variable get its value?
- Where is this function in the source files?
- What functions call this function?
- What functions are called by this function?
- Where does the message "out of space" come from?
- Where is this source file in the directory structure?
- What files include this header file?

### 1. Build the database

Do this in the root of your project:

```sh
$ cscope -bqR
```

This will create 3 files: `cscope{,.in,.po}.out` in the current working
directory. Think of them as your database.

Unfortunately `cscope` only analyzes `*.[c|h|y|l]` files by default. If you want
to use cscope for a Java project instead, do this:

```sh
$ find . -name "*.java" > cscope.files
$ cscope -bq
```

### 2. Add the database

Open a connection to your freshly built database:

```vim
:cs add cscope.out
```

Verify that the connection was made:

```vim
:cs show
```

(Yes, you can add multiple connections.)

### 3. Query the database

```vim
:cs find <kind> <query>
```

E.g. `:cs find d foo` will list all functions that are called by `foo(...)`.

| Kind | Explanation |
|------|-------------|
| s    | **s**ymbol: find all references to the token        |
| g    | **g**lobal: find global definition(s) of the token  |
| c    | **c**alls: find all calls to the function           |
| t    | **t**ext: find all instances of the text            |
| e    | **e**grep: egrep search for the word                |
| f    | **f**ile: open the filename                         |
| i    | **i**ncludes: find files that include the filename  |
| d    | **d**epends: find functions called by this function |

I suggest some convenience mappings e.g.:

```vim
nnoremap <buffer> <leader>cs :cscope find s  <c-r>=expand('<cword>')<cr><cr>
nnoremap <buffer> <leader>cg :cscope find g  <c-r>=expand('<cword>')<cr><cr>
nnoremap <buffer> <leader>cc :cscope find c  <c-r>=expand('<cword>')<cr><cr>
nnoremap <buffer> <leader>ct :cscope find t  <c-r>=expand('<cword>')<cr><cr>
nnoremap <buffer> <leader>ce :cscope find e  <c-r>=expand('<cword>')<cr><cr>
nnoremap <buffer> <leader>cf :cscope find f  <c-r>=expand('<cfile>')<cr><cr>
nnoremap <buffer> <leader>ci :cscope find i ^<c-r>=expand('<cfile>')<cr>$<cr>
nnoremap <buffer> <leader>cd :cscope find d  <c-r>=expand('<cword>')<cr><cr>
```

So, when `:tag` (or `<c-]>`) jumps to a definition from the tags file, `:cstag`
does the same, but also takes connected cscope databases into account. The
option `'cscopetag'` makes `:tag` act like `:cstag` automatically. This is very
convenient if you already have tag-related mappings.

Help: `:h cscope`

## MatchIt

Since Vim is written in C, a lot of features assume C-like syntax. By default,
if your cursor is on `{` or `#endif`, you can use `%` to jump to the
corresponding `}` or `#ifdef` respectively.

Vim comes bundled with a plugin called matchit.vim which is not enabled by
default. It makes `%` also cycle through HTML tags, if/else/endif constructs in
VimL etc. and introduces a few new commands.

#### Installation for Vim 8

```vim
" vimrc
packadd! matchit
```

#### Installation for Vim 7 and older

```vim
" vimrc
runtime macros/matchit.vim
```

Since the documentation of matchit is pretty extensive, I suggest also doing the
following once:

```vim
:!mkdir -p ~/.vim/doc
:!cp $VIMRUNTIME/macros/matchit.txt ~/.vim/doc
:helptags ~/.vim/doc
```

#### Small intro

The plugin is ready to use now. See `:h matchit-intro` for the supported
commands and `:h matchit-languages` for the supported languages.

That said, it's easy to define your own matching pairs:

```vim
autocmd FileType python let b:match_words = '\<if\>:\<elif\>:\<else\>'
```

Afterwards you can cycle through these 3 statements in any Python file by using
`%` (forward) or `g%` (backward).

Help:

```
:h matchit-install
:h matchit
:h b:match_words
```

# Tips

## Saner behavior of n and N

The direction of `n` and `N` depends on whether `/` or `?` was used for
searching forward or backward respectively. This is pretty confusing to me.

If you want `n` to always search forward and `N` backward, use this:

```vim
nnoremap <expr> n  'Nn'[v:searchforward]
nnoremap <expr> N  'nN'[v:searchforward]
```

## Saner command-line history

If you're anything like me, you're used to going to next and previous items via
`<c-n>` and `<c-p>` respectively. By default, this also works in the
command-line and recalls older or more recent command-lines from history.

So far, so good. But `<up>` and `<down>` are even smarter! They recall the
command-line whose beginning matches the current command-line. E.g. `:echo <up>`
may change to `:echo "Vim rocks!"`.

Of course, I don't want you to reach to the arrow keys, just map it instead:

```vim
cnoremap <c-n>  <down>
cnoremap <c-p>  <up>
```

I depend on this behaviour several times a day.

## Saner CTRL-L

By default, `<c-l>` clears and redraws the screen (like `:redraw!`). The
following mapping does the same, plus de-highlighting the matches found via `/`,
`?` etc., plus fixing syntax highlighting (sometimes Vim loses highlighting due
to complex highlighting rules), plus force updating the syntax highlighting in
diff mode:

```vim
nnoremap <leader>l :nohlsearch<cr>:diffupdate<cr>:syntax sync fromstart<cr><c-l>
```

## Disable audible and visual bells

```vim
set noerrorbells
set novisualbell
set t_vb=
```

See [Vim Wiki: Disable beeping](http://vim.wikia.com/wiki/Disable_beeping).

## Quickly move current line

Sometimes I need a quick way to move the current line above or below:

```vim
nnoremap [e  :<c-u>execute 'move -1-'. v:count1<cr>
nnoremap ]e  :<c-u>execute 'move +'. v:count1<cr>
```

These mappings also take a count, so `2]e` moves the current line 2 lines below.

## Quickly add empty lines

```vim
nnoremap [<space>  :<c-u>put! =repeat(nr2char(10), v:count1)<cr>'[
nnoremap ]<space>  :<c-u>put =repeat(nr2char(10), v:count1)<cr>
```

Now `5[<space>` inserts 5 blank lines above the current line.

## Quickly edit your macros

This is a real gem! The mapping takes a register (or `*` by default) and opens
it in the cmdline-window. Hit `<cr>` when you're done editing for setting the
register.

I often use this to correct typos I did while recording a macro.

```vim
nnoremap <leader>m  :<c-u><c-r><c-r>='let @'. v:register .' = '. string(getreg(v:register))<cr><c-f><left>
```

Use it like this `<leader>m` or `"q<leader>m`.

Notice the use of `<c-r><c-r>` to make sure that the `<c-r>` is inserted
literally. See `:h c_^R^R`.

## Quickly jump to header or source file

This technique can probably be applied to many filetypes. It sets _file marks_
(see `:h marks`) when leaving a source or header file, so you can quickly jump
back to the last accessed one by using `'C` or `'H` (see `:h 'A`).

```vim
autocmd BufLeave *.{c,cpp} mark C
autocmd BufLeave *.h       mark H
```

**NOTE**: The info is saved in the viminfo file, so make sure that `:set
viminfo?` includes `:h viminfo-'`.

## Quickly change font size in GUI

I think this was taken from tpope's config:

```vim
command! Bigger  :let &guifont = substitute(&guifont, '\d\+$', '\=submatch(0)+1', '')
command! Smaller :let &guifont = substitute(&guifont, '\d\+$', '\=submatch(0)-1', '')
```

## Change cursor style dependent on mode

I like to use a block cursor in normal mode, i-beam cursor in insert mode, and
underline cursor in replace mode.

```vim
if empty($TMUX)
  let &t_SI = "\<Esc>]50;CursorShape=1\x7"
  let &t_EI = "\<Esc>]50;CursorShape=0\x7"
  let &t_SR = "\<Esc>]50;CursorShape=2\x7"
else
  let &t_SI = "\<Esc>Ptmux;\<Esc>\<Esc>]50;CursorShape=1\x7\<Esc>\\"
  let &t_EI = "\<Esc>Ptmux;\<Esc>\<Esc>]50;CursorShape=0\x7\<Esc>\\"
  let &t_SR = "\<Esc>Ptmux;\<Esc>\<Esc>]50;CursorShape=2\x7\<Esc>\\"
endif
```

This simply tells Vim to print a certain sequence of characters ([escape
sequence](https://en.wikipedia.org/wiki/Escape_sequence)) when entering/leaving
insert mode. The underlying terminal, or programs like
[tmux](https://tmux.github.io) that sit between Vim and the terminal, will
process and evaluate it.

There's one drawback though: there are many terminal emulator implementations
and not all use the same sequences for doing the same things. The sequences used
above might not work with your implementation. Your implementation might not
even support different cursor styles. Check the documentation.

The example above works with iTerm2.

## Don't lose selection when shifting sidewards

If you select one or more lines, you can use `<` and `>` for shifting them
sidewards. Unfortunately you immediately lose the selection afterwards.

You can use `gv` to reselect the last selection (see `:h gv`), thus you can work
around it like this:

```vim
xnoremap <  <gv
xnoremap >  >gv
```

Now you can use `>>>>>` on your visual selection without any problems.

**NOTE**: The same can be achieved using `.`, which repeats the last change.

## Reload a file on saving

Using [autocmds](#autocmds) you can do anything on saving a file, e.g. sourcing
it in case of a dotfile or running a linter to check for syntactical errors in
your source code.

```vim
autocmd BufWritePost $MYVIMRC source $MYVIMRC
autocmd BufWritePost ~/.Xdefaults call system('xrdb ~/.Xdefaults')
```

## Smarter cursorline

I love the cursorline, but I only want to use it in the current window and not
when being in insert mode:

```vim
autocmd InsertLeave,WinEnter * set cursorline
autocmd InsertEnter,WinLeave * set nocursorline
```

## Faster keyword completion

The keyword completion (`<c-n>`/`<c-p>`) tries completing whatever is listed in
the `'complete'` option. By default, this also includes tags (which can be
annoying) and scanning all included files (which can be very slow). If you can
live without these things, disable them:

```vim
set complete-=i   " disable scanning included files
set complete-=t   " disable searching tags
```

## Cosmetic changes to colorschemes

Always use a dark gray statusline, no matter what colorscheme is chosen:

```vim
autocmd ColorScheme * highlight StatusLine ctermbg=darkgray cterm=NONE guibg=darkgray gui=NONE
```

The same, but only for the "lucius" colorscheme (check `:echo
color_name` which should be set by all valid colorschemes):

```vim
autocmd ColorScheme lucius highlight StatusLine ctermbg=darkgray cterm=NONE guibg=darkgray gui=NONE
```

# Commands

Useful commands that are good to know. Use `:h :<command name>` to learn more
about them, e.g. `:h :global`.

## :global and :vglobal

Execute a command on all matching lines. E.g. `:global /regexp/ print` will use
`:print` on all lines that contain "regexp".

Fun fact: You probably all know good old grep, the filter program written by Ken
Thompson. What does it do? It prints all lines matching a certain regular
expression! Now guess the short form of `:global /regexp/ print`? That's right!
It's `:g/re/p`. Ken Thompson was inspired by vi's `:global` when he wrote grep.

Despite its name, `:global` only acts on all lines by default, but it also takes
a range. Assume you want use `:delete` on all lines from the current line to the
next blank line (matched by the regular expression `^$`) that contain "foo":

```vim
:,/^$/g/foo/d
```

For executing commands on all lines that do _not_ match a given pattern, use
`:global!` or its alias `:vglobal` (think _inVerse_) instead.

## :normal and :execute

These commands are commonly used in Vim scripts.

With `:normal` you can do normal mode mappings from the command-line. E.g.
`:normal! 4j` will make the cursor go down 4 lines (without using any custom
mapping for "j" due to the "!").

Mind that `:normal` also takes a count, so `:%norm! Iabc` would prepend "abc" to
every line.

With `:execute` you can mix commands with expressions. Assume you edit a C
source file and want to switch to its header file:

```vim
:execute 'edit' fnamemodify(expand('%'), ':r') . '.h'
```

Both commands are often used together. Assume you want to make the cursor go
down "n" lines:

```vim
:let n = 4
:execute 'normal!' n . 'j'
```

## :redir

Many commands print messages and `:redir` allows to redirect that output. You
can redirect to files, [registers](#registers) or variables.

```vim
:redir => neatvar
:reg
:redir END
:echo neatvar
:" For fun let's also put it onto the current buffer.
:put =nicevar
```

Help: `:h :redir`

# Debugging

## General tips

If you encounter a strange behaviour, try reproducing it like this:

```
vim -u NONE -N
```

This will start Vim without vimrc (thus default settings) and in nocompatible
mode (which makes it use Vim defaults instead of vi defaults). (See `:h
--noplugin` for other combinations of what to load at start.)

If you can still reproduce it now, it's most likely a bug in Vim itself! Report
it to the [vim_dev](https://groups.google.com/forum/#!forum/vim_dev) mailing
list. Most of the time the issue won't be resolved at this time and you'll have
to further investigate.

Plugins often introduce new/changed/faulty behaviour. E.g. if it happens on
saving, check `:verb au BufWritePost` to get a list of potential culprits.

If you're using a plugin manager, comment them out until you find the culprit.

Issue is still not resolved? If it's not a plugin, it must be your other
settings, so maybe your options or autocmds etc.

Time to use binary search. Repeatedly split the search space in two until you
find the culprit line. Due to the nature of binary division, it won't take many
steps.

In practice, it works like this: Put the `:finish` command in the middle of your
vimrc. Vim will skip everything after it. If it still happens, the problem is in
the active upper half. Move the `:finish` to the middle of _that_ half.
Otherwise, the issue is in the inactive lower half. Move the `:finish` to the
middle of _that_ half. And so on.

## Verbosity

Another useful way for observing what Vim is currently doing is increasing the
verbosity level. Currently Vim supports 9 different levels. See `:h 'verbose'`
for the full list.

```vim
:e /tmp/foo
:set verbose=2
:w
:set verbose=0
```

This would show all the files that get sourced, e.g. the undo file or various
plugins that act on saving.

If you only want increase verbosity for a single command, there's also
`:verbose`, which simply gets put in front of any other command. It takes the
verbosity level as count and defaults to 1:

```vim
:verb set verbose
"  verbose=1
:10verb set verbose
"  verbose=10
```

It's very often used with its default verbosity level 1 to show where an option
was set last:

```vim
:verb set ai?
"      Last set from ~/.vim/vimrc
```

Naturally, the higher the verbosity level the more overwhelming the output. But
fear no more, you can simply redirect the output to a file:

```vim
:set verbosefile=/tmp/foo | 15verbose echo "foo" | vsplit /tmp/foo
```

You can also enable verbosity at starting time, with the `-V` option. It
defaults to verbosity level 10. E.g. `vim -V5`.

## Profiling startup time

Vim startup feels slow? Time to crunch some numbers:

```
vim --startuptime /tmp/startup.log +q && vim /tmp/startup.log
```

The first column is the most important as it shows the elapsed absolute time. If
there is a big jump in time between two lines, the second line is either a very
big file or a file with faulty VimL code that is worth investigating.

## Profiling at runtime

Required [feature](#what-kind-of-vim-am-i-running): `+profile`

Vim provides a built-in capability for profiling at runtime and is a great way
to find slow code in your environment.

The `:profile` command takes a bunch of sub-commands for specifying what to
profile.

If you want to profile _everything_, do this:

```
:profile start /tmp/profile.log
:profile file *
:profile func *
<do something in Vim>
<quit Vim>
```

Vim keeps the profiling information in memory and only writes it out to the
logfile on exit. (Neovim has fixed this using `:profile dump`).

Have a look at `/tmp/profile.log`. All code that was executed during profiling
will be shown. Every line, how often it was executed and how much time it took.

Most of the time that will be plugin code the user isn't familiar with, but if
you're investigating a certain issue, jump to the bottom of the log. Here are
two different sections `FUNCTIONS SORTED ON TOTAL TIME` and `FUNCTIONS SORTED ON
SELF TIME` that are worth gold. At a quick glance you can see, if a certain
function is taking too long.

## Debugging Vim scripts

If you ever used a command-line debugger before, `:debug` will quickly feel
familiar.

Simply prepend `:debug` to any other command and you'll be put into debug mode.
That is, the execution will stop at the first line about to be executed and that
line will be displayed.

See `:h >cont` and below for the 6 available debugger commands and note that,
like in gdb and similar debuggers, you can also use their short forms: `c`, `q`,
`n`, `s`, `i`, and `f`.

Apart from that those, you're free to use any Vim command, e.g. `:echo myvar`,
which gets executed in the context of the current position in the code.

You basically get a
[REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) by
simply using `:debug 1`.

It would be a pain if you had to single-step through every single line, so of
course we can define breakpoints, too. (Breakpoints are called breakpoints,
because the execution stops when they're hit, thus you can simply skip code
you're not interested in.) See `:h :breakadd`, `:h :breakdel`, and `:h
:breaklist` for further details.

Let's assume you want to know what code is run every time you save a file:

```vim
:au BufWritePost
" signify  BufWritePost
"     *         call sy#start()
:breakadd func *start
:w
" Breakpoint in "sy#start" line 1
" Entering Debug mode.  Type "cont" to continue.
" function sy#start
" line 1: if g:signify_locked
>s
" function sy#start
" line 3: endif
>
" function sy#start
" line 5: let sy_path = resolve(expand('%:p'))
>q
:breakdel *
```

As you can see, using `<cr>` will repeat the previous debugger command, `s` in
this case.

`:debug` can be used in combination with the [verbose](#verbosity) option.

## Debugging syntax files

Syntax files are often the cause for slowdowns due to wrong and/or complex
regular expressions. If the `+profile` [feature](#what-kind-of-vim-am-i-running)
is compiled in, Vim provides the super useful `:syntime` command.

```vim
:syntime on
" hit <c-l> a few times to redraw the window which causes the syntax rules to get applied again
:syntime off
:syntime report
```

The output contains important metrics. E.g. you can see which regexp takes too
long and should be optimized or which regexps are used all the time but never
even match.

See `:h :syntime`.

# Miscellaneous

## Additional resources

| Resource | Description |
|----------|-------------|
| [Seven habits of effective text editing](http://www.moolenaar.net/habits.html) | By Bram Moolenaar, the author of Vim. |
| [Seven habits of effective text editing 2.0 (PDF)](http://www.moolenaar.net/habits_2007.pdf) | See above. |
| [IBM DeveloperWorks: Scripting the Vim editor](http://www.ibm.com/developerworks/views/linux/libraryview.jsp?sort_order=asc&sort_by=Title&search_by=scripting+the+vim+editor) | Five-part series on Vim scripting. |
| [Learn Vimscript the Hard Way](http://learnvimscriptthehardway.stevelosh.com) | Develop a Vim plugin from scratch. |
| [Practical Vim (2nd Edition)](http://www.amazon.com/Practical-Vim-Edit-Speed-Thought/dp/1680501275/) | Hands down the best book about Vim. |
| [Vimcasts.org](http://vimcasts.org/episodes/archive) | Vim screencasts. |
| [Why, oh WHY, do those #?@! nutheads use vi?](http://www.viemu.com/a-why-vi-vim.html) | Common misconceptions explained. |
| [Your problem with Vim is that you don't grok vi](http://stackoverflow.com/a/1220118) | Concise, informative and correct. A real gem. |

## Vim distributions

Vim distributions are bundles of custom settings and plugins for Vim.

More advanced users know how to configure their editor anyway, so distributions
are mostly targeted at beginners. If you think about that, it's quite
paradoxical though: Making it easier by adding even more things to learn about?

I know that many people don't want to spend hours and hours on customizing an
editor (and actually you never stop customizing your vimrc when you finally got
hooked), but eventually you only get efficient in Vim when you take the time to
learn it properly.

Repeat after me: "A programmer should know their tools."

Anyway, if you know what you're doing, you might draw some inspiration from
looking at a few distributions:

- [cream](http://cream.sourceforge.net)
- [janus](https://github.com/carlhuda/janus.git)
- [spacevim](https://github.com/SpaceVim/SpaceVim)
- [spf13](https://github.com/spf13/spf13-vim)

## Standard plugins

Surprising to many people, Vim comes with a handful of plugins on its own that
all get loaded by default. Check `:scriptnames` after starting Vim to see all
sourced files.

Most of them will never get used, so disable them as you see fit. They will
still be shown as sourced, but only the first lines actually get read before Vim
bails out. No further code (mappings, commands, logic) will be processed.

| Plugin     | Disable it using..                  | Help |
|------------|-------------------------------------|------|
| 2html      | `let g:loaded_2html_plugin = 1`     | `:h 2html` |
| getscript  | `let g:loaded_getscriptPlugin = 1`  | `:h pi_getscript` |
| gzip       | `let g:loaded_gzip = 1`             | `:h pi_gzip` |
| logipat    | `let g:loaded_logipat = 1`          | `:h pi_logipat` |
| matchparen | `let g:loaded_matchparen = 1`       | `:h pi_paren` |
| netrw      | `let g:loaded_netrwPlugin = 1`      | `:h pi_netrw` |
| rrhelper   | `let g:loaded_rrhelper = 1`         | `:e $VIMRUNTIME/plugin/rrhelper.vim` |
| spellfile  | `let g:loaded_spellfile_plugin = 1` | `:h spellfile.vim` |
| tar        | `let g:loaded_tarPlugin = 1`        | `:h pi_tar` |
| vimball    | `let g:loaded_vimballPlugin = 1`    | `:h pi_vimball` |
| zip        | `let g:loaded_zipPlugin = 1`        | `:h pi_zip` |

## Map CapsLock to Control

CapsLock belongs to the most useless keys on your keyboard, but it's much easier
to reach than the Control key, since it lies on your [home
row](https://raw.githubusercontent.com/mhinz/vim-galore/master/contents/images/content-homerow.png).
Mapping CapsLock to Control is a great way to prevent or at least reduce
[RSI](https://de.wikipedia.org/wiki/Repetitive-Strain-Injury-Syndrom) if you
program a lot.

Attention: When you get used to it, you can't live without it anymore.

**OSX**:

`System Preferences -> Keyboard -> Keyboard Tab -> Modifier Keys`. Change
"CapsLock" to "Control".

**Linux**:

To change the keys in X, put this in your `~/.xmodmap`:

    remove Lock = Caps_Lock
    keysym Caps_Lock = Control_L
    add Control = Control_L

Afterwards source it via `$ xmodmap ~/.xmodmap`.

An alternative would be using [caps2esc](https://github.com/oblitum/caps2esc) or
[xcape](https://github.com/alols/xcape).

**Windows**:

See [superuser.com: Map Caps-Lock to Control in Windows
8.1](http://superuser.com/questions/764782/map-caps-lock-to-control-in-windows-8-1).

## Easter eggs

| Command   | Message |
|-----------|---------|
| `:Ni!` | `Do you demand a shrubbery?` |
| `:h 'sm'` | `NOTE: Use of the short form is rated PG.` |
| `:h 42` | `What is the meaning of life, the universe and everything? Douglas Adams, the only person who knew what this question really was about is now dead, unfortunately.  So now you might wonder what the meaning of death is...` |
| `:h UserGettingBored` | `When the user presses the same key 42 times. Just kidding! :-)` |
| `:h bar` | `Ceci n'est pas une pipe.` |
| `:h holy-grail` | `You found it, Arthur!` |
| `:h map-modes` | `:nunmap can also be used outside of a monastery.` |
| `:help!` | `E478: Don't panic!` (Glitch? When used in a help buffer (`buftype=help`) this works like `:h help.txt` instead.) |
| `:smile` | Try it out yourself. ;-) Added in 7.4.1005. |

## Standard plugins

## Why hjkl for navigation?

When [Bill Joy](https://en.wikipedia.org/wiki/Bill_Joy) created
[vi](https://en.wikipedia.org/wiki/Vi), a predecessor of Vim, he did it on a
[ADM-3A](https://en.wikipedia.org/wiki/ADM-3A) which had no extra cursor buttons
but used, you might already guessed it, hjkl instead.

Keyboard layout: [click](https://raw.githubusercontent.com/mhinz/vim-galore/master/contents/images/content-adm-3a-layout.jpg)

This also shows why `~` is used to denote the home directory on Unix systems.

# Common problems

## Editing small files is slow

There are two things which can have a huge impact on performance:

1. Complex **regular expressions**. Particular the Ruby syntax file caused
   people to have slowdowns in the past. (Also see [Debugging syntax files](#debugging-syntax-files).)
2. **Screen redraws**. Some features force all lines to redraw.

| Typical culprit | Why? | Solution? |
|-----------------|------|-----------|
| `:set cursorline`        | Causes all lines to redraw. | `:set nocursorline` |
| `:set cursorcolumn`      | Causes all lines to redraw. | `:set nocursorcolumn` |
| `:set relativenumber`    | Causes all lines to redraw. | `:set norelativenumber` |
| `:set foldmethod=syntax` | If the syntax file is slow already, this makes it even worse. | `:set foldmethod=manual`, `:set foldmethod=marker` or [FastFold](https://github.com/Konfekt/FastFold) |
| `:set synmaxcol=3000`    | Due to internal representation, Vim has problems with long lines in general. Highlights columns till column 3000. | `:set synmaxcol=200` |
| matchparen.vim           | Loaded by default. Uses regular expressions to find the accompanying parenthesis. | Disable plugin: `:h matchparen` |

**NOTE**: You only need to do this if you experience actual performance
drawbacks. In most cases using the things mentioned above is absolutely fine.

## Editing huge files is slow

The biggest issue with big files is, that Vim reads the whole file at once. This
is done due to how buffers are represented internally.
([Discussion on vim_dev@](https://groups.google.com/forum/#!topic/vim_dev/oY3i8rqYGD4/discussion))

If you only want to read, `tail hugefile | vim -` is a good workaround.

If you can live without syntax, settings and plugins for the moment:

```
$ vim -u NONE -N
```

This should make navigation quite a lot faster, especially since no expensive
regular expressions for syntax highlighting are used. You should also tell Vim
not to use swapfiles and viminfo files to avoid long delays on writing:

```
$ vim -n -u NONE -i NONE -N
```

Putting it in a nutshell, try to avoid using Vim when intending to write really
huge files. :\

## Bracketed paste (or why do I have to set 'paste' all the time?)

Bracketed paste mode allows terminal emulators to distinguish between typed text
and pasted text.

Did you ever tried pasting code into Vim and afterwards everything seemed messed
up?

This only happens if you paste via `cmd+v`, `shift-insert`, `middle-click` etc.
because then you're just throwing text at the terminal emulator. Vim doesn't
know that you just pasted the text, it thinks you're an extremely fast typist.
Accordingly, it tries to indent the lines and fails.

Obviously this is not an issue, if you paste using Vim's registers, e.g. `"+p`,
because then Vim knows that you're actually pasting.

To workaround this, you have to `:set paste`, so it gets pasted as-is. See `:h
'paste'` and `:h 'pastetoggle'`.

If you're fed up with toggling `'paste'` all the time, have a look at this fine
plugin that does it for you:
[bracketed-paste](https://github.com/ConradIrwin/vim-bracketed-paste).

Additional read from the same author as the plugin:
[here](http://cirw.in/blog/bracketed-paste).

**Neovim**: Neovim tries to make all of this much more seamless and sets
bracketed paste mode automatically if the terminal emulator supports it.

## Delays when using escape key in terminal

If you live in the command-line, you probably use a so-called _terminal
emulator_ like xterm, gnome-terminal, iTerm2, etc. (opposed to a real
[terminal](https://en.wikipedia.org/wiki/Computer_terminal)).

Like their ancestors, terminal emulators use [escape
sequences](https://en.wikipedia.org/wiki/Escape_sequence) (or _control
sequences_) to control things like moving the cursor, changing text colors, etc.
They're simply strings of ASCII characters starting with an escape character
(displayed in [caret notation](https://en.wikipedia.org/wiki/Caret_notation) as
`^[`). When such a string arrives, the terminal emulator looks up the
accompanying action in the [terminfo](https://en.wikipedia.org/wiki/Terminfo)
database.

To make the problem clearer, I'll explain mapping timeouts first. They always
happen when there's ambiguity between mappings:

```vim
:nnoremap ,a  :echo 'foo'<cr>
:nnoremap ,ab :echo 'bar'<cr>
```

Both mappings work as expected, but when typing `,a`, there will be a delay of 1
second, because Vim waits whether the user keys in another `b` or not.

Escape sequences pose the same problem:

- `<esc>` is used a lot for returning to normal mode or quitting an action.
- Cursor keys are encoded using escape sequences.
- Vim expects <kbd>Alt</kbd> (also called _Meta key_) to send a proper 8-bit
  encoding with the high bit set, but many terminal emulators don't support it
  (or don't enable it by default) and send an escape sequence instead.

You can test the above like this: `vim -u NONE -N` and type `i<c-v><left>` and
you'll see a sequence inserted that starts with `^[` which denotes the escape
character.

Putting it in a nutshell, Vim has a hard time distinguishing between a typed
`<esc>` character and a proper escape sequence.

By default, Vim uses `:set timeout timeoutlen=1000`, so it delays on ambiguity
of mappings _and_ key codes by 1 second. This is a sane value for mappings, but
you can define the key code timeout on its own which is the most common
workaround for this entire issue:

```vim
set timeout           " for mappings
set timeoutlen=1000   " default value
set ttimeout          " for key codes
set ttimeoutlen=10    " unnoticeable small value
```

Under `:h ttimeout` you find a small table showing the relationship between
these options.

If you're using tmux between Vim and your terminal emulator, also put this in
your `~/.tmux.conf`:

```tmux
set -sg escape-time 0
```

## Function search undo

- A search pattern in a command (`/`, `:substitute`, ...) changes the "last used
  search pattern". (It's saved in the `/` register; print it with `:echo @/`).
- A simple text change can be redone with `.`. (It's saved in the `.` register;
  print it with `:echo @.`).

Both things are _not_ the case, if you do them from a function, though! Thus you
can't easily highlight words from a function or redo the text changes made by
it.

Help: `:h function-search-undo`

# Caprichos técnicos

## Nova linha usada para NUL

Caractéres NULOS (ou "_NUL characters_", `\0`) em um arquivo, são guardados como uma nova linha (ou "_Newline_", `\n`) na memória e mostrados em um buffer como `^@`.

Veja `man 7 ascii` e `:h NL-used-for-Nul` para mais informação.

# Lista de esquemas de cores

Aqui está uma lista de esquemas de cores que são comumente usados:

- [acme-colors](https://github.com/plan9-for-vimspace/acme-colors)
- [base16](https://github.com/chriskempson/base16-vim)
- [gotham](https://github.com/whatyouhide/vim-gotham)
- [gruvbox](https://github.com/morhetz/gruvbox)
- [janah](https://github.com/mhinz/vim-janah)
- [jellybeans](https://github.com/nanotech/jellybeans.vim)
- [lucius](https://github.com/jonathanfilip/vim-lucius)
- [molokai](https://github.com/tomasr/molokai)
- [railscasts](https://github.com/jpo/vim-railscasts-theme)
- [seoul256](https://github.com/junegunn/seoul256.vim)
- [solarized](https://github.com/altercation/vim-colors-solarized) (ou uma variação mais leve: [flattened](https://github.com/romainl/flattened))
- [tomorrow](https://github.com/chriskempson/vim-tomorrow-theme)
- [vividchalk](https://github.com/tpope/vim-vividchalk)
- [yowish](https://github.com/kabbamine/yowish.vim)
- [zenburn](https://github.com/jnurmine/Zenburn)

