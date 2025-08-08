# DIOoficinaprojeto
Projeto de um sistema de uma oficina mecânica
O modelo é composto por tabelas de entidades principais e tabelas de ligação para gerenciar relacionamentos complexos.

Tabelas Principais (Entidades)
Clientes: Armazena os dados cadastrais dos clientes.

Veiculos: Contém as informações de cada veículo, sendo que cada veículo pertence a um único cliente.

Equipe_de_Mecanicos: Cadastra as equipes de trabalho da oficina.

Mecanicos: Cadastro individual de cada mecânico, com seus dados e especialidade.

OS: É a tabela central do sistema. Cada linha representa uma Ordem de Serviço única, vinculada a um veículo e a uma equipe responsável.

Pecas: Catálogo de todas as peças disponíveis para uso, com seus respectivos valores.

Servicos: Catálogo de todos os serviços de mão de obra oferecidos, com seus valores.

Relacionamentos Muitos-para-Muitos (M:N)
A flexibilidade do sistema reside no uso de tabelas de ligação para gerenciar os relacionamentos M:N:

OS_has_Pecas e OS_has_Servicos:

Problema Resolvido: Uma única Ordem de Serviço pode necessitar de várias peças e de vários serviços diferentes.

Solução: Estas tabelas criam a ponte entre a OS e os catálogos de Pecas e Servicos. Isso permite que uma OS tenha uma lista ilimitada de itens sem poluir a tabela principal OS.

Equipe_has_Mecanicos:

Problema Resolvido: A regra de negócio define que um mecânico pode fazer parte de várias equipes, e uma equipe é composta por vários mecânicos.

Solução: Esta tabela de ligação conecta as tabelas Equipe_de_Mecanicos e Mecanicos, permitindo essa associação flexível. A chave primária composta (idEquipe, idMecanicos) garante que um mecânico não possa ser adicionado duas vezes na mesma equipe.
