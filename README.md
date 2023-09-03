# A Linguagem de Programação Rust

![Status de Build](https://github.com/rust-lang/book/workflows/CI/badge.svg)

Este repositório contém o código-fonte do livro "A Linguagem de Programação Rust em PT-BR".

[O livro está disponível em formato impresso pela No Starch Press (Em inglês)][nostarch].

[nostarch]: https://nostarch.com/rust-programming-language-2nd-edition

Você também pode ler o livro gratuitamente online. Por favor, consulte o livro conforme fornecido com
as versões mais recentes do Rust [estável], [beta], ou [nightly]. Esteja ciente de que problemas
nessas versões podem já ter sido corrigidos neste repositório, já que essas
versões são atualizadas com menos frequência.

[estável]: https://doc.rust-lang.org/stable/book/
[beta]: https://doc.rust-lang.org/beta/book/
[nightly]: https://doc.rust-lang.org/nightly/book/

Veja as [versões] para fazer o download apenas do código de todos os trechos de código que aparecem no livro.

[versões]: https://github.com/rust-lang/book/releases

## Requisitos

Para construir o livro, é necessário [mdBook], idealmente na mesma versão que
o rust-lang/rust utiliza neste [arquivo][rust-mdbook]. Para obtê-lo:

[mdBook]: https://github.com/rust-lang-nursery/mdBook
[rust-mdbook]: https://github.com/rust-lang/rust/blob/master/src/tools/rustbook/Cargo.toml

```bash
$ cargo install mdbook --version <número_da_versão>
```

## Construção

Para construir o livro, digite:

```bash
$ mdbook build
```

A saída estará no subdiretório `book`. Para conferir, abra-a em
seu navegador da web.

_Firefox:_
```bash
$ firefox book/index.html                       # Linux
$ open -a "Firefox" book/index.html             # OS X
$ Start-Process "firefox.exe" .\book\index.html # Windows (PowerShell)
$ start firefox.exe .\book\index.html           # Windows (Cmd)
```

_Chrome:_
```bash
$ google-chrome book/index.html                 # Linux
$ open -a "Google Chrome" book/index.html       # OS X
$ Start-Process "chrome.exe" .\book\index.html  # Windows (PowerShell)
$ start chrome.exe .\book\index.html            # Windows (Cmd)
```

Para executar os testes:

```bash
$ mdbook test
```

## Contribuindo

Adoraríamos sua ajuda! Por favor, veja [CONTRIBUTING.md][contrib] para saber sobre os
tipos de contribuições que estamos buscando.

[contrib]: https://github.com/rust-lang/book/blob/main/CONTRIBUTING.md

Como o livro é [impresso][nostarch], e porque queremos
manter a versão online do livro o mais próxima possível da versão impressa quando
possível, pode demorar mais do que você está acostumado para resolvermos seu problema
ou pull request.

Até agora, temos feito uma grande revisão para coincidir com [Edições Rust](https://doc.rust-lang.org/edition-guide/). Entre essas revisões maiores, só estaremos corrigindo erros. Se seu problema ou pull request
não está estritamente corrigindo um erro, ele pode ficar pendente até a próxima vez que estivermos
trabalhando em uma grande revisão: espere algo em torno de meses ou anos. Agradecemos
pela sua paciência!

### Traduções

Adoraríamos ajuda para traduzir o livro! Veja a etiqueta [Traduções] para participar
de esforços que estão atualmente em andamento. Abra uma nova issue para começar a trabalhar
em uma nova língua! Estamos aguardando o [suporte do mdbook] para múltiplos idiomas
antes de mesclarmos qualquer um, mas sinta-se à vontade para começar!

[Traduções]: https://github.com/rust-lang/book/issues?q=is%3Aopen+is%3Aissue+label%3ATranslations
[suporte do mdbook]: https://github.com/rust-lang-nursery/mdBook/issues/5

## Verificação Ortográfica

Para verificar arquivos de origem em busca de erros de ortografia, você pode usar o script `spellcheck.sh`
disponível no diretório `ci`. Ele precisa de um dicionário de palavras válidas,
que é fornecido em `ci/dictionary.txt`. Se o script produzir um falso
positivo (digamos, você usou a palavra `BTreeMap`, que o script considera inválida),
você precisa adicionar essa palavra ao `ci/dictionary.txt` (mantenha a ordem classificada para
consistência).