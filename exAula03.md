# Implantação de Rede Industrial  
## Indústria de Produção de Tijolos Ecológicos

---

# 1. Contextualização do Projeto

A empresa pretende modernizar o processo produtivo de tijolos ecológicos por meio da implantação de uma rede industrial capaz de integrar máquinas, sensores e sistema supervisório.

Atualmente, o controle da produção é parcialmente manual, o que dificulta:

- O monitoramento em tempo real  
- O controle preciso da prensa hidráulica  
- O registro histórico da produção  
- A identificação rápida de falhas  

A proposta consiste na implantação de uma infraestrutura de comunicação baseada em Ethernet Industrial, permitindo o controle automatizado e futura integração com sistemas corporativos.

---

# 2. Levantamento Técnico dos Equipamentos

A escolha dos equipamentos foi realizada considerando:

- Ambiente com poeira e vibração  
- Temperatura variável  
- Possibilidade de expansão futura  
- Disponibilidade no mercado nacional  

---

## 2.1 Controlador Lógico Programável (CLP)

**Modelo pesquisado:** Siemens S7-1200  
**Fornecedor consultado:** Siemens Brasil / RS Components  
**Valor médio:** R$ 4.400 a R$ 4.800  
**Prazo médio de entrega:** 15 a 25 dias  

### Justificativa da escolha

Optou-se por um CLP com comunicação Profinet e suporte a módulos de expansão, considerando que a indústria poderá futuramente adicionar novas prensas ou esteiras.

Quantidade prevista: 2 unidades  
Total estimado: R$ 9.000  

---

## 2.2 Switch Industrial Gerenciável

**Modelo pesquisado:** Siemens Scalance XB005  
**Valor médio:** R$ 2.500 a R$ 3.000  
**Prazo médio de entrega:** até 20 dias  

### Especificações relevantes

- 5 a 8 portas Ethernet  
- Faixa de temperatura operacional ampliada  
- Montagem em trilho DIN  
- Estrutura metálica resistente  

Justificativa: diferentemente de switches comerciais, o modelo industrial suporta vibração e interferência eletromagnética provenientes da prensa hidráulica.

Quantidade: 2 unidades  
Total estimado: R$ 5.600  

---

## 2.3 Cabeamento

- Cabo Ethernet CAT6 industrial blindado (300 m)  
- Conectores RJ45 industriais  
- Eletrocalhas metálicas  

Valor total estimado: R$ 2.700  
Prazo de aquisição: imediato (fornecedores nacionais)

A blindagem é fundamental devido aos motores e inversores de frequência, que geram ruído elétrico.

---

## 2.4 Interface Homem-Máquina (IHM)

**Modelo pesquisado:** Siemens KTP700 Basic  
**Valor médio:** R$ 3.000  
Quantidade prevista: 2 unidades  

Permite que o operador visualize:

- Quantidade produzida  
- Tempo de ciclo  
- Alarmes de falha  
- Status da prensa  

Total estimado: R$ 6.000  

---

## 2.5 Sistema Supervisório (SCADA)

**Software sugerido:** Elipse E3  
**Valor estimado da licença:** R$ 8.000  
**Computador industrial:** R$ 6.000  

Funções previstas:

- Registro histórico  
- Relatórios de produção  
- Controle remoto  
- Integração futura com ERP  

---

# 3. Orçamento Consolidado

| Item                                   | Valor Estimado (R$) |
|----------------------------------------|----------------------|
| CLPs                                  | 9.000                |
| Sensores e módulos                    | 10.000               |
| Switches industriais                  | 5.600                |
| Cabeamento                            | 2.700                |
| IHMs                                  | 6.000                |
| SCADA + Computador                    | 14.000               |
| Serviços (instalação e programação)   | 30.000               |
| **Total Geral Estimado**              | **77.300**           |

Prazo total estimado do projeto: 45 a 60 dias.

---

# 4. Análise de Viabilidade Técnica e Econômica

## 4.1 Análise Técnica

A solução proposta é adequada ao ambiente industrial, pois utiliza:

- Equipamentos industriais certificados  
- Comunicação padrão Ethernet  
- Topologia simples (estrela)  
- Separação entre rede industrial e rede corporativa  

Além disso, a escalabilidade é garantida pela possibilidade de:

- Adicionar novos módulos de I/O  
- Expandir switches  
- Integrar novos CLPs  
- Conectar futuramente ao ERP  

---

## 4.2 Análise Econômica

Investimento inicial estimado: R$ 77.300  

Com base na estimativa de aumento de produtividade (entre 15% e 20%) e na redução do desperdício de matéria-prima, estima-se uma economia média mensal aproximada de R$ 7.000 a R$ 9.000.

### Payback estimado

Entre 9 e 12 meses.

---

## 4.3 Riscos e Dependências

- Dependência de fornecedor específico (Siemens)  
- Possível variação cambial  
- Necessidade de equipe técnica qualificada  

### Medidas de mitigação

- Treinamento técnico interno  
- Contrato de suporte técnico  
- Planejamento de estoque mínimo de peças críticas  

---

# 5. Diagrama da Arquitetura Proposta

                                      REDE CORPORATIVA
                                             │
                                      ┌──────▼──────┐
                                      │ Firewall /  │
                                      │  Roteador   │
                                      └──────┬──────┘
                                             │
                           ===============================
                           |   REDE INDUSTRIAL (VLAN)   |
                           ===============================
                                             │
                                   ┌─────────▼─────────┐
                                   │ Switch Industrial │
                                   │   Gerenciável     │
                                   └─────────┬─────────┘
                       ┌─────────────────────┼─────────────────────┐
                       │                     │                     │
                ┌──────▼──────┐       ┌──────▼──────┐       ┌──────▼──────┐
                │    CLP 1    │       │    CLP 2    │       │     IHM     │
                │ (Prensa 1)  │       │ (Prensa 2)  │       │ Operação    │
                └──────┬──────┘       └──────┬──────┘       └─────────────┘
                       │                     │
        ┌──────────────┼──────────────┐  ┌───┼──────────────┐
        │              │              │  │   │              │
   Sensores       Atuadores      Inversor  Sensores     Atuadores
  (Pressão,       (Válvulas,     de Freq. (Pressão,    (Motores,
   Umidade)        Motores)                Umidade)     Válvulas)

                                             │
                                   ┌─────────▼─────────┐
                                   │  Servidor SCADA   │
                                   │ (Supervisório)    │
                                   └─────────┬─────────┘
                                             │
                                   Banco de Dados /
                                   Histórico de Produção

                    -------------------------------------------
                    |  PORTAS DISPONÍVEIS NO SWITCH PARA      |
                    |  FUTURA EXPANSÃO (Novos CLPs / IHMs)    |
                    -------------------------------------------

A arquitetura proposta mantém organização lógica, segurança e permite expansão futura mediante a adição de novos dispositivos ao switch industrial.

---

# 6. Conclusão

A implantação da rede industrial é viável técnica e economicamente.

Além de aumentar a produtividade, a empresa passará a ter maior controle sobre o processo produtivo, reduzindo falhas e melhorando a tomada de decisão.

O projeto também prepara a indústria para futuras integrações com sistemas corporativos e para a adoção de conceitos de Indústria 4.0.
