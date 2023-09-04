## Olá, Mundo!

Agora que você instalou o Rust, é hora de escrever seu primeiro programa Rust. É tradicional, ao aprender uma nova linguagem, escrever um pequeno programa que imprime o texto `Olá, mundo!` na tela, então faremos o mesmo aqui!

> Observação: Este livro pressupõe uma familiaridade básica com a linha de comando. O Rust não faz exigências específicas sobre sua edição, ferramentas ou onde seu código está localizado, portanto, se você preferir usar um ambiente de desenvolvimento integrado (IDE) em vez da linha de comando, fique à vontade para usar o seu IDE favorito. Muitos IDEs agora têm algum grau de suporte ao Rust; verifique a documentação do IDE para obter detalhes. A equipe do Rust tem se concentrado em proporcionar um ótimo suporte ao IDE por meio do `rust-analyzer`. Consulte o [Apêndice D][devtools] para obter mais detalhes.

### Criando um Diretório de Projeto

Você começará criando um diretório para armazenar seu código Rust. Não importa para o Rust onde seu código está localizado, mas, para os exercícios e projetos deste livro, sugerimos criar um diretório *projetos* no seu diretório pessoal (*home*) e manter todos os seus projetos lá.

Abra um terminal e insira os seguintes comandos para criar um diretório *projetos* e um diretório para o projeto "Olá, mundo!" dentro do diretório *projetos*.

Para Linux, macOS e PowerShell no Windows, insira o seguinte:

```console
$ mkdir ~/projetos
$ cd ~/projetos
$ mkdir ola_mundo
$ cd ola_mundo
```

Para o Windows CMD, insira o seguinte:

```cmd
> mkdir "%USERPROFILE%\projetos"
> cd /d "%USERPROFILE%\projetos"
> mkdir ola_mundo
> cd ola_mundo
```

### Escrevendo e Executando um Programa Rust

A seguir, crie um novo arquivo de origem e nomeie-o *main.rs*. Os arquivos Rust sempre terminam com a extensão *.rs*. Se você estiver usando mais de uma palavra em seu nome de arquivo, a convenção é usar um sublinhado para separá-las. Por exemplo, use *ola_mundo.rs* em vez de *olamundo.rs*.

Agora abra o arquivo *main.rs* que você acabou de criar e insira o código no Exemplo 1-1.

<span class="filename">Nome do arquivo: main.rs</span>

```rust
fn main() {
    println!("Olá, mundo!");
}
```

<span class="caption">Exemplo 1-1: Um programa que imprime `Olá, mundo!`</span>

Salve o arquivo e volte para a janela do seu terminal no diretório *~/projetos/ola_mundo*. No Linux ou macOS, insira os seguintes comandos para compilar e executar o arquivo:

```console
$ rustc main.rs
$ ./main
Olá, mundo!
```

No Windows, insira o comando `.\main.exe` em vez de `./main`:

```powershell
> rustc main.rs
> .\main.exe
Olá, mundo!
```

Independentemente do seu sistema operacional, a string `Olá, mundo!` deve ser impressa no terminal. Se você não vir esta saída, consulte a seção de ["Solução de Problemas"][troubleshooting] na parte de Instalação para obter ajuda.

Se `Olá, mundo!` foi impresso, parabéns! Você oficialmente escreveu um programa Rust. Isso faz de você um programador Rust - bem-vindo!

### Anatomia de um Programa Rust

Vamos revisar este programa "Olá, mundo!" em detalhes. Aqui está a primeira parte do quebra-cabeça:

```rust
fn main() {

}
```

Essas linhas definem uma função chamada `main`. A função `main` é especial: ela é sempre o primeiro código que é executado em todos os programas executáveis em Rust. Aqui, a primeira linha declara uma função chamada `main` que não possui parâmetros e não retorna nada. Se houvesse parâmetros, eles seriam colocados entre os parênteses `()`.

O corpo da função é envolto por `{}`. O Rust exige chaves curvas em torno de todos os corpos de função. É um bom estilo colocar a chave de abertura na mesma linha que a declaração da função, adicionando um espaço entre eles.

