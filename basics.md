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


## 📑 Tipos de Registro DNS

O servidor DNS responde a solicitações graças aos **registros DNS**.  
Saber identificar os principais tipos de registros é fundamental para entender o funcionamento e comportamento durante testes.

---

### 📌 Principais Tipos de Registros DNS

#### 🧭 NS (Name Server)
Identifica os **servidores DNS primário e secundário** responsáveis por um domínio.

📘 **Exemplo:**
```dns
kali.com.br. IN NS nameserver1.kali.com.br
```

---

#### 🅰️ A – Endereço de Host (IPv4)
Associa **nomes DNS com endereços IPv4**.

📘 **Exemplos:**
```dns
kali.com. IN A 127.0.0.1
kali.com.br. IN A 192.168.1.2
kali2.com.br. IN A 192.168.1.3
```

---

#### 🧾 AAAA – Endereço de Host (IPv6)
Associa **nomes DNS com endereços IPv6**.

📘 **Exemplo:**
```dns
ipv6_host1.kali.com. IN AAAA 4321:0:1:2:3:4:567:89ab
```

---

#### 🔁 CNAME (Canonical Name)
Mapeia um **alias (apelido)** de um servidor DNS para outro.  
Permite que múltiplos nomes apontem para o mesmo IP.

📘 **Exemplos:**
```dns
www.servidor.com.br. CNAME servidor.com.br.
ftp.servidor.com.br. CNAME servidor.com.br.
smtp.servidor.com.br. CNAME servidor.com.br.
```

---

#### 🖥️ HINFO (Host Information)
Armazena **informações sobre o host**, como CPU, sistema operacional, etc.

📘 **Exemplo:**
```dns
kali.com.br. HINFO INTEL-386 LINUX
```

---

#### ✉️ MX (Mail Exchanger)
Armazena **informações de servidores de e-mail**, incluindo prioridade.

📘 **Exemplos:**
```dns
kali.com.br. MX 5 mail1.kali.com.br
kali.com.br. MX 10 mail2.kali.com.br
```

🔔 **Nota:** quanto menor o número, **maior a prioridade**.

---

#### 🔄 PTR (Pointer)
Utilizado para criar **zonas reversas**, mapeando um IP para um nome DNS.  
É o inverso do registro tipo A.

📘 **Exemplo:**
```dns
1.168.192.in-addr.arpa. PTR host.kali.com.br.
```

---

#### 🧷 SOA (Start of Authority)
Define as **características de uma zona**, incluindo servidor principal, e-mail do responsável, TTLs e número de série.

📘 **Exemplo:**
```dns
@ IN SOA nameserver.kali.com.br. postmaster.kali.com.br. (
    1      ; serial number
    3600   ; refresh [1h]
    600    ; retry [10m]
    86400  ; expire [1d]
    3600 ) ; min TTL [1h]
```
