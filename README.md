# Sistema de Gerenciamento de Biblioteca — MIPS Assembly

Trabalho Prático da disciplina de Arquitetura de Computadores  
IFMG – Campus Ouro Branco  
Professor: Ederson Naves Fernandes Gonçalves Júnior

## Sobre o projeto

Sistema de gerenciamento de biblioteca desenvolvido em Assembly MIPS, executado no simulador MARS. O programa permite cadastrar livros, registrar empréstimos e devoluções, e listar a situação atual do acervo.

## Como executar

1. Abra o simulador [MARS](http://courses.missouristate.edu/KenVollmar/MARS/)
2. Vá em **File → Open** e selecione o arquivo `biblioteca.asm`
3. Clique em **Run → Assemble** (ou F3)
4. Clique em **Run → Go** (ou F5)
5. Use a aba **Run I/O** para interagir com o programa

## Funcionalidades

| Opção | Descrição |
|-------|-----------|
| 1 | Cadastrar um novo livro (título digitado pelo usuário, código gerado automaticamente) |
| 2 | Emprestar um livro pelo código |
| 3 | Devolver um livro pelo código |
| 4 | Listar todos os livros e seus status |
| 5 | Encerrar o programa |

## Estrutura dos dados

O programa usa 3 vetores paralelos — a mesma posição em cada vetor representa o mesmo livro:

- `codigos[]` — código de cada livro (igual ao índice, gerado automaticamente)
- `status[]` — situação do livro: `0` = Disponível, `1` = Emprestado
- `titulos[]` — título de cada livro (até 30 caracteres)

Capacidade máxima: **50 livros**.

## Exemplo de uso

```
===== BIBLIOTECA =====
1 - Cadastrar Livro
2 - Emprestar Livro
3 - Devolver Livro
4 - Listar Livros
5 - Sair
Opcao: 1
Digite o titulo do livro: O Hobbit
O Hobbit - Codigo 0
Livro cadastrado com sucesso!

Opcao: 4
Codigo: 0 | Disponivel
```
