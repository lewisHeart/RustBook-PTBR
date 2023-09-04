# Introdução

> Nota: Esta edição do livro é a mesma que [A Linguagem de Programação Rust][nsprust] disponível em formato impresso e ebook em inglês pela [No Starch Press][nsp].

[nsprust]: https://nostarch.com/rust-programming-language-2nd-edition
[nsp]: https://nostarch.com/

Bem-vindo ao *Livro da Linguagem de Programação Rust*, um livro introdutório sobre Rust. A linguagem de programação Rust ajuda você a escrever software mais rápido e confiável. Ergonomia de alto nível e controle de baixo nível muitas vezes entram em conflito no design de linguagens de programação; Rust desafia esse conflito. Ao equilibrar capacidade técnica poderosa e uma ótima experiência de desenvolvedor, Rust oferece a você a opção de controlar detalhes de baixo nível (como uso de memória) sem toda a dificuldade tradicionalmente associada a esse controle.

## Para Quem é o Rust

O Rust é ideal para muitas pessoas por uma variedade de razões. Vamos analisar algumas das principais categorias.

### Equipes de Desenvolvedores

O Rust está se mostrando uma ferramenta produtiva para colaboração entre grandes equipes de desenvolvedores com diferentes níveis de conhecimento em programação de sistemas. O código de baixo nível é propenso a vários bugs sutis, que na maioria das outras linguagens só podem ser identificados por meio de extensos testes e revisão cuidadosa do código por desenvolvedores experientes. No Rust, o compilador desempenha o papel de guardião, recusando-se a compilar código com esses bugs difíceis de detectar, incluindo bugs de concorrência. Ao trabalhar junto com o compilador, a equipe pode gastar seu tempo concentrando-se na lógica do programa em vez de rastrear bugs.

O Rust também traz ferramentas de desenvolvedor contemporâneas para o mundo da programação de sistemas:

- O Cargo, o gerenciador de dependências e ferramenta de construção incluída, facilita a adição, compilação e gerenciamento de dependências de forma indolor e consistente em todo o ecossistema Rust.
- A ferramenta de formatação Rustfmt garante um estilo de codificação consistente entre os desenvolvedores.
- O Servidor de Linguagem Rust alimenta a integração com Ambientes de Desenvolvimento Integrado (IDE) para conclusão de código e mensagens de erro em linha.

Ao usar essas e outras ferramentas no ecossistema Rust, os desenvolvedores podem ser produtivos ao escrever código de nível de sistemas.

### Estudantes

O Rust é para estudantes e aqueles que estão interessados em aprender sobre conceitos de sistemas. Usando Rust, muitas pessoas aprenderam sobre tópicos como desenvolvimento de sistemas operacionais. A comunidade é muito acolhedora e feliz em responder às perguntas dos estudantes. Através de esforços como este livro, as equipes do Rust desejam tornar os conceitos de sistemas mais acessíveis a mais pessoas, especialmente àqueles que são novos na programação.

### Empresas

Centenas de empresas, grandes e pequenas, usam Rust em produção para uma variedade de tarefas, incluindo ferramentas de linha de comando, serviços web, ferramentas de DevOps, dispositivos embarcados, análise e transcodificação de áudio e vídeo, criptomoedas, bioinformática, mecanismos de busca, aplicativos de Internet das Coisas, aprendizado de máquina e até partes importantes do navegador web Firefox.

### Desenvolvedores de Código Aberto

O Rust é para pessoas que desejam construir a linguagem de programação Rust, a comunidade, ferramentas de desenvolvedor e bibliotecas. Adoraríamos ter sua contribuição para a linguagem Rust.

### Pessoas que Valorizam Velocidade e Estabilidade

O Rust é para pessoas que desejam velocidade e estabilidade em uma linguagem. Por velocidade, queremos dizer tanto o quão rapidamente o código Rust pode ser executado quanto a velocidade com que o Rust permite que você escreva programas. As verificações do compilador Rust garantem estabilidade por meio de adições de recursos e refatoração. Isso contrasta com o código legado frágil em linguagens que não possuem essas verificações, que os desenvolvedores frequentemente têm medo de modificar. Ao buscar abstrações de custo zero, recursos de alto nível que compilam para código de baixo nível tão rápido quanto o código escrito manualmente, o Rust busca fazer com que o código seguro seja também rápido.

A linguagem Rust espera atender muitos outros usuários; aqueles mencionados aqui são apenas alguns dos maiores interessados. No geral, a maior ambição do Rust é eliminar as compensações que os programadores aceitaram por décadas, fornecendo segurança *e* produtividade, velocidade *e* ergonomia. Experimente o Rust e veja se suas escolhas funcionam para você.

## Para Quem é Este Livro

Este livro parte do pressuposto de que você escreveu código em outra linguagem de programação, mas não faz suposições sobre qual. Tentamos tornar o material amplamente acessível para pessoas de uma ampla variedade de origens de programação. Não dedicamos muito tempo a falar sobre o que é a programação ou como pensar sobre ela. Se você é completamente novo na programação, seria melhor ler um livro que forneça especificamente uma introdução à programação.

## Como Usar Este Livro

Em geral, este livro parte do pressuposto de que você está lendo em sequência, da frente para trás. Capítulos posteriores constroem conceitos apresentados em capítulos anteriores, e capítulos anteriores podem não entrar em detalhes sobre um tópico específico, mas retomarão o assunto em um capítulo posterior.

Você encontrará dois tipos de capítulos neste livro: capítulos de conceito e capítulos de projeto. Nos capítulos de conceito, você aprenderá sobre um aspecto do Rust. Nos capítulos de projeto, construiremos pequenos programas juntos, aplicando o que você aprendeu até agora. Os Capítulos 2, 12 e 20 são capítulos de projeto; os demais são capítulos de conceito.

