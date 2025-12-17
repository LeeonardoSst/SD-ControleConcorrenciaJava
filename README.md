## Análise – Uso de Semáforos

Nesta atividade foram analisados dois programas em Java: `Carro.java` e
`CarroLock.java`. Ambos simulam a movimentação de carros concorrendo pelo
acesso a um mesmo recurso, com o objetivo de controlar o número de acessos
simultâneos.

Os dois programas foram compilados e executados, gerando logs para observar
o comportamento das threads.

Carro.java
No programa `Carro.java` é utilizado um semáforo para controlar o acesso ao
recurso compartilhado. O semáforo limita a quantidade de carros que podem
acessar o recurso ao mesmo tempo. Quando o número máximo é atingido, os
outros carros precisam esperar até que um acesso seja liberado.

Durante a execução, foi possível observar que o semáforo impede que muitos
carros entrem ao mesmo tempo, organizando o fluxo e evitando conflitos.

CarroLock.java
No programa `CarroLock.java` o controle de concorrência é feito utilizando
`Lock`. Nesse caso, apenas um carro pode acessar o recurso por vez, e os
demais ficam aguardando até que o acesso seja liberado.

O comportamento observado foi mais restritivo em comparação ao semáforo,
pois o acesso ocorre de forma exclusiva, o que pode gerar mais espera
dependendo da situação.

Comparação
A principal diferença entre os dois programas está na forma de controle do
acesso. O semáforo permite um número limitado de acessos simultâneos, enquanto
o Lock garante acesso exclusivo. O semáforo é mais flexível para situações
em que mais de uma thread pode acessar o recurso ao mesmo tempo.

### Conclusão
Com base nos testes realizados, foi possível perceber que ambos os métodos
evitam problemas de concorrência. O semáforo é mais indicado quando é
necessário permitir múltiplos acessos controlados, enquanto o Lock é mais
adequado quando o recurso deve ser acessado por apenas uma thread por vez.
