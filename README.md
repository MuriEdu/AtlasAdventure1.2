# Atlas Adventure
# Descrição do Projeto

O jogo **Atlas Adventure** narra a jornada de um destemido guerreiro chamado Atlas, que embarca em uma expedição por uma floresta sombria, repleta de labirintos de pedras, para enfrentar os perigosos Uka Ukas. Esses são guerreiros fantasmas que emergem da floresta durante a noite para assombrar o pacífico vilarejo de Winter Rose, o lar de Atlas. A essência desses seres assume uma forma elemental, sendo vulnerável apenas a ataques de um poder correspondente ao seu elemento de origem.

Para aniquilá-los, nosso herói deve coletar amuletos ao longo do caminho, conferindo-lhe os atributos elementares necessários. Entretanto, Atlas só pode carregar consigo até 5 amuletos, cada um concedendo o poder de derrotar um Uka Uka. Os amuletos são armazenados em uma fila de uso, avançando a cada quebra do primeiro amuleto utilizado.

A dinâmica do jogo apresenta uma estratégia única: sempre que Atlas coleta dois amuletos do mesmo elemento, com um deles estando na primeira posição da fila, estes podem se fundir para formar um super amuleto (através de comando do jogador). Este poderoso artefato é capaz de aniquilar qualquer Uka Uka, proporcionando ao protagonista uma vantagem significativa na sua missão.

# Estrutura de Dados

No projeto, optamos por utilizar uma estrutura de dados personalizada para facilitar a mecânica de uso e junção dos amuletos. A estrutura atual consiste em uma combinação de fila e pilha. Um fluxo principal representa os itens coletados na ordem em que foram inseridos, enquanto outros 3 fluxos armazenam apenas os itens da mesma cor. Cada fluxo é iniciado por um header (mainRow, stackRosa, stackVermelho, stackAmarelo), totalizando 4 cabeçalhos.

A estrutura projetada facilita a verificação de elementos repetidos e de mesma natureza (cor) armazenados nela. Cada nó possui 3 ponteiros, caracterizando-se como uma estrutura multiencadeada e composta:

- **NextInRow (NIR):** representa o próximo elemento no fluxo principal.
- **NextInList (NIL):** representa o próximo elemento da pilha da respectiva cor.
- **PrevInList (PIL):** representa o elemento anterior da pilha da respectiva cor.

![Node](/img/node.jpeg)

Além dos nós padrão, utiliza-se nós header para o fluxo principal e para cada lista de cores.

Exemplo da estrutura com 3 elementos inseridos na seguinte ordem: Rosa, Vermelho e Vermelho.

![ED](/img/ed.png)

Além disso, a estrutura possui as seguintes operações primitivas:

- **Insere(GameObject item, string color):** Insere adiciona um novo elemento à estrutura, criando um nó com um GameObject e uma cor associada. Esse nó é inserido na linha principal e empilhado na pilha correspondente à cor.
- **Remove(ref string color):** Remove elimina o primeiro elemento (o item que foi coletado primeiro) da linha principal e o elemento correspondente na pilha associada à sua cor. Atualiza a cor do elemento removido usando o parâmetro de referência color.
- **RemovePar(ref string color, ref GameObject otherToDestroy):** RemovePar remove um par específico de elementos. Dado o primeiro elemento da fila do fluxo principal, caso haja outro elemento da mesma cor, os dois são removidos, o primeiro da fila retornado e o outro passado como parâmetro.
- **Cheia():** Cheia verifica se a estrutura alcançou sua capacidade máxima (5). Retorna verdadeiro se a linha principal estiver cheia, ou seja, se atingiu a capacidade definida; caso contrário, retorna falso.
- **Vazia():** Vazia verifica se a estrutura está sem elementos na linha principal. Retorna verdadeiro se estiver vazia; caso contrário, retorna falso.

# Teaser do Jogo
[Youtube](https://youtu.be/aKxQA-citdY)

# Download

[Link para Download](https://drive.google.com/file/d/1yu9HPs4JE9RoqwTu6nKG2x1qcki6sDZ2/view?usp=drive_link)

## Tutorial para Instalação:
1. Baixar o arquivo compactado .rar.
2. Descompactar no local desejado para instalação.
3. Abra o arquivo com a extensão .exe nomeado como “Projeto teste”.
- Caso o link não esteja funcionando, entre em contato =)

# Equipe
* [Murilo Eduardo Feijo Ramos](https://www.linkedin.com/in/muriedu/)
* Pietro Bernardo Dutra Scaglione
* Ulysses Santos Carneiro
