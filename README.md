# m4-pond2
Este projeto se trata sobre a criação de uma miniatura de semáforo usando Arduíno e uma maquete de madeira.


## Especificações
Segue abaixo as especificações para a atividade

| Componente               | Quantidade | Especificação                    |
|--------------------------|------------|----------------------------------|
| LED Verde                | 1          | Indicador de sinal               |
| LED Amarelo              | 1          | Indicador de sinal               |
| LED Vermelho             | 1          | Indicador de sinal               |
| Jumper Macho-Fêmea       | 6          | Conexão entre pinos e protoboard |
| Jumper Macho-Macho       | 3          | Conexão entre protoboard         |
| Resistor 1 kOhm          | 3          | Limitar corrente para LEDs       |
| Protoboard               | 1          | Montagem do circuito             |
| Arduino UNO              | 1          | Microcontrolador principal       |
| Cabo USB A/B             | 1          | Conexão e alimentação do Arduino |



## Montagem 
Nessa secção será tratado sobre a experiência do aluno na montagem do circuito elétrico da atividade

A preparação do circuito foi feita com extrema cautela considerando a fragilidade dos componentes. O primeiro passo seria inserir 3 jumpers (1 pra cada led) macho-macho, com seus terminais respectivamente, 1 na protoboard e outro em um pino digital do Arduíno, dessa forma a protoboard estará carregada e conectada nas portas do microcontrolador. O próximo passo é adicionar 3 resistores de 1 kOhms na mesma linha de conexão que os jumpers anteriormente colocado. Resistores devidamentes colocados, agora é a hora de adicionar outros jumpers, como os resistores possuem 2 terminais, 1 estara´conectado na linha de conexão dos jumpers do arduíno e agora adicione outro jumper macho-fêmea na mesma linha de conexão que o outro terminal do resistor e o conecte no terminal maior do Led. Por último, mas não menos importante, conecte no terminal menor dos Leds na GND dos pinos analógicos do Arduíno.

Foto da montagem:
![Montagem completa do Circuito](../fotoIDE.jpeg)



## Código utilizado 

```c++
// Define as variáveis com as portas do protoboard
int red = 13;
int green = 11;
int yellow = 12;

void setup() {

// Define quais são as portas que iremos atuar sobre o Led
  pinMode(red, OUTPUT);
  pinMode(green, OUTPUT);
  pinMode(yellow, OUTPUT);

}

void loop() {

// Liga o led vermelho e o desliga depois de 6000 milisegundos (6 segundos)
  digitalWrite(green, LOW);
  digitalWrite(yellow, LOW);
  digitalWrite(red, HIGH);
  delay(6000);
  digitalWrite(red, LOW);
  delay(200);

// Liga o led amarelo e o desliga depois de 2000 milisegundos (2 segundos)
  digitalWrite(yellow, HIGH);
  delay(2000);
  digitalWrite(yellow, LOW);
  delay(200);

// Liga o led verde e o desliga depois de 2000 milisegundos e depois 2000 milisegundos (2 segundos)
  digitalWrite(green, HIGH);
  delay(2000);
  delay(2000);
  digitalWrite(green, LOW);
  delay(200);

// Liga o led amarelo e o desliga depois de 2000 milisegundos (2 segundos)
  digitalWrite(yellow, HIGH);
  delay(2000);
  digitalWrite(yellow, LOW);
  delay(200);

}
```

## Vídeos do funcionamento
[Vídeo de Funcionamento](videoIDE.mp4)

