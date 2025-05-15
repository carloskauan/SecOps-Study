# 📑 Sumário

- [📘 O que é um Sistema Operacional?](#-o-que-é-um-sistema-operacional)
- [⚙️ Principais Funções de um Sistema Operacional](#-principais-funções-de-um-sistema-operacional)
  - [🧠 Gerenciamento de Processos](#-gerenciamento-de-processos)
  - [💾 Gerenciamento de Memória](#-gerenciamento-de-memória)
  - [🖥️ Gerenciamento de Entrada/Saída (I/O)](#-gerenciamento-de-entradasaída-io)
  - [📁 Gerenciamento de Arquivos](#-gerenciamento-de-arquivos)
  - [🔐 Segurança e Proteção](#-segurança-e-proteção)
  - [🌐 Gerenciamento de Redes](#-gerenciamento-de-redes)
- [🧱 Estrutura Geral de um Sistema Operacional](#-estrutura-geral-de-um-sistema-operacional)
  - [🔌 Camadas Principais](#-camadas-principais)
- [🛠️ Chamada de Sistema (System Calls)](#️-chamada-de-sistema-system-calls)
- [🔐 Importância para a Cibersegurança](#-importância-para-a-cibersegurança)
- [🧩 Tipos de Sistemas Operacionais](#-tipos-de-sistemas-operacionais)
  - [🧱 Sistemas Monolíticos](#-sistemas-monolíticos)
  - [🔬 Sistemas Microkernel](#-sistemas-microkernel)
  - [⚖️ Sistemas Híbridos](#-sistemas-híbridos)
  - [⏱️ Sistemas de Tempo Real (RTOS)](#️-sistemas-de-tempo-real-rtos)
  - [🌐 Sistemas Distribuídos](#-sistemas-distribuídos)
  - [☁️ Sistemas Virtualizados e em Nuvem](#️-sistemas-virtualizados-e-em-nuvem)

# 📘 O que é um Sistema Operacional?

Um **Sistema Operacional (SO)** é um software essencial que coordena e gerencia o uso do hardware por parte dos programas e dos usuários.  
Ele atua como uma **ponte entre o usuário e o hardware**, garantindo que os recursos sejam utilizados de forma **eficiente, organizada e segura**.

---

## ⚙️ Principais Funções de um Sistema Operacional

### 🧠 Gerenciamento de Processos

- **Processo**: é um programa em execução.
- O SO é responsável por:
  - Criar, pausar, retomar e finalizar processos.
  - Realizar o **escalonamento da CPU**, ou seja, decidir qual processo usará a CPU e por quanto tempo.
  - Garantir que múltiplos processos compartilhem os recursos de forma **justa e eficiente** (multitarefas).

---

### 💾 Gerenciamento de Memória

- Garante que cada processo tenha a **quantidade de memória necessária**.
- Técnicas utilizadas:
  - **Paginação**: divide a memória em blocos (páginas) para facilitar a alocação.
  - **Segmentação**: divide com base na lógica dos dados (ex: código, dados, pilha).
- Protege a memória contra **acesso indevido** por outros processos.

---

### 🖥️ Gerenciamento de Entrada/Saída (I/O)

- Controla o acesso e a comunicação com dispositivos periféricos.
- Técnicas comuns:
  - **Buffering**: usa memória temporária para evitar espera.
  - **Caching**: armazena dados acessados com frequência.
  - **Spooling**: organiza tarefas em fila para dispositivos compartilhados (como impressoras).

---

### 📁 Gerenciamento de Arquivos

- Cria e organiza **arquivos e diretórios**.
- Controla **leitura, escrita, remoção e permissões**.
- Mantém a **integridade e segurança** dos dados armazenados.

---

### 🔐 Segurança e Proteção

- **Autenticação**: confirma a identidade do usuário.
- **Criptografia**: protege os dados armazenados e em trânsito.
- **Controle de acesso**: define quem pode acessar o quê.
- Previne que **programas maliciosos** afetem o sistema e outros usuários.

---

### 🌐 Gerenciamento de Redes

- Permite que o sistema se comunique com outros dispositivos via **protocolos de rede**.
- Gerencia conexões TCP/IP e a **transferência de dados entre sistemas distribuídos**.
- Essencial para a **internet, servidores e computação em nuvem**.

---

## 🧱 Estrutura Geral de um Sistema Operacional

### 🔌 Camadas Principais

- **Nível de Hardware**  
  Inclui todos os dispositivos físicos.  
  O SO interage com este nível através dos **drivers de dispositivo**.

- **Kernel**  
  O **coração do sistema operacional**.  
  Gerencia todos os recursos e fornece os serviços essenciais.  
  Pode ser:
  - **Monolítico**: tudo junto em um único bloco.
  - **Microkernel**: apenas o essencial no núcleo; o restante roda no espaço do usuário.

- **Bibliotecas do Sistema**  
  Oferecem funções reutilizáveis que permitem que programas acessem os recursos do sistema.

- **Shell (Interface do Usuário)**  
  Permite a interação do usuário com o sistema:
  - **CLI (Linha de Comando)**: ex. Bash, PowerShell.
  - **GUI (Interface Gráfica)**: ex. Windows Explorer, GNOME.

- **Aplicações de Usuário**  
  Programas que rodam sobre o sistema, como editores, navegadores, jogos etc.

---

## 🛠️ Chamada de Sistema (*System Calls*)

- Mecanismo pelo qual programas de usuário requisitam **serviços ao kernel**.
- Funcionam como **portas de entrada** para o núcleo do SO.
- Exemplos:

```c
fork();   // Cria um novo processo
exec();   // Executa um programa
read();   // Lê dados de um arquivo ou dispositivo
write();  // Escreve dados em um arquivo ou dispositivo
```
## 🔐 Importância para a Cibersegurança

- Vulnerabilidades no Sistema Operacional — especialmente no **kernel** ou nas **system calls** — são alvos comuns de ataques.
- Compreender a estrutura do SO permite:
  - Identificar e mitigar falhas de segurança.
  - Implementar mecanismos de defesa mais eficazes.
- Exemplos de ataques comuns:
  - **Escalonamento de privilégios**: quando um usuário comum obtém acesso de administrador.
  - **Buffer overflow**: exploração de estouros de memória para execução de código malicioso.
  - **Manipulação indevida de arquivos e permissões**: acesso não autorizado a dados sensíveis.

---

## 🧩 Tipos de Sistemas Operacionais

### 🧱 Sistemas Monolíticos

- O kernel é grande e contém todas as funcionalidades integradas.
- **Vantagens**: alto desempenho, já que tudo roda em espaço privilegiado.
- **Desvantagens**: uma falha em qualquer módulo pode comprometer todo o sistema.
- **Exemplos**: Linux, Unix clássico, Windows 95/98.

---

### 🔬 Sistemas Microkernel

- O kernel é reduzido, contendo apenas funções essenciais (como gerenciamento de processos e comunicação).
- Outros serviços (como drivers e sistema de arquivos) rodam fora do kernel, no espaço do usuário.
- **Vantagens**: maior segurança e estabilidade.
- **Desvantagens**: overhead devido à comunicação entre módulos.
- **Exemplos**: Minix, QNX.

---

### ⚖️ Sistemas Híbridos

- Combinam características de kernels monolíticos e microkernels.
- Buscam equilibrar **desempenho** e **modularidade**.
- **Exemplos**: Windows NT+, macOS moderno, Linux atual.

---

### ⏱️ Sistemas de Tempo Real (RTOS)

- Projetados para responder a eventos em **tempo determinístico e garantido**.
- Utilizados em ambientes onde atrasos são inaceitáveis (ex: controle de aviões, automação industrial).
- **Exemplos**: FreeRTOS, VxWorks.

---

### 🌐 Sistemas Distribuídos

- Conjunto de computadores independentes que colaboram como se fossem um único sistema.
- Características:
  - **Sincronização entre nós**.
  - **Distribuição de tarefas**.
  - **Tolerância a falhas**.
- **Exemplos**: Hadoop, Kubernetes, Google File System (GFS).

---

### ☁️ Sistemas Virtualizados e em Nuvem

- Permitem que múltiplos sistemas operacionais rodem sobre o mesmo hardware físico.
- Utilizam tecnologias como **máquinas virtuais** ou **containers**.
- **Vantagens**:
  - Melhor aproveitamento de recursos.
  - Isolamento entre ambientes.
- **Riscos**:
  - **Escape de VM**: quando um processo ultrapassa os limites da máquina virtual e afeta o host.
- **Exemplos**: VMware, KVM, Docker.

---
