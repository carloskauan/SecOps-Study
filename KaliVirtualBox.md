# 📑 Sumário

- [⚙️ Configurando o Redo no Kali Linux no VirtualBox](#️-configurando-o-redo-no-kali-linux-no-virtualbox)
  - [🌐 Modo de Rede no VirtualBox](#-modo-de-rede-no-virtualbox)
    - [🔄 Solução: Usar o Modo Bridged Adapter](#-solução-usar-o-modo-bridged-adapter)
    - [👁️ Modo Promíscuo](#️-modo-promíscuo)
  - [🛠️ Como Configurar no VirtualBox](#️-como-configurar-no-virtualbox)

- [💻 Terminais de Comando no Kali Linux](#-terminais-de-comando-no-kali-linux)
  - [🔌 Iniciar serviços de rede](#-iniciar-serviços-de-rede)
  - [⛔ Interromper serviços de rede](#-interromper-serviços-de-rede)
  - [📡 Verificar IP atual](#-verificar-ip-atual)
  - [📥 Atribuir IP automaticamente via DHCP](#-atribuir-ip-automaticamente-via-dhcp)

- [⬆️ Atualização de pacotes e sistema](#️-atualização-de-pacotes-e-sistema)
  - [📦 Atualizar repositório de programas](#-atualizar-repositorio-de-programas)
  - [🔧 Atualizar programas instalados](#-atualizar-programas-instalados)
  - [🖥️ Atualizar sistema operacional](#-atualizar-sistema-operacional)


# Configurando o Redo no Kali Linux no VirtualBox

> ⚠️ **Observação:**  
> A instalação do Kali Linux no VirtualBox deve ser feita de forma padrão, utilizando a imagem oficial do site do Kali e seguindo o processo típico de instalação no VirtualBox, **sem modificações avançadas** no sistema ou nas configurações iniciais.

---

## Modo de Rede no VirtualBox

Por padrão, as máquinas virtuais no VirtualBox são configuradas para utilizar o modo **NAT**.  
Esse modo, porém, **não fornece endereços IP válidos diretamente** para as VMs, o que pode limitar a comunicação com outros dispositivos na rede local.

### Solução: Usar o Modo Bridged Adapter

Para contornar essa limitação, recomenda-se utilizar o modo **Bridged Adapter**, que permite à VM:

- Obter um endereço IP válido diretamente do roteador da rede.
- Ser tratada como um dispositivo físico conectado à rede local.

### Modo Promíscuo

Também é possível ativar o **modo promíscuo**, permitindo à VM capturar pacotes de rede que **não são destinados diretamente a ela**, o que é especialmente útil em testes de segurança e análises de tráfego.

---

## Como Configurar no VirtualBox

1. Selecione a VM desejada (por exemplo, **Kali Linux**).
2. Clique em **Configurações**.
3. Vá até a aba **Rede**.
4. No campo **Modo de Acesso à Rede**, selecione **Placa em modo Bridge (Bridged Adapter)**.
5. Logo abaixo, no campo **Modo Promíscuo**, selecione **Permitir Tudo**.
6. Clique em **OK** para salvar.

Após aplicar essas configurações, inicie a VM e verifique se ela obteve um IP válido da rede.

---

# Terminais de Comando no Kali Linux

### Iniciar serviços de rede
```bash
root@kali# /etc/init.d/networking start
```

### Interromper serviços de rede
```bash
root@kali# /etc/init.d/networking stop
```

### Verificar IP atual
```bash
root@kali# ifconfig
```
### Atribuir IP automaticamente via DHCP
```bash
root@kali# dhclient eth0
```

# Atualização de pacotes e sistema

### Atualizar repositorio de programas
```bash
root@kali# /etc/init.d/networking start
```
### Atualizar programas instalados
```bash
root@kali# /etc/init.d/networking start
```
### Atualizar sistema operacional
```bash
root@kali# /etc/init.d/networking start
```

