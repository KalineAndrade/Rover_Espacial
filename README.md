    
# Rover Espacial 
<img 
    align="left" 
    alt="C++" 
    title="C++"
    width="30px" 
    style="padding-right: 10px;" 
    src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/cplusplus/cplusplus-original.svg" 
/> 

---

Protótipo de Rover Espacial, foi desenvolvido em um projeto acadêmico de robótica. O veículo tinha sua estrutura fabricada por impressão 3D e era controlado por um aplicativo de celular via Bluetooth. Entre as funções estão a movimentação por motores   DC, o acionamento de laser, o direcionamento por servomotor e um sensor LDR.

---

TECNOLOGIAS UTILIZADAS

- Arduino Nano
- Arduino IDE / linguagem Arduino baseada em C++
- Módulo Bluetooth HC-05 (registrado nas anotações; alcance anotado de aproximadamente 10 m)
- Comunicação serial por `SoftwareSerial`, nos pinos 8 (RX) e 7 (TX)
- Servomotor, motores DC com ponte H, laser e sensor LDR
- Estrutura fabricada por impressão 3D

---

LASER | Código de validação para ligações do laser

```const byte PINO_LASER = 2;

void setup() {
  pinMode(PINO_LASER, OUTPUT);
}

void loop() {
  digitalWrite(PINO_LASER, HIGH);
  delay(1000);

  digitalWrite(PINO_LASER, LOW);
  delay(1000);
}
```
MOTOR | O microcontrolador vai ler as instruções constantemente

```const byte IN1 = 4;
const byte IN2 = 5;
const byte IN3 = 11;
const byte IN4 = 12;

void pararMotores() {
  digitalWrite(IN1, LOW);
  digitalWrite(IN2, LOW);
  digitalWrite(IN3, LOW);
  digitalWrite(IN4, LOW);
}

void setup() {
  pinMode(IN1, OUTPUT);
  pinMode(IN2, OUTPUT);
  pinMode(IN3, OUTPUT);
  pinMode(IN4, OUTPUT);
  pararMotores();
}

void loop() {
  // Sequência com o movimento para frente.
  digitalWrite(IN1, LOW);
  digitalWrite(IN2, HIGH);
  digitalWrite(IN3, HIGH);
  digitalWrite(IN4, LOW);
  delay(2000);

  pararMotores();
  delay(2000);
}
```