> Observação: Se você deseja manter um estilo padrão em todos os projetos Rust, pode usar uma ferramenta de formatação automática chamada `rustfmt` para formatar seu código em

 um estilo específico (mais sobre `rustfmt` no [Apêndice D][devtools]). A equipe do Rust incluiu esta ferramenta na distribuição padrão do Rust, assim como o `rustc`, então ela deve estar instalada no seu computador!

O corpo da função `main` contém o seguinte código:

```rust
    println!("Olá, mundo!");
```

Esta linha faz todo o trabalho neste pequeno programa: ela imprime texto na tela. Existem quatro detalhes importantes a serem observados aqui.

Primeiro, o estilo do Rust é usar quatro espaços para recuar, não uma tabulação.

Segundo, `println!` chama um macro Rust. Se ele chamasse uma função, seria escrito como `println` (sem o `!`). Discutiremos macros Rust com mais detalhes no Capítulo 19. Por enquanto, você só precisa saber que o uso de `!` significa que você está chamando um macro em vez de uma função normal e que macros nem sempre seguem as mesmas regras que funções.

Terceiro, você vê a string `"Olá, mundo!"`. Passamos esta string como um argumento para `println!`, e a string é impressa na tela.

Quarto, terminamos a linha com um ponto e vírgula (`;`), o que indica que esta expressão está concluída e a próxima está pronta para começar. A maioria das linhas de código Rust termina com um ponto e vírgula.

### Compilar e Executar São Etapas Separadas

Você acabou de executar um programa recém-criado, então vamos examinar cada etapa do processo.

Antes de executar um programa Rust, você deve compilá-lo usando o compilador Rust, inserindo o comando `rustc` e passando o nome do seu arquivo de origem, assim:

```console
$ rustc main.rs
```

Se você tiver experiência em C ou C++, perceberá que isso é semelhante ao `gcc` ou `clang`. Após a compilação bem-sucedida, o Rust gera um executável binário.

No Linux, macOS e PowerShell no Windows, você pode ver o executável inserindo o comando `ls` no seu shell:

```console
$ ls
main  main.rs
```

No Linux e macOS, você verá dois arquivos. Com o PowerShell no Windows, você verá os mesmos três arquivos que veria usando o CMD. Com o CMD no Windows, você inseriria o seguinte:

```cmd
> dir /B %= a opção /B indica para mostrar apenas os nomes dos arquivos =%
main.exe
main.pdb
main.rs
```

Isso mostra o arquivo de código-fonte com a extensão *.rs*, o arquivo executável (*main.exe* no Windows, mas *main* em todas as outras plataformas) e, ao usar o Windows, um arquivo contendo informações de depuração com a extensão *.pdb*. A partir daqui, você executa o arquivo *main* ou *main.exe*, assim:

```console
$ ./main # ou .\main.exe no Windows
```

Se o seu *main.rs* for o seu programa "Olá, mundo!", esta linha imprimirá `Olá, mundo!` no seu terminal.

Se você estiver mais familiarizado com uma linguagem dinâmica, como Ruby, Python ou JavaScript, talvez não esteja acostumado a compilar e executar um programa como etapas separadas. O Rust é uma linguagem compilada "ahead-of-time", o que significa que você pode compilar um programa e dar o executável para outra pessoa, e ela pode executá-lo mesmo sem ter o Rust instalado. Se você der um arquivo *.rb*, *.py* ou *.js* para alguém, essa pessoa precisará ter uma implementação de Ruby, Python ou JavaScript instalada (respectivamente). Mas, nessas linguagens, você só precisa de um comando para compilar e executar seu programa. Tudo é um compromisso no design da linguagem.

Apenas compilar com `rustc` está bem para programas simples, mas à medida que seu projeto cresce, você desejará gerenciar todas as opções e facilitar o compartilhamento do seu código. Em seguida, apresentaremos a você a ferramenta Cargo, que ajudará você a escrever programas Rust do mundo real.

[troubleshooting]: ch01-01-installation.html#troubleshooting
[devtools]: appendix-04-useful-development-tools.md