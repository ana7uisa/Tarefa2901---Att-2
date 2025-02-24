🔴 Atividade 2 - Temporização de LEDs com Acionamento por Botão 🔵🟢

🎯 Objetivo

Desenvolver um sistema de acionamento de LEDs utilizando a função add_alarm_in_ms() do Pico SDK. O sistema deverá ativar os LEDs em sequência a partir do clique de um botão (pushbutton), com um intervalo de 3 segundos entre as transições.

📌 Componentes Necessários

Microcontrolador: Raspberry Pi Pico W

LEDs: Azul, Vermelho e Verde

Resistores: 330Ω para cada LED

Botão (Pushbutton)

📋 Requisitos

Acionamento dos LEDs:

Ao pressionar o botão, todos os LEDs acendem simultaneamente.

Após 3 segundos, um LED é desligado, restando dois acesos.

Mais 3 segundos depois, mais um LED é desligado, restando apenas um.

Após mais 3 segundos, o último LED apaga, finalizando o ciclo.

Temporização:

O atraso entre cada mudança de estado dos LEDs deve ser de 3 segundos (3.000 ms), utilizando a função add_alarm_in_ms().

Funções de Call-Back:

A lógica de desligamento dos LEDs será implementada em funções de call-back do temporizador, seguindo o exemplo da função turn_off_callback() estudada em aula.

Bloqueio de Reativação:

O botão não pode iniciar um novo ciclo enquanto o último LED não for desligado. Assim, durante a execução das temporizações, o sistema deve ignorar novos cliques no botão.

Testes no BitDogLab:

Utilize a Ferramenta Educacional BitDogLab para validar o funcionamento do código.

O LED RGB deve ser conectado aos GPIOs 11, 12 e 13.

O botão A deve ser conectado ao GPIO 05.

📜 Código-fonte

O código utiliza interrupções GPIO para detectar o pressionamento do botão e timers one-shot para gerenciar a sequência de desligamento dos LEDs.

🔧 Implementação

GPIOs utilizados:

LED Azul: GPIO 11

LED Vermelho: GPIO 12

LED Verde: GPIO 13

Botão: GPIO 5

Bibliotecas empregadas:

pico/stdlib.h para manipulação dos GPIOs

hardware/timer.h para controle de temporização

hardware/gpio.h para configuração do botão

Mecanismo de Temporização:

A função add_alarm_in_ms() agenda o desligamento dos LEDs em sequência.

A interrupção falling-edge no botão detecta o acionamento e inicia o ciclo.

Uma variável de controle impede que o botão seja pressionado novamente até que todos os LEDs tenham sido desligados.

🔍 Testes e Validação

Utilize o BitDogLab para testar a simulação do sistema com os componentes indicados.

Verifique se o botão só responde após o ciclo de desligamento ser concluído.

Confirme o tempo de 3 segundos entre cada transição dos LEDs.
Além disso, segue a atividade 2 no wokwi online:
https://wokwi.com/projects/421971391410063361
