# Docker - Visão Geral

#### **Autora**: *Lorrany Azevedo*

Se você é desenvolvedor provavelmente já ouviu falar sobre Docker... O Docker se popularizou muito no mundo de desenvolvimento pois é uma ferramenta que facilita muito a manipulação e a criação de containers, containers linux já existiam a muito tempo antes do Docker.

Tá mas o que são containers? Antes de explicar sobre os containers propriamente vou explicar alguns conceitos que nos ajudam a entender melhor o que são containers.


## Virtualização e Hypervisor 

A virtualização é o processo de execução de uma instância virtual de um sistema de computador em um hardware, onde essa instância virtual ocupa uma quantidade determinada da capacidade do hardware onde ela está sendo executada. Com isso podemos executar vários sistemas operacionais em um único servidor simultaneamente. Cada uma dessas instâncias virtuais que chamamos de VM (Virtual Machine), executa seus processos de forma que esses processos enxergam apenas o sistema operacional da sua VM sem enxergar outros processos ou sistemas operacionais que estejam na camada abaixo da VM, no caso o host.

Para que isso seja possível temos os hipervisores que são programas de software responsáveis por alocar recursos físicos necessários para as VM's.

"Os hipervisores são tradicionalmente divididos em duas classes: A primeira classe de hipervisores  que costuma ser chamada"bare metal" que executam máquinas virtuais convidadas diretamente no hardware de um sistema, comportando-se essencialmente como um sistema operacional. Os hipervisores do tipo dois ou "hospedados" se comportam mais como aplicativos tradicionais que podem ser iniciados e interrompidos como um programa normal." Tradução livre feita pela autora - [What is virtualization?](https://opensource.com/resources/virtualization)

## Containers

Os containers assim como as vms rodam aplicações de forma isolada do sistema do host em que estão sendo executados, para o mundo exterior eles podem parecer seu próprio sistema completo, entretanto diferentemente das VM's os containers compartilham o kernel do host, ou seja eles não precisam replicar um sistema operacional completo assim como fazem as VM's, isso significa que para o container basta que ele replique apenas os componentes necessários para o funcionamento da aplicação.

Isso faz com que ganhemos aumento de desempenho pois o container está sendo executado pelo host, e reduz também o uso de recursos do host já que as imagens do container são beeeeeemmmm menores do que o espaço que uma VM precisa para existir, ou seja, podemos exucutar muito mais containers do que vms no mesmo host. Assim como as vms os conateiners também possuem uma interface de rede para que eles possam ser expostos ao mundo. 

Abaixo temos uma imagem que mostra essa difereça:

<img width="734" alt="image" src="https://user-images.githubusercontent.com/30262806/189227284-a74b07d0-bc08-46a2-8351-d223d8f55341.png"> (3)

## Docker



-----------------------------------
## Referências

- 1: [O que é virtualização?](https://www.redhat.com/pt-br/topics/virtualization/what-is-virtualization)
- 2: [Livro Descomplicando Docker](https://livro.descomplicandodocker.com.br/chapters/chapter_01.html)
- 3: [O que é um container Linux?](https://www.redhat.com/pt-br/topics/containers/whats-a-linux-container)
