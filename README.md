# ModeloOsMecanica
  ## Modelo de ordem de serviços utilizando um exemplo de uma mecanica.

## 1. Tabela Clientes
Armazena informações sobre os clientes que levam seus veículos para a oficina.
Campos:
id_cliente (PK): Identificador único do cliente.
nome: Nome do cliente.
endereco: Endereço do cliente.
telefone: Telefone de contato do cliente.
email: E-mail do cliente.

## 2. Tabela Veiculos
Armazena informações sobre os veículos dos clientes.
Campos:
id_veiculo (PK): Identificador único do veículo.
id_cliente (FK): Identificador do cliente dono do veículo.
marca: Marca do veículo.
modelo: Modelo do veículo.
ano: Ano de fabricação do veículo.
placa: Placa do veículo.

## 3. Tabela Mecanicos
Armazena informações sobre os mecânicos da oficina.
Campos:
id_mecanico (PK): Identificador único do mecânico.
nome: Nome do mecânico.
endereco: Endereço do mecânico.
especialidade: Especialidade do mecânico (e.g., motor, suspensão, elétrica).

## 4. Tabela Equipes
Armazena informações sobre as equipes de mecânicos que trabalham nas OS.
Campos:
id_equipe (PK): Identificador único da equipe.
nome_equipe: Nome da equipe.

## 5. Tabela Equipe_Mecanicos
Relaciona mecânicos a equipes.
Campos:
id_equipe (FK): Identificador da equipe.
id_mecanico (FK): Identificador do mecânico.

## 6. Tabela Ordens_Servico (OS)
Armazena informações sobre as ordens de serviço.
Campos:
id_os (PK): Identificador único da ordem de serviço.
id_veiculo (FK): Identificador do veículo associado à OS.
id_equipe (FK): Identificador da equipe responsável pela OS.
data_emissao: Data de emissão da OS.
data_conclusao: Data prevista para conclusão dos trabalhos.
status: Status da OS (e.g., "Aguardando aprovação", "Em andamento", "Concluída").
valor_total: Valor total da OS (soma dos serviços e peças).

## 7. Tabela Servicos
Armazena informações sobre os serviços que podem ser realizados na oficina.
Campos:
id_servico (PK): Identificador único do serviço.
descricao: Descrição do serviço.
valor_mao_de_obra: Valor da mão de obra para o serviço.

## 8. Tabela Pecas
Armazena informações sobre as peças que podem ser utilizadas nos serviços
Campos:
id_peca (PK): Identificador único da peça.
descricao: Descrição da peça.
valor: Valor da peça.

## 9. Tabela OS_Servicos
Relaciona os serviços realizados em uma OS.
Campos:
id_os (FK): Identificador da ordem de serviço.
id_servico (FK): Identificador do serviço.
quantidade: Quantidade de vezes que o serviço foi realizado.
valor_total_servico: Valor total do serviço (quantidade * valor_mao_de_obra).

## 10. Tabela OS_Pecas
Relaciona as peças utilizadas em uma OS.
Campos:
id_os (FK): Identificador da ordem de serviço.
id_peca (FK): Identificador da peça.
quantidade: Quantidade de peças utilizadas.
valor_total_peca: Valor total da peça (quantidade * valor).

## 11. Tabela Autorizacoes
Armazena as autorizações dos clientes para a execução dos serviços.
Campos:
id_autorizacao (PK): Identificador único da autorização.
id_os (FK): Identificador da ordem de serviço.
id_cliente (FK): Identificador do cliente que autorizou.
data_autorizacao: Data da autorização.
status_autorizacao: Status da autorização (e.g., "Autorizado", "Pendente").
