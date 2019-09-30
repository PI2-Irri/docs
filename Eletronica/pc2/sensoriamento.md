### Especificaçao de Sensoriamento

1. **Sensor de Temperatura**

O projeto tem como objetivo automatizar a irrigação de uma gramado com área aproximada de $400m^2$. O sensor então deve ser a prova dágua, afim de seja possível aferir a temperatura da superfície do solo sem que haja preocupação com a integridade física do sensor. Senso assim, o sensor que se adequa ao requisitos do projeto é o sensor DS18B20 da Maxim Integrated. 

O sensor DS18B20 é um termômetro digital oferece medidas de temperatura em Célsius com resolução de 9 a 12 bits e possui uma função de alarme. Cada sensor utiliza apenas uma porta para comunicação com o microcontrolador. Ademais, o sensor pode receber alimentação diretamente do microcontrolador, não necessitando de uma alimentação externa. Todo sensor possui um código serial único de 64 bits, o que permite que vários sensores funcionem utilizando a mesma porta de comunicação. 

A seguir, está uma lista com algumas características do sensor.

- Tensão de Alimentação - 3,0V a 5,0V;
- Corrente de Operação - 1.5mA;
- Comunicação requer apenas uma porta do microcontrolador;
- Faixa de operação: -55ºC até +125ºC;
- $\pm$ 0,5ºC de precisão garantida na faixa de temperatura entre -10ºC e +85ºC;
- Resolução de 9 a 12 bits programável;
- Funciona com alimentação parasita (Alimentação pelo fio de comunicação);
- Altamente escalável;
- Função alarme ajustável pelo usuário.

2. **Sensor de Umidade**

O projeto possui também como objetivo o monitoramento da irrigação do gramado. Logo, é necessário um sensor de umidade que possua alta durabilidade. Estão disponíveis no mercado sensores resistivos, capacitivos e tensiômetros. Para o propósito deste projeto, foi decidido, de acordo com os requisitos, que o sensor escolhido é o sensor capacitivo. O sensor capacitivo que melhor se adequa é o $SEN0193$. 

O sensor de umidade capacitivo mede a quantidade de umidade no solo por sensibilidade capacitiva. Isso o torna menos sucetível a corrosão o que garante a alta durabilidade do sensor. Ele possui um regulador de tensão incluso, fazendo possuir uma tensão de operação entre 3,3V e 5,0V, o que proporciona boa compartibilidade com microcontroladores que operam na mesma faixa de tensão. Sua comunicação com microcontrolador é do tipo analógica, fazendo com o que o microcontrolador possua um conversor analógico digital para que seja realizada a leitura dos dados provenientes do sensor.

A seguir, está uma lista com algumas caracteríscitas do sensor.

- Tensão de Alimentação - 3,3V a 5,0V.
- Corrente de Operação - 5mA
- Tensão de Saída - 0 a 3.0V.
- Dimensões: 9,80 x 2,3 cm
- Peso: 15g