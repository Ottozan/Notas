**ses1004** - Cadastro de Vendedores: Erro na verificação de duplicidade. Estava ocorrendo na alteração também. (Ricardo, via Skype)

**cca3047r** -  **Ficha de Sócio** - Incluído nome, cpf e data de nascimento dos filhos. Alterado para pegar **endereço do primeiro imóvel cadastrado** e não do cadastro do parceiro;



**lte3125r** - *Gestão Mais Leite e Reprodutivo* - Incluído resumo de número de visitas e quilometragem percorrida pelos técnicos quando a opção for **Gestão Mais Leite**, antes só era calculado no **Reprodutivo**



**ses3086r** - Extrato de Eventos - Verificação do motivo de saldos no valor de 0,01 ou -0,01 quando a quantidade está zerada (Marcos, via Skype).



**ses3138i** - Parceiros por Município / Localidade - Está pegando a data do SES-ASSO, quando deveria pegar do CCA-SCIO, consequentemente o TXT estava saindo errado. Corrigido.



**res3001**-*Gestao Estoque Insumos* - Incluído parâmetro na tela para listar produtos Inativos ou não. Padrão = "N". Alterados os programas chamados: ***ses3043i e ses3043r***



**ses3086r** -  *Extrato de Eventos* - Esse programa é chamado hoje pelo **SES3526I**, duas vezes, uma para o Evento 01 e uma para o Evento 20. Ele roda, tanto na tela quanto na crontab.
É preciso tirar a chamada do ses3526i para que ele rode uma vez e gere os dois arquivos, separados, um para cada evento.. Criado o **ses3086i** para essa finalidade.



**ses3826a** - chama o **ses3826r** - ***Planejamento Orçamentário** - utilizando direcionador contábil*, na crontab. Esse programa é chamado diversas vezes com parâmetros diferentes no ses3526i hoje. 



