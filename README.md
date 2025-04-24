# Pricipios de segurança
### Autenticidade
Define que uma informação etsá sendo enviada por uma fonte segura, e não foi interceptada e alterada por atacantes

###

# Configurando o Redo no Kali no VirtualBox

> **Observação:** A instalação do Kali Linux no VirtualBox deve ser feita de forma padrão, utilizando a imagem oficial disponibilizada no site do Kali e seguindo o processo típico de instalação no VirtualBox, sem modificações avançadas no sistema ou nas configurações iniciais.

Por padrão, as máquinas virtuais no VirtualBox são configuradas para utilizar o modo **NAT**. Esse modo, porém, não fornece endereços IP válidos diretamente para as VMs, o que pode limitar a comunicação com outros dispositivos na rede local.

Para contornar essa limitação, recomenda-se utilizar o modo **Bridged Adapter**, que permite à VM obter um endereço IP válido diretamente do roteador da rede, como se fosse um dispositivo físico conectado à rede local. 

Além disso, é possível ativar o modo **promíscuo**, que permite à VM capturar pacotes de rede que não são destinados diretamente a ela, o que é especialmente útil em testes de segurança e análises de tráfego de rede.

Essas opções devem ser configuradas diretamente pelo VirtualBox. Para isso:

1. Selecione a VM desejada (por exemplo, o Kali Linux).
2. Clique em **Configurações**.
3. Vá até a aba **Rede**.
4. No campo **Modo de Acesso à Rede**, selecione **Placa em modo Bridge (Bridged Adapter)**.
5. Logo abaixo, no campo **Modo Promíscuo**, selecione **Permitir Tudo**.

Após aplicar essas configurações, inicie a VM e verifique se ela obteve um IP válido da rede.

# Terminais de comando Kali

### Iniciar serviços de rede
~~~
root@kali# /etc/init.d/networking start
~~~
### Interromper serviços de rede 
~~~
root@kali# /etc/init.d/networking stop
~~~
### Verificar IP
~~~
root@kali# ifconfig
~~~
### Atribuir numero IP via DHCP
~~~
root@kali# dhclient eth0
~~
