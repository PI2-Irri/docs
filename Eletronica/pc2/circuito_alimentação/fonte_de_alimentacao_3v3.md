# Fonte de Alimentação - 3v3 AC/DC

A sessão abaixo descreve os requisitos de alimentação para o sistema de atuadores. 

O microcontrolador escolhido para o controle do sistema de atuador é a ESP32. De acordo com seu datasheet, sua tensão de alimentação é 3,3V e sua corrente é de 500mA na sua máxima operação. Logo, é necessário que seja elaborado um circuito retificador para a conversão da tensão alternada fornecida pela concessionária de energia elétrica para a tensão contínua adequada para o sistema. 

Dado que a tensão entregue pela concessionária de energia elétrica de Brasília (CEB) é de 220V à 60Hz, será necessário um transformador de aproximadamente 35:1, transformando 220VAC para aproximadamente 6,3VAC. Após a tensão ser abaixada, o sinal elétrico passa por uma ponte retificadora, afim de transformar a senóide em pulsos positivos de frequência duas vezes maior que a da entrada.

Passado este processo de retificação da onda, é necessário a filtragem dos pulsos, logo é necessário que o capacitor possua tempo de carga e descarga lento, a fim de que a descarga seja mais lenta que a próxima carga do capacitor. A saída nessa parte do circuito está entre 6,3V e 4,5V.

Para a adequação da tensão na saída, é colocado um diodo zener de 3,9V, para que a tensão seja constante à essa tensão. A saída do diodo é ligada à base de um transistor TBJ pnp com tensão VEB de 0,6V, para que a corrente entregue seja maior. Logo, a saída do circuito terá 3,3V e corrente máxima de 1A.

Aqui vai a imagem do circuito no kicad

Aqui vai a lista dos materiais.

- 1 Transistor TBJ TIP42 PNP
- 1 Resistor 270$\Omega$ 1/2W
- 1 Resistor 1K$\Omega$ 1/2W
- 2 Capacitores 1000uF/25V Eletrolitico
- 1 Capacitor 100uF/25V Eletrolitico
- 1 Capacitor 0.1uF/50V Cerâmico
- 4 diodos 1N4002 - 100V, 1A
- 1 diodo zener 1N4730A 3,9V 1W
- 1 transformador 230VAC - 6.3VAC 1A
