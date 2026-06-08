# petshop-control-system

# Sistema de Controle de Banho

Este projeto é um sistema de simulação interativa via terminal para o controle de uma máquina de banho automatizada de pet shop. O software gerencia os recursos internos da máquina (água e shampoo), o estado de higiene do equipamento e o fluxo de atendimento do animal (entrada, banho e saída).

O projeto foi desenvolvido para consolidar conceitos fundamentais de **Programação Orientada a Objetos (POO)** em Java.

---

## Conceitos de POO Aplicados

O sistema foi modelado utilizando boas práticas de desenvolvimento orientado a objetos, destacando-se:

* **Encapsulamento:** As classes `Pet` e `PetMachine` protegem seus estados internos (`water`, `shampoo`, `clean`, `pet`) através de modificadores de acesso `private`, expondo o comportamento estritamente necessário por meio de métodos públicos de verificação e ação.
* **Associação de Objetos:** A classe `PetMachine` possui uma relação de associação com a classe `Pet` (uma máquina *tem um* pet), controlando dinamicamente quando o animal entra e sai do ciclo de lavagem.
* **Responsabilidade Única:** Cada classe possui um papel bem definido no ecossistema da aplicação:
    * `Pet`: Representa a entidade do animal e seu estado de higiene.
    * `PetMachine`: Centraliza as regras de negócio, limites de insumos e funcionamento do maquinário.
    * `Main`: Atua como a camada de interface (CLI), capturando as entradas do usuário usando `Scanner` e direcionando os comandos.

---

## Regras de Negócio Implementadas

O código simula restrições realistas de um ambiente operacional:
1.  **Limitação de Insumos:** A máquina inicia com capacidade padrão (30L de água e 10L de shampoo). Cada banho consome 10L de água e 2L de shampoo.
2.  **Fluxo de Higiene da Máquina:** Retirar um pet que tomou banho deixa a máquina temporariamente suja. O sistema bloqueia a entrada de um novo pet até que a ação de limpeza seja executada.
3.  **Validações de Estado:** Não é possível dar banho sem um pet inserido, nem colocar um animal se a máquina já estiver ocupada.
