Sistema de Gerenciamento de Biblioteca em Assembly MIPS
Trabalho prático desenvolvido para a disciplina de Arquitetura de Computadores pelo Professor Ederson Naves Fernandes Gonçalves Júnior.

O objetivo do projeto é aplicar conceitos de baixo nível, como manipulação de vetores paralelos, cálculo manual de ponteiros de memória (offset) e estruturas de repetição utilizando a linguagem Assembly MIPS.

🛠️ O que o sistema faz
O programa roda em um loop principal simulando um menu interativo no terminal. As opções são:

Cadastrar Livro: Adiciona um novo livro (limite máximo de 50). O ID/Código é gerado automaticamente com base no índice da memória para evitar erros.

Emprestar Livro: Altera o status do livro para "Emprestado" após validar se o código existe e se o livro está realmente disponível.

Devolver Livro: Retorna o status do livro para "Disponível", validando se ele estava previamente emprestado.

Listar Livros: Varre a memória e exibe na tela o ID, o título e a situação atual de cada livro cadastrado.

Sair: Encerra a execução do programa.

💾 Estrutura de Dados e Arquitetura
Como o foco do trabalho foi usar apenas os conceitos iniciais da disciplina, o código foi implementado de forma linear em um único bloco main, controlando o fluxo estritamente por labels e desvios condicionais (beq, bne, blt, j), sem uso de funções/procedimentos complexos ou manipulação de pilha (stack).

Os dados são armazenados na diretiva .data em três vetores paralelos:

codigos: Inteiros (4 bytes por elemento) que guardam o ID automático do livro.

status: Inteiros (4 bytes por elemento) onde 0 significa Disponível e 1 Emprestado.

titulos: Espaço alocado de 30 bytes por registro para armazenar strings com os nomes dos livros.

Particularidade técnica (Cálculo de Offset)
Como o MIPS não possui indexação direta de arrays (vetor[i]), o deslocamento de memória foi feito manualmente. Para evitar o uso de instruções pesadas de multiplicação, implementamos um laço de somas sucessivas:

Para os vetores de inteiros (codigos e status), o programa incrementa de 4 em 4 bytes.

Para o vetor de strings (titulos), o incremento é feito de 30 em 30 bytes.

Devido a uma limitação do simulador MARS, o espaço total do vetor de títulos teve que ser declarado com o valor final já calculado estaticamente (1500 bytes para os 50 livros), já que a diretiva .space não aceita expressões matemáticas do tipo 50 * 30.

🚀 Como Executar
Pré-requisitos
Ter o simulador MARS (MIPS Assembler and Runtime Simulator) instalado na máquina (requer Java).

Passo a Passo
Clone o repositório:

Bash
git clone https://github.com/MateusVon/Trabalho-Arquitetura-e-Organizacao-de-Computadores.git
Abra o simulador MARS.

Vá em File -> Open e selecione o arquivo do código-fonte (geralmente .asm ou .s).

Aperte a tecla F3 (ou vá em Run -> Assemble) para compilar o código.

Aperte F5 (ou Run -> Go) para iniciar a execução.

Interaja com o sistema utilizando o painel de Run I/O na parte inferior do simulador.

👥 Autores
Gabriel Henrique Aladim

Mateus Von Sperling
