# Coleta de Informações (Footprinting) em Pentest

A **coleta de informações** ou **footprinting** é a **primeira etapa** de um pentest. O reconhecimento consiste em obter todas as informações a respeito da rede, incluindo topologia, mapeamento, servidores, funcionários, entre outros.

Quanto mais informações forem coletadas, **maior será a probabilidade de sucesso** no acesso ao sistema auditado.

---

## Fontes de Informações

Todas as informações relacionadas ao segmento da empresa podem ser valiosas para o processo de coleta, como:

- Servidores
- Roteadores
- Firewalls
- Hábitos dos funcionários
- Capacitação dos funcionários
- Pessoas relacionadas à empresa
- Empresas terceirizadas
- Emails, redes sociais (Facebook, LinkedIn)
- Telefones
- Informações descartadas no lixo

Essas fontes ajudam significativamente na coleta de informações. Além disso, **engenharia social** pode ser aplicada para ampliar o volume de informações coletadas.

---

## Uso de Ferramentas e Pesquisa Online

Mecanismos de busca como **Google** e **Yahoo** são poderosas ferramentas para coleta rápida de informações. Em poucas horas, conseguimos obter dados que potencializam o teste de intrusão. Um bom começo é **pesquisar no site alvo**:

1. **Ler o site com atenção**: Identifique domínios associados, emails de contato, nomes da administração, etc.
2. **Extrair informações interessantes**: Informações como esses dados podem ser usadas para ataques futuros (ex.: quebra de sistemas de login como HTTP, SMTP, WPA2).
3. **Repositórios históricos**: Acesse sites como **archive.org**, que armazena versões antigas de sites. Muitas vezes, o histórico de um site revela dados valiosos que não estão mais disponíveis publicamente.

---

## Coletando Informações sobre o Domínio

Uma etapa importante no processo de coleta é pesquisar sobre o **domínio alvo**. O domínio pode exibir dados públicos úteis, como:

- Emails do responsável
- Servidores DNS (para enumeração DNS e transferência de zona)
- País de origem

Essas informações são vitais para a construção de um plano de ataque. Uma das maneiras de coletar dados sobre um domínio é usando o comando **whois**.

---

## Comando Whois no Linux

O comando **whois** no Linux pode ser utilizado para buscar e enumerar informações sobre um domínio nos órgãos regulamentadores. Antes de usá-lo, é importante entender como funciona a estrutura de domínios na internet.

Cada país tem um órgão **regulamentador de domínios**. Por exemplo, no Brasil, o responsável é o **registro.br**. Esses órgãos são controlados por entidades superiores. O **registro.br** é vinculado ao **Lacnic**, que gerencia os domínios da América Latina. O **IANA** (ou futura ICANN) é a entidade responsável pela gestão global.

---

## Exemplo de Uso do Whois

Para realizar uma busca no Kali Linux, utilize o seguinte comando:

```bash
root@kali# whois www.site.com.br
```

```bash
root@kali# whois www.microsoft.com.br
```

Essa busca irá retornar informações públicas registradas sobre o domínio, como emails de contato e servidores DNS.
