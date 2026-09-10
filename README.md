# chamada-smart-2026
[README.md](https://github.com/user-attachments/files/32036775/README.md)
# DoeFácil

Projeto acadêmico de controle de doações de roupas e alimentos.

**Instituição:** Unicesumar — Maringá/PR  
**Curso:** Engenharia de Software  
**Turma:** ESOFT4-M-A  
**Etapa:** AEP do 1º bimestre de 2026.2 — planejamento e modelagem.

## Integrantes

| Nome | RA |
| --- | --- |
| Arthur Correia Ramos Fonseca | 25240314-2 |
| Igor kasikawa da Silva | 25165089-2 |
| Paulo Fortunato | 25142855-2 |

## Proposta

Organizar os registros de recebimento e distribuição de itens, permitindo consultar o saldo disponível. O usuário previsto é o responsável por uma iniciativa de doações. O vínculo proposto com a ODS 1 está no apoio à organização da distribuição de itens básicos. Não foram realizadas entrevistas ou validações com uma instituição parceira, e não há impacto social medido.

## Funcionalidades planejadas

- RF01: cadastrar doadores com nome e telefone.
- RF02: registrar doações com um ou mais itens, data e doador. Roupas possuem tamanho e condição; alimentos possuem validade.
- RF03: consultar doações, detalhes e quantidades disponíveis, inclusive após reiniciar o programa.
- RF04: editar doações e itens, preservando as quantidades já distribuídas e o tipo de itens com saídas.
- RF05: excluir doações cadastradas por engano somente quando não houver distribuição de seus itens.
- RF06: registrar distribuições com data e quantidade, sem exceder o saldo.

As quantidades serão inteiras (peças ou embalagens/unidades). O saldo será calculado a partir das saídas. O projeto propõe impedir a distribuição de alimentos vencidos. Não inclui login, entregas, interface web ou cadastro de beneficiários.

## Tecnologias e modelagem propostas

Java, MySQL, JDBC e MySQL Connector/J, com interface pelo terminal. As versões serão definidas no desenvolvimento conforme o ambiente da equipe.

O domínio terá Doador, Doacao, ItemDoacao (abstrata), Roupa, Alimento e Distribuicao. Doacao compõe um ou mais itens. Roupa e Alimento sobrescreverão descreverDetalhes() com @Override. A tabela itens_doacao usará um campo tipo para identificar a subclasse.

O código será separado em menu, serviços, domínio e acesso a dados (DAO). O banco será modelado com doadores, doacoes, itens_doacao e distribuicoes. A validação do saldo e a gravação da saída serão feitas na mesma transação, com bloqueio do item.

## Estrutura

| Caminho | Finalidade |
| --- | --- |
| src/ | Código Java a desenvolver no 2º bimestre. |
| docs/ | Documento da primeira entrega e fontes dos diagramas. |
| database/ | Script SQL a desenvolver no 2º bimestre. |

Os arquivos .gitkeep mantêm as pastas preparadas no Git. Eles não são código do sistema.

## Situação e execução

Esta é a entrega de planejamento. Ainda não existe aplicação executável ou script SQL implementado. No 2º bimestre, este README deverá receber versões, dependências, configuração do banco, comandos de compilação e execução e instruções para importar o SQL.

## Planejamento proposto

| Período relativo | Entrega | Responsável proposto |
| --- | --- | --- |
| Semanas 1 e 2 | Conexão MySQL e cadastro de doadores | Arthur |
| Semanas 3 e 4 | Registro e consulta de doações, herança e polimorfismo | Igor |
| Semanas 5 e 6 | Edição, exclusão e validações | Paulo |
| Semanas 7 e 8 | Distribuição, integração, validação e documentação | Todos |

A distribuição de tarefas e a duração são propostas a revisar pelo grupo. O calendário do 2º bimestre ainda não foi divulgado; as datas serão acrescentadas após sua divulgação. Cada integrante deverá registrar suas contribuições no histórico do repositório.

## Antes do envio

- Inserir o link real do repositório no PDF; o campo atual está pendente.
- Confirmar os responsáveis e revisar o cronograma relativo. O guia pede datas, mas o calendário ainda não está disponível.
- Conferir a visibilidade pública e a presença das pastas.

## Referências

- [ONU Brasil — ODS 1](https://brasil.un.org/pt-br/sdgs/1)
- [Dev.java — Inheritance](https://dev.java/learn/inheritance/)
- [MySQL — Connector/J](https://dev.mysql.com/doc/connector-j/en/)
- Guia_Extraoficial_AEP_4Semestre_2026.pdf, fornecido pelo grupo.
- Exemplo_AEP_ChamadaSmart.pdf, fornecido pelo grupo como referência de apresentação.
