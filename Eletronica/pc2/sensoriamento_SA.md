# Sensoriamento do Sistema de Atuadores

O sistema de atuadores será responsável pelo armazenamento e distribuição da água utilizada no sistema de irrigação, de acordo com as rotinas de automação. Na entrada do reservatório, será utilizado um sensor de fluxo para a coleta de dados referente ao gasto hídrico. Também no reservatório, será utilizado um sensor de nível para o monitoramento da quantidade de água, assim evitando que o sistema de bombeamento funcione a vazio.  Falar aqui sobre as subseções.  blábláblá

## Sensor de Fluxo

Um sensor de fluxo de água é um dispositivo que consiste basicamente de um corpo de válvula de plástico, um conjunto de rotor e um sensor de corrente do tipo Hall. É instalado na entrada de água para da detecção do fluxo. Quando a água flui através do conjunto rotor, o mesmo gira, fazendo com que o sensor Hall gere em sua saída uma onda quadrada com frequência que aumenta diretamente proporcional com o fluxo. 

Dentre os sensores disponíveis no mercado, destaca-se o YF-S201B, que de acordo com suas especificações técnicas e preço, se adequa ao projeto Irri.

A seguir, está uma lista com algumas especificações do sensor.

- Leve, pequeno e fácil de montar;
- Tipo de Sensor: Efeito Hall;
- Tensão de Operação: 5,0V a 24,0V;
- Corrente máxima de operação: 15mA (5,0V);
- Faixa de Fluxo: 1 a 30l/min;
- Pressão Máxima: 2,0 MPa;
- Pulsos por litro: 450;
- Frequência: 7,5 $\cdot$ Fluxo(l/min);
- Temperatura de operação: $-25\degree$C a $80\degree$C;
- Pinaegem: Vermelho → alimentação, Amarelo → Saída PWM, Preto → GND

## Sensor de Nível de Água

Um sensor de nível é um dispositivo de instrumentação eletrônica que funciona como uma chave on-off, que pode ser utilizado para o acionamento de bombas, relés, válvulas solenoides, lâmpadas e etc através de um microcontrolador. É construído de material plástico, composto de uma haste, na qual desliza um cilindro feito de material pouco denso. Esse cilindro possui um íma que aciona um sensor magnético no meio da haste, que por sua vez fecha o contato dos fios que saem do sensor.

É importante notar que, como seu funcionamento é baseado em uma chave liga e desliga, é fundamental que sejam utilizados resistores de pull-down na entrada do microcontrolador para que não haja curto circuito na porta de entrada do sinal. 

A seguir, está uma lista com algumas especificações do sensor. 

- Material: Pláscito PP;
- Tensão Máxima de Operação: 100V DC ;
- Corrente Máxima de Operação: 1A;
- Carga Máxima: 50W;
- Temperatura de operação: -20$\degree$C a 80$\degree$C;
- Peso: 12g;
- Dimensões: 50 x 19mm.