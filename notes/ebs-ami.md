# EBS e AMI

## EBS (Elastic Block Store)
- Armazenamento em **blocos** anexado a instâncias EC2 (como um “HD/SSD externo”).
- Flexível: pode ser expandido conforme a necessidade.
- Casos de uso:
  - Bancos de dados (MySQL, PostgreSQL, Oracle)
  - Dados de aplicativos web
  - Logs de sistema

### Tipos de volume
- **gp3/gp2:** balanceado, custo x desempenho.
- **io1/io2:** alta performance para bancos críticos.
- **st1/sc1:** otimizado para throughput, dados menos acessados.

---

## Snapshots EBS
- **Backup incremental** de um volume EBS.
- Armazenados internamente no Amazon S3 (não visível ao usuário).
- Permitem:
  - Restaurar volumes
  - Copiar dados entre regiões (disaster recovery)
- **Boas práticas:**
  - Taguear snapshots
  - Definir políticas de retenção
  - Evitar manter cópias desnecessárias (custos extras)
  
---

## AMI (Amazon Machine Image)
- É uma **imagem pré-configurada** usada para lançar instâncias EC2.
- Contém:
  - Sistema operacional
  - Configurações de software
  - Aplicativos instalados
- Tipos de AMI:
  - Fornecidas pela AWS
  - AMIs da comunidade
  - AMIs personalizadas (criada pelo usuário a partir de uma instância)

### Por que usar AMIs?
- Padronizar ambientes
- Acelerar criação de novas instâncias
- Garantir consistência na configuração de servidores

### Relação entre AMI e EBS
- Ao criar uma AMI, a AWS gera automaticamente **snapshots dos volumes EBS** anexados à instância.
- Esses snapshots ficam armazenados e são usados como base para a AMI.
- Quando uma nova instância é lançada a partir da AMI:
  - A AWS cria **novos volumes EBS** a partir desses snapshots.
- Por isso, AMI, EBS e Snapshots andam juntos no ciclo de vida do EC2.

