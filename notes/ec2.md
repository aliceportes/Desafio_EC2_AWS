# EC2 (Elastic Compute Cloud)

- Serviço de **computação escalável** da AWS para criar máquinas virtuais na nuvem.
- Permite rodar aplicações em **Windows ou Linux**.
- Modelo **IAAS (Infraestrutura como Serviço)**:
  - AWS cuida da infraestrutura física (hardware, rede, energia).
  - Usuário é responsável por sistema operacional, dados, aplicativos e conexões.
- Cada instância EC2 é composta por:
  - CPU
  - Memória
  - Disco
  - Rede
  - Sistema Operacional
- Segurança configurada via **Security Groups** (firewall virtual):
  - Definição de portas, protocolos e IPs autorizados.
- As instâncias podem ser integradas com outros serviços, como **EBS** (armazenamento em blocos) e **S3** (armazenamento de objetos).

---

## Tipos de instâncias
- **General Purpose (T, M):** equilíbrio entre CPU, memória e rede.
- **Compute Optimized (C):** cargas de trabalho que exigem alto poder de processamento.
- **Memory Optimized (R, X, Z):** indicado para bancos de dados e aplicações que precisam de muita memória.
- **Storage Optimized (I, D, H):** leitura/escrita intensiva em disco (ex.: Big Data, Data Warehouses).
- **Accelerated Computing (P, G, F):** indicado para IA, machine learning, renderização gráfica e simulações complexas.

---

## Modelos de compra
- **On-Demand:** 
  - Paga por hora/segundo de uso.
  - Ideal para testes, aplicações temporárias ou cargas imprevisíveis.
- **Reserved:** 
  - Mais barato (até 70% de desconto).
  - Exige compromisso de 1 ou 3 anos.
  - Bom para workloads estáveis e de longo prazo.
- **Spot:** 
  - Até 90% de desconto.
  - Pode ser interrompida pela AWS a qualquer momento (com aviso de 2 minutos).
  - Boa para cargas flexíveis, como processamento em lote ou testes de resiliência.

---

## Insights principais
- **Escolher a instância certa** é crucial para equilibrar custo e desempenho.
- **Escalabilidade**: é possível aumentar ou diminuir capacidade rapidamente.
- **Responsabilidade compartilhada**: a AWS garante a infraestrutura, mas a configuração e segurança do sistema são do usuário.
- **Boa prática**: sempre configurar tags para organizar instâncias por projeto, ambiente ou custo.

---

## Otimização de custos 

- **Desligar instâncias** fora do horário de uso (ex.: ambientes de dev, teste e treinamento).
- **Remover recursos ociosos**, como volumes EBS não anexados, IPs elásticos não utilizados, snapshots sem política de retenção.
- **Escalar recursos conforme demanda**:
  - **Verticalmente:** aumentar CPU/memória da mesma instância em picos temporários.
  - **Horizontalmente:** adicionar mais instâncias para dividir a carga.
- **Escolher o modelo certo de instância:**
  - **On-Demand:** flexível, paga por hora, ideal para testes e workloads imprevisíveis.
  - **Reserved:** até 70% mais barato, compromisso de 1 ou 3 anos. Bom para cargas estáveis.
  - **Spot:** até 90% de desconto, mas pode ser interrompida. Boa para workloads tolerantes a falhas.

