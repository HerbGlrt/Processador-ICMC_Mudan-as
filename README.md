# Disciplina SSC0119 Prática em Organização de Computadores
- Por Favor, para as aulas e informações da Disciplina SSC0119 Prática em Organização de Computadores, usar a página da Disciplina em: https://gitlab.com/simoesusp/disciplinas/-/tree/master/SSC0119-Pratica-em-Organizacao-de-Computadores


# ICMC-Processor
Development of a complete environment to teach and learn computer architecture, VHDL processor design and Assembly language

This project consists of the development of a complete environment to teach and learn computer architecture, VHDL processor design and Assembly language.

The proposed ICMC-Processor was designed to be simple, efficient, and easy to teach and understand. It was proposed as the main project for Computer Organization classes at the ICMC-University of Sao Paulo, in Sao Carlos, Sao Paulo state, Brazil.

This project consists of five parts:

1-	FPGA processor design (Altera VHDL project for Cyclone II DE2-70 board)

2-	Assembler software (to generate binary code for the ICMC-Processor implemented on FPGA)

3-	Simulator software (to simulate the execution of code on the ICMC-Processor)

4-	Compiler software (to compile a reduced set of  C language commands)

5-	Documentation (Processor architecture and Assembly language description)

# Adição da Funcionalidade "Ir para a Declaração"
Se você chegou até aqui, é porque está interessado em contribuir para aprimorar nosso simulador. Recentemente, tive a ideia de adicionar a funcionalidade "Ir para a Declaração" ao simulador, inspirado pela praticidade encontrada em outras IDEs populares como Replit ou VSCode.

# Exemplo da ideia retirada do compilador Replit
![Vídeo sem título ‐ Feito com o Clipchamp](https://github.com/HerbGlrt/Processador-ICMC_Mudan-as/assets/62862399/ef8a2757-ae04-4431-b9c8-dd35777dba20)

# Como Adicionar "Ir para a Declaração"

Para implementar essa função no simulador existente, aqui estão algumas diretrizes gerais:

1. **Análise Estática Simples:**
   - Comece desenvolvendo um analisador estático que possa identificar declarações e suas posições no código assembly. Pode ser útil examinar padrões de nomenclatura, como rótulos e diretivas.

2. **Banco de Dados de Símbolos:**
   - Crie um banco de dados de símbolos que faça o mapeamento dos nomes dos rótulos para suas posições no código, como por exemplo o char ':' que é necessário após o início de uma nova função. Isso pode ser feito usando uma estrutura simples, como um dicionário.

3. **Atalhos de Teclado:**
   - Implemente atalhos de teclado que, quando acionados, usem a posição do cursor para pesquisar no banco de dados de símbolos e navegar até a declaração correspondente. No caso do Replit ou VSCode, a tecla utilizada é o Ctrl.

4. **Realce da Declaração (Opcional):**
   - Considere adicionar um destaque visual à declaração correspondente quando o usuário estiver sobre um nome de símbolo e acionar o atalho de teclado.

# Inspiração Pessoal

Essa ideia surgiu durante meu uso do simulador para recriar o jogo "Fireboy and Watergirl", onde senti a falta dessa funcionalidade e percebi que adicioná-la poderia tornar a experiência de programação mais fluida e eficiente.

# Resultados:
Eu tentei fazer uma implementação em C++ da referida função dentro do arquivo view.cpp, alterando diretamente na montagem do processador. Porém não consegui mexer na parte da GUI para alterar a interface gráfica do usuário e levar a sua tela à referida função, além da identificação da posição do mouse do usuário dentro do ambiente de programação de modo que permita a seleção da função a ser buscada. 
Ainda assim, acredito ser uma funcionalidade que trará muita fluidez e dinamicidade ao ambiente de programação do Sublime Text 3, mais especificamente para simular o processador do ICMC de uma maneira mais "a par" das funções atualmente utilizadas no mundo da programação.
