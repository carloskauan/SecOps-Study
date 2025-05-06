# 📡 DHCP – Dynamic Host Configuration Protocol

**DHCP** é um protocolo da **camada de aplicação** (7ª camada do modelo OSI), usado para **atribuir automaticamente configurações de rede** aos dispositivos que se conectam a uma rede.

💡 Em vez de configurar manualmente endereços IP, gateway, DNS e outros parâmetros, o DHCP **automatiza esse processo**, facilitando a administração e reduzindo erros.

---

## 🧱 Estrutura e Arquitetura

### 🔧 Componentes Principais

- **Cliente DHCP**  
  Dispositivo que solicita configurações de rede (PCs, notebooks, celulares, VMs, etc.)

- **Servidor DHCP**  
  Responsável por fornecer os parâmetros de rede (pode ser um roteador, switch de camada 3 ou servidor dedicado).

- **Agente de Transmissão (Relay)**  
  Encaminha mensagens DHCP entre sub-redes, muito útil em redes de grande porte.

---

## 🔄 Ciclo DORA – Processo de Alocação

O processo de atribuição dinâmica de IP segue 4 etapas, conhecidas pelo acrônimo **DORA**:

### 1. 📢 Discover
O cliente envia uma mensagem **`DHCPDISCOVER`** em broadcast para localizar servidores DHCP.  
> Como ainda não possui IP, o pacote vai para `255.255.255.255`.

### 2. 🎁 Offer
Um ou mais servidores respondem com **`DHCPOFFER`**, oferecendo:
- Endereço IP sugerido
- Máscara de sub-rede
- Gateway padrão
- Servidores DNS
- Tempo de concessão (lease time)

### 3. 📩 Request
O cliente envia um **`DHCPREQUEST`** aceitando uma das ofertas.  
> Também pode ser usado para renovar um IP já em uso.

### 4. ✅ Acknowledge
O servidor envia **`DHCPACK`** confirmando a concessão do IP.  
> A partir daí, o cliente pode usar o endereço atribuído.

---

## 📌 Resumo

✅ O DHCP é um **componente fundamental** para:

- Automatizar configurações de rede
- Melhorar a escalabilidade
- Reduzir erros operacionais
- Simplificar a administração de redes domésticas e corporativas

---

| ID do Produto | Referência | Descrição             | Quantidade | Valor Unitário (R\$) | Total (R\$) |
| ------------- | ---------- | --------------------- | ---------- | -------------------- | ----------- |
| 001           | REF-A001   | Caneta Azul           | 10         | 2,50                 | 25,00       |
| 002           | REF-B002   | Caderno Universitário | 5          | 15,00                | 75,00       |
| 003           | REF-C003   | Mochila Escolar       | 2          | 120,00               | 240,00      |

# 🌐 DNS (Domain Name System)

O **DNS** é o serviço responsável por **traduzir nomes de domínios em endereços IP** (e vice-versa).  

Por exemplo, o domínio para os endereços:

- 🌍 `www.site.com.br`
- 📂 `ftp.site.com.br`
- ✉️ `smtp.site.com.br`

é **`site.com.br`**.

---

## 🧭 Estrutura Hierárquica dos Domínios

Os domínios na internet são estruturados de forma **hierárquica**.  
Ao acessar `www.site.com.br`, o navegador faz consultas na seguinte ordem:

1. 🔝 Domínio de topo (TLD): `.br`
2. 🧱 Subdomínio: `.com`
3. 🏠 Domínio: `site.com.br`

Essa hierarquia funciona como uma **árvore**, indo do mais geral ao mais específico.

---

## 📡 Exemplo de Interação com o Servidor DNS

```plaintext
🖥️ Cliente:
– Servidor, qual é o IP do mta7.am0.yahoodns.net?

🌐 Servidor:
– Cliente, o IP é 66.196.118.35.

🖥️ Cliente:
– Servidor, qual é o IP do mta6.am0.yahoodns.net?

🌐 Servidor:
– Cliente, o IP é 98.138.112.34.
```

---

## 🛠️ Tipos de Servidores DNS

### 🧠 Somente Cache

- 🔁 Responde às consultas buscando outros servidores DNS.
- 📦 Armazena temporariamente os resultados (cache).
- ⚡ Responde rapidamente a consultas repetidas.
- 🔧 **Exemplo:** o `bind` utiliza essa configuração por padrão.

---

### 📘 Servidor Mestre (Primário)

- 📂 Contém um banco de dados local com as informações do domínio.
- 🏛️ É a **fonte oficial** de dados DNS.
- ✅ Responde diretamente às consultas feitas por clientes.

---

### 📙 Servidor Escravo (Secundário)

- 🟢 Também responde às consultas DNS.
- 🔄 Recebe os dados por **transferência de zona** do servidor mestre.
- 📤 Cópia completa dos registros e IPs para manter sincronização.

---

## 🧾 Registros DNS

As informações dos servidores DNS ficam armazenadas em **registros**, que definem tipos específicos de dados associados a um nome DNS.

| 🏷️ Tipo de Registro | 📖 Função                                             |
|----------------------|------------------------------------------------------|
| 🅰️ A                | Associa o nome DNS a um endereço IP.                 |
| 🧮 HINFO            | Associa o nome DNS a informações de hardware.        |

---

🔚 **Resumo:** O DNS é uma peça fundamental da internet, responsável por permitir que possamos acessar sites usando nomes amigáveis em vez de números difíceis de memorizar. 🚀
