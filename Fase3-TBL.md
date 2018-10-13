## ℹ️ Inspeção de modelo de dados

- Problema: Achar os defeitos de um modelo de dados
- Contexto: [aqui](https://aprender.ead.unb.br/pluginfile.php/590584/mod_resource/content/1/Contexto_TBL1_Fase3.pdf)

- ## Resultados

<p align="justify">A tabela a seguir, descreve os erros encontrados em todos os níveis do projeto lógico de Banco de dados, bem como a criticidade desse erro, sugestões para correção do erro e o tempo estimado para ser realizada essa correção.

| Artefato             | Descrição do erro                                                                                                                                                 | Criticidade | Proposta de reparo                                                                                               | Prazo sugerido |
|----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------|------------------------------------------------------------------------------------------------------------------|----------------|
| DE-R                 | Ao deixar atributos de cliente em venda, permite apenas uma compra por cliente. Erro de lógica                                                                    | Alta        | Retirar o nome do cliente da entidade venda e criar uma entidade cliente com nome, cpf e id                      | 5 minutos      |
| DE-R                 | Falta o sentido do relacionamento comercializa. Erro de diagramação                                                                                               | Baixa       | Inserir o sentido do relacionamento comercializa                                                                 | 1 minuto       |
| DE-R                 | Um remédio poder estar em várias receitas e o contrário também ocorre. Dessa forma o relacionamento não pode ser 1:1. Erro de lógica                              | Alta        | Alterar a cardinalidade do relacionamento de 1:1 para n:m                                                        | 1 minuto       |
| DE-R                 | Para realizar o relacionamento citado acima, a entidade Receita deve possuir um Id. Erro de lógica                                                                | Alta        | Inserir uma chave primária(Id) na entidade Receita                                                               | 1 minuto       |
| DE-R                 | Não está sendo possível armazenar de forma adequada a quantidade individual de cada item na venda. Erro de lógica                                                 | Média       | Inserir um atributopara quantidade no relacionamento comercializa e indicar que a quantidade em venda é derivado | 2 minutos      |
| Diagrama Lógico      | Com as mudanças feitas no DE-R,o diagrama lógico fica em desconformidade com ele. Erro de conformidade entre os níveis                                            | Alta        | Adaptar mudanças citadas no DE-R para o lógico                                                                   | 10 minutos     |
| Diagrama Lógico      | Os atributos de quantidade e preço total da entidade Venda são derivados e não devem constar no diagrama lógico. Erro de diagramação                              | Média       | Retirar os dois atributos do diagrama lógico                                                                     | 1 minuto       |
| Diagrama Lógico      | Uma linha sai da tabela venda e não se liga com nenhuma outra tabela                                                                                              | Baixa       | Retirar essa linha                                                                                               | 1 minuto       |
| Dicionário de dados  | Com as mudanças feitas no DE-R e no diagrama lógico, o dicionário de dados fica em desconformidade com eles. Erro de conformidade entre os níveis                 | Alta        | Adaptar mudanças citadas no DE-R e no lógico para o dicionário de dados                                          | 15 minutos     |
| Dicionário de dados  | Os atributos de tipo INTEGER no dicionário de dados estão com um tamanho limitado. Isso não ocorre no diagrama lógico acima. Erro de conformidade entre os níveis | Baixa       | Limitar o tamanho máximo dos atributos do tipo INTEGER no diagrama lógico                                        | 3 minutos      |
| Dicionário de dados  | O atributo número da tabela Fabricante está limitado em 2 casas. Existem números de endereços com mais casas do que apenas 2. Erro de lógica                      | Alta        | Aumentar tamanho do atributo número para no mínimo 4                                                             | 1 minuto       |
| Tempo total estimado | -                                                                                                                                                                 | -           | -                                                                                                                | 41 minutos     |


- ## Sugestões de melhoria
<p align="justify">A tabela abaixo explicita as sugestões de melhoria encontradas que podem auxiliar a tornar o projeto mais coeso. Essas sugestões não explicitam erros, apenas áreas em que o projeto pode ser melhorado. É importante ressaltar que caso alguma sugestão seja acatada, ela deve ser replicada corretamente nos níveis inferiores.

Artefato | Sugestão|
------|------|
DER|- Acrescentar id na entidade perfumaria;<br>- “Tipo” em perfumaria pode virar uma entidade;<br>- “Tarja” em medicamento pode virar uma entidade;<br>- “Tipo_embalagem” pode virar uma entidade;<br>- A especialização de produto não indica se é total ou parcial, pode-se colocar T ou P junto ao triângulo|
Lógico|- Atributos de data podem virar do tipo date ao invés de varchar<br>- Telefone pode ser transformado em char e ter seu tamanho máximo reduzido para 11<br>- CRM do médico na tabela receita deve ser um VARCHAR e não um INTEGER|
Dicionário de dados|Não foi encontrada nenhuma sugestão de melhoria|
