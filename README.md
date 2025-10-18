# 🧰 Sistema de Controle de Ordens de Serviço — Oficina Mecânica

## 📖 Descrição do Projeto
Este projeto apresenta o **modelo conceitual** de um sistema de controle e gerenciamento de **ordens de serviço (OS)** em uma **oficina mecânica**.  
O objetivo é registrar e controlar todo o ciclo de uma OS: desde a chegada do veículo, avaliação pela equipe, autorização do cliente, execução dos serviços e utilização de peças, até a finalização e entrega do veículo.

---

## 🧱 Estrutura Conceitual

O sistema contempla:

- **Clientes** que levam **veículos** para revisão ou conserto.  
- Cada **veículo** é designado a uma **equipe de mecânicos**.  
- Essa equipe **avalia**, **preenche** e **executa** uma **ordem de serviço (OS)**.  
- A **OS** é composta por **serviços** (tabela de referência de mão de obra) e **peças** utilizadas durante o conserto.  
- O valor total da OS é calculado com base nos serviços e peças empregados.

---

## 🔗 Principais Entidades

| Entidade | Descrição |
|-----------|------------|
| **Cliente** | Pessoa que possui veículos atendidos pela oficina. |
| **Veículo** | Automóvel trazido pelo cliente. |
| **Equipe** | Grupo de mecânicos responsáveis pela execução dos serviços. |
| **Mecânico** | Profissional com especialidade específica. |
| **Ordem de Serviço (OS)** | Documento que registra o conserto ou revisão de um veículo. |
| **Serviço** | Tipo de trabalho realizado, com valor de mão de obra definido. |
| **Peça** | Item ou componente utilizado na execução dos serviços. |
| **OS_Serviço / OS_Peça** | Entidades associativas que registram as quantidades e subtotais de serviços e peças em cada OS. |

---

## 🧩 Regras de Negócio

- Um cliente pode possuir vários veículos.  
- Cada veículo pode ter várias ordens de serviço.  
- Uma OS pertence a **um veículo** e é executada por **uma equipe**.  
- Uma equipe é composta por **vários mecânicos**.  
- Uma OS pode conter **vários serviços e várias peças**.  
- Um mesmo serviço ou peça pode estar presente em várias OS.  
- O cliente **autoriza** a execução antes do início dos trabalhos.  

---

## 🧠 Decisões de Modelagem

- Criadas entidades associativas `OS_Servico` e `OS_Peca` para tratar os relacionamentos N:N.  
- O campo `valor_total` na OS é um atributo derivado da soma de serviços e peças.  
- A equipe é modelada como entidade própria para permitir escalabilidade e reuso.  
- A tabela de referência de **mão de obra** é representada pela entidade `Serviço`.

---

## 🧭 Diagrama ER (conceitual)
