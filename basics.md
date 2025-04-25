# DHCP

**DHCP** (Dynamic Host Configuration Protocol) é um protocolo da **camada de aplicação** do modelo OSI (7ª camada), usado para **atribuir dinamicamente informações de configuração de rede** a dispositivos (hosts) que se conectam à rede.

Em vez de configurar manualmente IPs, gateways, servidores DNS e outros parâmetros, o DHCP faz isso **automaticamente**, reduzindo erros e facilitando a administração da rede.

---

## Estrutura e Arquitetura

### Componentes Principais

1. **Cliente DHCP**  
   Dispositivo que precisa de configuração de rede, como computadores, máquinas virtuais, smartphones etc.

2. **Servidor DHCP**  
   Dispositivo responsável por fornecer as configurações, como um roteador, switch de camada 3 ou servidor dedicado.

3. **Agente de Transmissão (Relay)**  
   Utilizado em redes grandes para encaminhar mensagens DHCP entre sub-redes.

---

## Ciclo DORA

O processo DHCP envolve a troca de mensagens entre cliente e servidor, seguindo uma sequência de 4 etapas conhecida como **DORA**:

1. **Discover**  
   O cliente envia uma mensagem de broadcast (`DHCPDISCOVER`) procurando servidores DHCP.  
   > Como ainda não tem IP, a mensagem é enviada para todos na rede: `255.255.255.255`.

2. **Offer**  
   Um ou mais servidores DHCP respondem com uma oferta (`DHCPOFFER`) contendo:
   - Um IP sugerido  
   - Máscara de sub-rede  
   - Gateway padrão  
   - Servidor DNS  
   - Tempo de concessão (lease time)

3. **Request**  
   O cliente envia uma mensagem (`DHCPREQUEST`) aceitando a oferta recebida.  
   > Essa mensagem também pode ser usada para renovar um IP já atribuído.

4. **Acknowledge**  
   O servidor confirma a concessão do IP com uma mensagem (`DHCPACK`).  
   > A partir desse ponto, o cliente pode utilizar o IP atribuído.

---

> ✅ **Resumo:** O DHCP é essencial para automatizar a configuração de rede, melhorar a escalabilidade e reduzir erros operacionais em ambientes de rede, tanto domésticos quanto corporativos.
