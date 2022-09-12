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

### Docker Engine 

O docker é uma ferramenta que serve para a gerenciar, buildar, executar e até orquestrar containers (**Docker Swarm**), além disso ele pode ser executado tanto em computadores como laptops e desktops como em vms, servidores em nuvem etc, o que o torna uma ferramenta com uma portabilidade muito boa já que você pode executar a mesma imagem de um container em diversos ambientes diferenetes. 

O Docker engine é uma aplicação cliente-servidor, onde o cliente se comunica com o **Docker Daemon (dockerd)** que escutas as requisições da api do docker e faz o gerenciamento dos objetos Docker (imagens, containers, volumes etc). Os componentes da engine do docker são:
	
- Um servidor chamado **Docker Daemon (dockerd)** 
- Uma API REST que especifica as interfaces que os programas podem usar para conversar com o daemon e instruí-lo sobre o que fazer.
- Um cliente de interface de linha de comando (CLI) (docker command).

<img width="529" alt="image" src="https://user-images.githubusercontent.com/30262806/189550518-440bbd1d-1621-4149-b8d2-19b2c246ae74.png">


O servidor e o cliente podem ser executados (ou não) na mesma máquina, eles se comunicam usando uma API REST, com UNIX sockets ou uma interface de rede.

### Dockerfile (Imagens)

Como já dissemos podemos buildar containers com o docker e para isso utilizamos o Dockerfile, o Dockerfile é o arquivo onde iremos colocar tudo o que o nosso container irá precisar para trabalhar como por exemplo a imagem do sistema operacional no qual o seu container será baseado, a instalação de programas, bibliotecas e etc. O Dockerfile é um arquivo read-only e será o responsável pela criação do seu container, que nada mais é do que uma instância executavel da sua imagem.

### Volumes

Os volumes no docker são os responsáveis por persistirem os dados referentes a um container, eles são inicializados quando criamos o conatiner. Os volumes são diretórios comuns que são criados no host quando criamos o nosso container, ou seja, parar ou até mesmo deletar o seu conatiner não irá destruir esses volumes. Além de persistir os dados do container podemos usar os volumes para compartilhar esses dados.

### Docker Registry

Os resgitries do Docker nada mais são que lugares que utilizamos para armazenar nossas imagens. O DockerHub é um registry público e o Docker tem por configuração default buscar suas imagens nele, utilizando comandos como ```docker pull``` ou ```docker push``` você pode pegar ou subir imagens pro registry, inclusive esses comandos não te lembram algo??? sim os comandos do git ;)

## Bora praticar!!

**Dica: Sempre que tiverem duvidas recomendo a leitura da documentação as leituras aqui indicadas são boas para quem está começando mas na sua vida de dev você precisa aprender a ler e a buscar informações na documentação**

**Dica 2: Coloquei opções de tutoriais em português caso você tenha muita dificuldade com o inglês entretanto recomendo tentar os tutoriais em inglês.**

Agora que vimos um pouco de alguns dos principais conceitos do Docker é importante praticarmos para entender melhor como os conceitos funcionam na pratica e obviamente aprendermos a utilizar o docker, em caso de ter ficado alguma duvida (ou não), recomendo a leitura dos materiais citados na descrição pois eles tem uma maior profundidade no assunto (principalmente a própria documentação do Docker)! ;)

**Instalação**: neste link ([Get Docker](https://docs.docker.com/get-docker/)) tem intruções para instalação para mac, linux e windows. 
</br>**Tutoriais em inglês**: 
- [Docker Tutorial — Getting Started with Python, Redis, and Nginx.](https://medium.com/hackernoon/docker-tutorial-getting-started-with-python-redis-and-nginx-81a9d740d091)
- [Docker Tutorial DevOpsGuide](https://github.com/Tikam02/DevOps-Guide/tree/master/Container-orchestration/Docker)

</br>**Tutoriais em Português**: 
- [Tutorial Definitivo de Docker para INICIANTES (Ubuntu)](https://terminalroot.com.br/2019/08/tutorial-definitivo-de-docker-para-iniciantes-ubuntu.html)
- [Um guia para iniciantes em Docker — como criar sua primeira aplicação com o Docker](https://www.freecodecamp.org/portuguese/news/um-guia-para-iniciantes-em-docker-como-criar-sua-primeira-aplicacao-com-o-docker/)
-----------------------------------
## Referências (Recomendo a leitura destas)

- 1: [O que é virtualização?](https://www.redhat.com/pt-br/topics/virtualization/what-is-virtualization)
- 2: [Livro Descomplicando Docker](https://livro.descomplicandodocker.com.br/chapters/chapter_01.html)
- 3: [O que é um container Linux?](https://www.redhat.com/pt-br/topics/containers/whats-a-linux-container)
- 4: [Docker Overview](https://docs.docker.com/get-started/overview/)
