# 📑 Sumário

- [📘 O que é um Sistema Operacional?](#-o-que-é-um-sistema-operacional)
- [⚙ Principais Funções de um Sistema Operacional](#-principais-funções-de-um-sistema-operacional)
    - [🧠 Gerenciamento de Processos](#-gerenciamento-de-processos)
    - [💾 Gerenciamento de Memória](#-gerenciamento-de-memória)
    - [🖥 Gerenciamento de Entrada/Saída (I/O)](#-gerenciamento-de-entradasaída-io)
    - [📁 Gerenciamento de Arquivos](#-gerenciamento-de-arquivos)
    - [🔐 Segurança e Proteção](#-segurança-e-proteção)
    - [🌐 Gerenciamento de Redes](#-gerenciamento-de-redes)
- [🧱 Estrutura Geral de um Sistema Operacional](#-estrutura-geral-de-um-sistema-operacional)
    - [🔌 Camadas Principais](#-camadas-principais)
- [🛠 Chamada de Sistema (System Calls)](#-chamada-de-sistema-system-calls)
- [🔐 Importância para a Cibersegurança](#-importância-para-a-cibersegurança)
- [🧩 Tipos de Sistemas Operacionais](#-tipos-de-sistemas-operacionais)
    - [🧱 Sistemas Monolíticos](#-sistemas-monolíticos)
    - [🔬 Sistemas Microkernel](#-sistemas-microkernel)
    - [⚖ Sistemas Híbridos](#-sistemas-híbridos)
    - [⏱ Sistemas de Tempo Real (RTOS)](#-sistemas-de-tempo-real-rtos)
    - [🌐 Sistemas Distribuídos](#-sistemas-distribuídos)
    - [☁ Sistemas Virtualizados e em Nuvem](#-sistemas-virtualizados-e-em-nuvem)
- [🚀 Processos no Sistema Operacional](#-processos-no-sistema-operacional)
    - [❓ O que é um Processo?](#-o-que-é-um-processo)
        - [Componentes de um Processo](#componentes-de-um-processo)
    - [🚦 Estados de um Processo](#estados-de-um-processo)
    - [🛡️ Importância na Cibersegurança](#importância-na-cibersegurança-1)
    - [📊 Tipos de Processos](#tipos-de-processos)
        - [Quanto à Origem](#quanto-à-origem)
        - [Quanto à Execução](#quanto-à-execução)
    - [🛡️ Utilização na Cibersegurança](#utilização-na-cibersegurança-1)
    - [⚙️ Como os Processos Funcionam?](#como-os-processos-funcionam)
        - [Algoritmos de Escalonamento Mais Comuns](#algoritmos-de-escalonamento-mais-comuns)
    - [🛡️ Porque Importa para a Cibersegurança?](#porque-importa-para-a-cibersegurança)
- [🧠 Memória no Sistema Operacional](#-memória-no-sistema-operacional-1)
    - [❓ O que é Memória?](#-o-que-é-memória-1)
        - [Componentes Principais](#componentes-principais-1)

---

# 📘 O que é um Sistema Operacional?

Um **Sistema Operacional (SO)** é um software fundamental que coordena e gerencia o uso do hardware por parte dos programas e dos usuários. Ele atua como uma **ponte entre o usuário e o hardware**, garantindo que os recursos sejam utilizados de forma **eficiente, organizada e segura**.

---

## ⚙ Principais Funções de um Sistema Operacional

### 🧠 Gerenciamento de Processos

- **Processo**: É um programa em execução.
- O SO é responsável por:
    - Criar, pausar, retomar e finalizar processos.
    - Realizar o **escalonamento da CPU**, ou seja, decidir qual processo utilizará a CPU e por quanto tempo.
    - Garantir que múltiplos processos compartilhem os recursos de forma **justa e eficiente** (multitarefa).

---

### 💾 Gerenciamento de Memória

- Garante que cada processo tenha a **quantidade de memória necessária**.
- Técnicas utilizadas:
    - **Paginação**: Divide a memória em blocos (páginas) para facilitar a alocação.
    - **Segmentação**: Divide a memória com base na lógica dos dados (ex: código, dados, pilha).
- Protege a memória contra **acesso indevido** por outros processos.

---

### 🖥 Gerenciamento de Entrada/Saída (I/O)

- Controla o acesso e a comunicação com dispositivos periféricos.
- Técnicas comuns:
    - **Buffering**: Utiliza memória temporária para evitar a espera por dispositivos mais lentos.
    - **Caching**: Armazena dados acessados frequentemente em uma área mais rápida para acesso futuro.
    - **Spooling**: Organiza tarefas em uma fila para dispositivos compartilhados (como impressoras), permitindo que os programas continuem a executar sem esperar pela conclusão da operação de I/O.

---

### 📁 Gerenciamento de Arquivos

- Cria e organiza **arquivos e diretórios** (pastas).
- Controla as operações de **leitura, escrita, remoção e as permissões** de acesso aos arquivos e diretórios.
- Mantém a **integridade e segurança** dos dados armazenados no sistema de arquivos.

---

### 🔐 Segurança e Proteção

- **Autenticação**: Confirma a identidade do usuário, geralmente através de nome de usuário e senha ou outros métodos.
- **Criptografia**: Protege os dados armazenados e em trânsito, tornando-os ilegíveis para usuários não autorizados.
- **Controle de acesso**: Define quem pode acessar quais recursos do sistema (arquivos, diretórios, dispositivos, etc.) e quais operações podem realizar.
- Previne que **programas maliciosos** afetem o sistema operacional e outros usuários, isolando processos e controlando o acesso a recursos críticos.

---

### 🌐 Gerenciamento de Redes

- Permite que o sistema se comunique com outros dispositivos através de **protocolos de rede** (como TCP/IP).
- Gerencia conexões de rede e a **transferência de dados entre sistemas distribuídos**.
- Essencial para o funcionamento da **internet, servidores e computação em nuvem**.

---

## 🧱 Estrutura Geral de um Sistema Operacional

### 🔌 Camadas Principais

- **Nível de Hardware**
    - Inclui todos os dispositivos físicos do computador (CPU, memória, dispositivos de E/S, etc.).
    - O SO interage com este nível através dos **drivers de dispositivo**, que são softwares específicos para cada tipo de hardware.

- **Kernel**
    - O **núcleo do sistema operacional**.
    - É responsável por gerenciar todos os recursos do sistema e fornecer os serviços essenciais para os outros componentes do software.
    - Pode ser:
        - **Monolítico**: Toda a funcionalidade do kernel (gerenciamento de processos, memória, arquivos, etc.) é implementada em um único bloco de código executado em modo privilegiado.
        - **Microkernel**: Apenas as funções mais básicas (comunicação entre processos, gerenciamento básico de memória) são implementadas no núcleo, enquanto outros serviços rodam como processos no espaço do usuário.

- **Bibliotecas do Sistema**
    - Oferecem um conjunto de funções reutilizáveis que permitem que os programas de usuário acessem os serviços do kernel de forma mais fácil e padronizada.

- **Shell (Interface do Usuário)**
    - Permite a interação do usuário com o sistema operacional.
    - **CLI (Linha de Comando)**: Interface baseada em texto onde os comandos são digitados (ex: Bash no Linux, PowerShell no Windows).
    - **GUI (Interface Gráfica)**: Interface visual com ícones, janelas e menus (ex: Windows Explorer no Windows, GNOME no Linux).

- **Aplicações de Usuário**
    - Programas desenvolvidos por usuários ou terceiros que são executados sobre o sistema operacional (ex: editores de texto, navegadores web, jogos).

---

## 🛠 Chamada de Sistema (System Calls)

- São mecanismos que permitem que os programas em modo de usuário (aplicações) solicitem **serviços ao kernel** do sistema operacional.
- Funcionam como **portas de entrada protegidas** para o núcleo do SO, permitindo que os programas acessem recursos de hardware e funcionalidades do sistema de forma controlada.
- Exemplos comuns:

```c
fork();    // Cria um novo processo
exec();    // Executa um novo programa
read();    // Lê dados de um arquivo ou dispositivo
write();   // Escreve dados em um arquivo ou dispositivo
```

## 🔐 Importância para a Cibersegurança

- Vulnerabilidades no Sistema Operacional, especialmente no **kernel** ou nas **system calls**, são alvos comuns de ataques, pois explorá-las pode conceder controle total sobre o sistema.
- Compreender a estrutura do SO permite:
    - Identificar e mitigar **falhas de segurança** em seus componentes.
    - Implementar **mecanismos de defesa** mais eficazes, como firewalls e sistemas de detecção de intrusão, que se baseiam no comportamento do SO.
- Exemplos de ataques comuns explorando o SO:
    - **Escalonamento de privilégios**: Uma vulnerabilidade que permite a um usuário com permissões limitadas obter acesso de administrador (root).
    - **Buffer overflow**: Uma falha de programação que pode ser explorada para sobrescrever áreas de memória e executar código malicioso.
    - **Manipulação indevida de arquivos e permissões**: Acesso não autorizado, modificação ou exclusão de dados sensíveis devido a falhas no gerenciamento de arquivos e permissões.

-----

# 🚀 Processos no Sistema Operacional

## ❓ O que é um Processo?

Um processo é uma **instância em execução de um programa**. Ele representa a unidade básica de trabalho que o sistema operacional pode agendar para execução na CPU. Um processo não é apenas o código do programa, mas também inclui o contexto necessário para sua execução.

#### Componentes de um Processo

Um processo compreende diversos componentes essenciais:

  - **Código do programa (Texto/Binário)**: As instruções que definem o que o programa deve fazer.
  - **Dados e variáveis**: As informações que o programa utiliza e manipula durante sua execução.
  - **Pilha (Stack)**: Uma estrutura de dados utilizada para gerenciar as chamadas de funções e as variáveis locais de cada função.
  - **Heap**: Uma área de memória utilizada para alocação dinâmica durante a execução do programa (por exemplo, quando o programa precisa criar objetos ou estruturas de dados em tempo de execução).
  - **Contador de programa (Program Counter)**: Um registrador que armazena o endereço da próxima instrução a ser executada.
  - **Registradores**: Pequenas áreas de armazenamento de alta velocidade dentro da CPU, utilizadas para armazenar operandos e resultados temporários.
  - **Informações de estado**: Dados que descrevem o estado atual do processo (por exemplo, se está pronto para executar, esperando por um evento, etc.).
  - **Recursos do sistema**: Uma lista dos recursos que o processo está utilizando (por exemplo, arquivos abertos, conexões de rede).

## 🚦 Estados de um Processo

Durante seu ciclo de vida, um processo pode passar por diferentes estados:

  - **New (Novo)**: O processo está sendo criado.
  - **Ready (Pronto)**: O processo está na memória principal e pronto para ser executado pela CPU, aguardando apenas sua vez no escalonamento.
  - **Running (Executando)**: As instruções do processo estão sendo executadas pela CPU.
  - **Waiting/Blocked (Esperando/Bloqueado)**: O processo está parado, aguardando a ocorrência de um evento específico (por exemplo, a conclusão de uma operação de E/S, o recebimento de um sinal).
  - **Terminated/Exit (Finalizado/Saído)**: O processo completou sua execução ou foi terminado pelo sistema operacional.

## 🛡️ Importância na Cibersegurança

  - **Malwares** frequentemente criam processos ocultos ou disfarçados para executar código malicioso sem chamar a atenção do usuário.
  - Técnicas como **Process Injection** permitem que um processo malicioso insira seu código dentro de outro processo legítimo, tornando a detecção mais difícil, pois o comportamento malicioso parece estar vindo de um programa confiável.

## 📊 Tipos de Processos

Os processos podem ser classificados de acordo com sua origem e como interagem com o usuário:

### Quanto à Origem

  - **Processos do sistema**: São criados e gerenciados diretamente pelo sistema operacional para realizar tarefas essenciais (ex: `init` ou `systemd` em sistemas Linux, gerenciador de memória, processos de E/S).
  - **Processos de usuário**: São iniciados por programas ou ações do usuário (ex: um navegador web, um editor de texto).

### Quanto à Execução

  - **Foreground (Interativos)**: São processos que geralmente requerem a interação direta do usuário (ex: um aplicativo com interface gráfica).
  - **Background (Serviços/Daemons)**: São processos que rodam em segundo plano, sem interação direta do usuário, fornecendo serviços ao sistema ou a outros programas (ex: o serviço `cron` para agendamento de tarefas no Linux).

### Utilização na Cibersegurança

  - **Rootkits** podem se disfarçar como processos do sistema para ocultar atividades maliciosas.
  - **Malwares** que operam em background podem executar tarefas maliciosas (como espionagem ou roubo de informações) sem que o usuário perceba.

## ⚙️ Como os Processos Funcionam?

O **escalonador de processos** é o componente do sistema operacional responsável por decidir qual processo terá permissão para usar a CPU em um determinado momento. O objetivo do escalonador é otimizar o uso da CPU, maximizar o throughput (a quantidade de trabalho concluído), minimizar o tempo de espera e garantir um tratamento justo para todos os processos.

### Algoritmos de Escalonamento Mais Comuns

  - **FIFO (First In, First Out)**: O primeiro processo a entrar na fila de prontos é o primeiro a ser executado. É simples, mas pode levar a um "efeito comboio" onde processos longos bloqueiam processos curtos.
  - **Round Robin**: Cada processo recebe uma fatia de tempo fixa (quantum) para executar. Se o processo não terminar dentro desse tempo, ele é movido para o final da fila de prontos, e o próximo processo recebe sua fatia de tempo. Isso garante que nenhum processo monopolize a CPU por muito tempo.
  - **Por prioridade**: Cada processo recebe uma prioridade, e o processo com a maior prioridade é executado primeiro. Processos com a mesma prioridade são geralmente escalonados usando FIFO ou Round Robin. A prioridade pode ser estática (atribuída na criação do processo) ou dinâmica (ajustada pelo sistema operacional com base no comportamento do processo).

### Porque Importa para a Cibersegurança?

  - Ataques de **Negação de Serviço (DoS)** podem explorar o gerenciamento de processos, criando um grande número de processos inúteis para sobrecarregar o sistema e impedir que processos legítimos sejam executados.
  - A técnica de **Process Hollowing** permite que um malware insira código malicioso em um processo legítimo que já está em execução, substituindo o código original do processo pelo código malicioso. Isso pode ajudar o malware a evitar a detecção, pois ele parece estar rodando dentro de um processo confiável.

-----

## 🧠 Memória no Sistema Operacional

### ❓ O que é Memória?

A **memória principal (RAM)** é onde os dados e os programas ficam armazenados temporariamente enquanto estão sendo usados pelo sistema operacional e pela CPU. Ela é essencial para a execução eficiente dos programas, pois permite que a CPU acesse rapidamente as informações de que precisa.

#### Componentes Principais

  - **Registradores**: Pequenas unidades de memória de alta velocidade localizadas diretamente dentro do processador (CPU). Eles são usados para armazenar dados e instruções que estão sendo processados naquele exato momento, permitindo o acesso mais rápido possível.
  - **Cache**: Uma camada de memória estática (SRAM) de alta velocidade localizada entre a CPU e a memória RAM. Ela armazena cópias de dados e instruções que foram acessados recentemente ou que são frequentemente usados, para reduzir o tempo de acesso da CPU à memória. Existem múltiplos níveis de cache (L1, L2, L3) com diferentes tamanhos e velocidades.
  - **Memória RAM (Random Access Memory)**: A memória principal do computador, onde os programas em execução e os dados que eles utilizam são armazenados. Ela permite o acesso aleatório a qualquer endereço de memória com tempos de acesso relativamente consistentes. A RAM é volátil, o que significa que seu conteúdo é perdido quando a energia é desligada.
  - **Memória Virtual**: Uma técnica de gerenciamento de memória que permite ao sistema operacional utilizar espaço no disco rígido (HD ou SSD) como uma extensão da memória RAM. Quando a RAM física está cheia, o sistema operacional pode mover temporariamente páginas de memória inativas para o disco (swap out) e trazê-las de volta para a RAM quando necessário (swap in). A memória virtual permite executar mais programas do que caberiam na RAM física, mas o acesso é muito mais lento.
