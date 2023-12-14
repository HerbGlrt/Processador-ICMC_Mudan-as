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

# Configuração da Placa DE0:

1- Configure o Clock para 1MHz: SW[2] = 1; SW[1]=1; SW[0]=0

2- Selecione o clock AUTOMATICO => sw[8] = 0

3- Agora e' so' programar a placa do Quartus

4- Para clock MANUAL => SW[8]=1  e  mudar a SW[9] para dar o clock no circuito

# Configuração da Placa DE115:

1- Configure o Clock para 1MHz: SW[6] = 1   e TODAS as outras para 0 (Para outros Clocks, tentar subir uma por uma (e apenas uma!) das SW[0]=1Hz, SW[1]=10Hz  ate' SW[6]=1MHz)

2- Selecione o clock AUTOMATICO => sw[16] = 1

3- Agora e' so' programar a placa do Quartus

4- Para clock MANUAL => SW[16]=1  e  mudar a SW[17] para dar o clock no circuito

# Para gerar o PROGRAMA:

1- Escreva o programa NORMALMENTE no Sublime (nome.ASM)

2- F7 para montar o arquivo binario (nome.MIF) e Simular (pra ver se Funciona, ANTES de esperar 20min no Quartus!!)

3- Mude o NOME do arquivo nome.MIF para CPURAM.MIF

4- Copie CPURAM.MIF para a pasta do Projeto no Quartus

5- Compile o projeto no Quartus

6- Programe a Placa e REZE!!!!

7- Troque o  input do Monitor para entrada VGA (tu vai sofrer nos menuzinhos da Philipis!!!)

# Simulador Online

Há uma versão online do simulador para facilitar o desenvolvimento de aplicações compatíveis com o processador. Esta é a versão mais estável dentre as disponíveis no repositório e dispensa qualquer etapa adicional de instalação na máquina local. 

- Pode ser acessado através do link: [https://thiagoambiel.github.io/SimuladorICMC/](https://thiagoambiel.github.io/SimuladorICMC/)

# Novo Simulador local usando go

Além do simulador online e o escrito em C++, foi criado um novo simulador cujo objetivo é dar suporte aos sistemas operacionais mais usados com binários pré compilados, além de ter uma interface mais moderna e de simples uso. O [goICMCsim](https://github.com/lucasgpulcinelli/goICMCsim) tem diversas funcionalidades úteis e é facilmente extensível. Para usá-lo, basta baixar o binário deste link:
- [https://github.com/lucasgpulcinelli/goICMCsim/releases](https://github.com/lucasgpulcinelli/goICMCsim/releases)

Se você gostar do simulador, considere contribuir no repositório!

# Compilador usando o framework do LLVM

No momento, um grande objetivo do projeto é desenvolver um compilador para a arquitetura. Para a sua criação, é importante ter um framework extensível, pois não deve ser necessária a definição da linguagem de alto nível que deverá ser compilada, somente a descrição da arquitetura e como ela funciona. Para isso, é utilizado o framework do LLVM, o qual baseia o compilador clang, rustc, julia, entre outros.

O desenvolvimento do compilador está sendo feito [neste](https://github.com/lucasgpulcinelli/LLVM-ICMC-backend) repositório. Há uma apresentação em português, que tem uma boa documentação de como o compilador funciona num alto nível [aqui](https://docs.google.com/presentation/d/1gBzEu6jkQpzviPLqYvcLvQtvajxIN58WHAHa-J1ruJg/edit?usp=sharing). Note que o compilador não está pronto, e novas contribuições são bem vindas, veja as [issues](https://github.com/lucasgpulcinelli/LLVM-ICMC-backend/issues)!