O Capítulo 1 explica como instalar o Rust, como escrever um programa "Olá, mundo!" e como usar o Cargo, o gerenciador de pacotes e ferramenta de construção do Rust. O Capítulo 2 é uma introdução prática à escrita de programas em Rust, permitindo que você desenvolva um jogo de adivinhação de números. Aqui, abordamos conceitos em alto nível, e capítulos posteriores fornecerão detalhes adicionais. Se você quiser colocar a mão na massa imediatamente, o Capítulo 2 é o lugar para isso. O Capítulo 3 aborda recursos do Rust que são semelhantes aos de outras linguagens de programação, e no Capítulo 4 você aprenderá sobre o sistema de propriedade do Rust. Se você é um aprendiz especialmente meticuloso que prefere aprender todos os detalhes antes de avançar para o próximo, pode pular o Capítulo 2 e ir direto para o Capítulo 3, retornando ao Capítulo 2 quando quiser trabalhar em um projeto aplicando os detalhes que você aprendeu.

O Capítulo 5 discute structs e métodos, e o Capítulo 6 aborda enums, expressões `match` e a construção de fluxo de controle `if let`. Você usará structs e enums para criar tipos personalizados em Rust.

No Capítulo 7, você aprenderá sobre o sistema de módulos do Rust e sobre as regras de privacidade para organizar seu código e sua Interface de Programação de Aplicativos (API) pública. O Capítulo 8 discute algumas estruturas de dados de coleção comuns que a biblioteca padrão fornece, como vetores, strings e mapas hash. O Capítulo 9 explora a filosofia e técnicas de tratamento de erros do Rust.

O Capítulo 10 explora conceitos de genéricos, traits e lifetimes, que permitem que você defina código que se aplica a vários tipos. O Capítulo 11 é totalmente dedicado a testes, que, mesmo com as garantias de segurança do Rust, são necessários para garantir a correção da lógica de seu programa. No Capítulo 12, construiremos nossa própria implementação de um subconjunto da funcionalidade da ferramenta de linha de comando `grep`, que procura texto dentro de arquivos. Para isso, usaremos muitos dos conceitos discutidos nos capítulos anteriores.

O Capítulo 13 explora closures e iteradores: recursos do Rust que vêm de linguagens de programação funcional. No Capítulo 14, examinaremos o Cargo com mais detalhes e discutiremos as melhores práticas para compartilhar suas bibliotecas com outras pessoas. O Capítulo 15 discute ponteiros inteligentes fornecidos pela biblioteca padrão e os traits que habilitam sua funcionalidade.

No Capítulo 16, exploraremos diferentes modelos de programação concorrente e discutiremos como o Rust ajuda você a programar em várias threads com confiança. O Capítulo 17 examina como os idiomas do Rust se comparam aos princípios da programação orientada a objetos com os quais você pode estar familiarizado.

O Capítulo 18 é uma referência a padrões e correspondência de padrões, que são maneiras poderosas de expressar ideias em programas Rust. O Capítulo 19 contém uma variedade de tópicos avançados de interesse, incluindo Rust inseguro, macros e mais sobre lifetimes, traits, tipos, funções e closures.

No Capítulo 20, completaremos um projeto no qual implementaremos um servidor web multithread de baixo nível!

Finalmente, alguns apêndices contêm informações úteis sobre a linguagem em um formato mais parecido com um guia de referência. O Apêndice A cobre as palavras-chave do Rust, o Apêndice B abrange operadores e símbolos do Rust, o Apêndice C aborda traits deriváveis fornecidos pela biblioteca padrão, o Apêndice D cobre algumas ferramentas de desenvolvimento úteis, e o Apêndice E explica as edições do Rust. No Apêndice F, você encontrará traduções do livro, e no Apêndice G, abordaremos como o Rust é criado e o que é o Rust nightly.

Não há uma maneira errada de ler este livro: se você quiser pular adiante, vá em frente! Você pode ter que voltar para capítulos anteriores se sentir alguma confusão. Mas faça o que funcionar para você.

<span id="ferris"></span>

Uma parte importante do processo de aprendizado do Rust é aprender a ler as mensagens de erro que o compilador exibe: elas o guiarão em direção a um código funcional. Portanto, forneceremos muitos exemplos que não compilam, junto com a mensagem de erro que o compilador mostrará em cada situação. Saiba que se você inserir e executar um exemplo aleatório, ele pode não compilar! Certifique-se de ler o texto circundante para ver se o exemplo que você está tentando executar está destinado a gerar erro. Ferris também o ajudará a distinguir o código que não está destinado a funcionar:

| Ferris                                                                                                           | Significado                                   |
|------------------------------------------------------------------------------------------------------------------|-----------------------------------------------|
| <img src="img/ferris/does_not_compile.svg" class="ferris-explain" alt="Ferris com um ponto de interrogação"/> | Este código não compila!                     |
| <img src="img/ferris/panics.svg" class="ferris-explain" alt="Ferris com as mãos para cima"/>                   | Este código causa uma falha!                 |
| <img src="img/ferris/not_desired_behavior.svg" class="ferris-explain" alt="Ferris com uma garra levantada, encolhendo os ombros"/> | Este código não produz o comportamento desejado. |

Na maioria das situações, o direcionaremos para a versão correta de qualquer código que não compile.

## Código Fonte

Os arquivos-fonte dos quais este livro é gerado podem ser encontrados no [GitHub][book].

[book]: https://github.com/rust-lang/book/tree/main/src