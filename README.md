# Modelo de previsão de contratação no âmbito do Decreto nº 11.430/2023

## Sobre o Decreto nº 11.430/2023

O Decreto nº 11.430/2023 regulamenta a Lei nº 14.133/2021 para dispor sobre a exigência, em contratações públicas, de percentual mínimo de mão de obra constituída por mulheres vítimas de violência doméstica e sobre a utilização do desenvolvimento, pelo licitante, de ações de equidade entre mulheres e homens no ambiente de trabalho como critério de desempate em licitações, no âmbito da administração pública federal direta, autárquica e fundacional.

Os editais de licitação e os avisos de contratação direta para a contratação de serviços contínuos com regime de dedicação exclusiva de mão de obra preverão o emprego de mão de obra constituída por mulheres vítimas de violência doméstica, em percentual mínimo de 8%, aplicando-se a contratos com quantitativos mínimos de 25 colaboradores.

As vagas incluem mulheres trans, travestis e outras possibilidades do gênero feminino e serão destinadas prioritariamente a mulheres pretas e pardas, observada a proporção de pessoas pretas e pardas na unidade da federação onde ocorrer a prestação do serviço, de acordo com o último censo demográfico do Instituto Brasileiro de Geografia e Estatística - IBGE.

É importante mencionar que o normativo indica que indisponibilidade de mão de obra com a qualificação necessária para atendimento do objeto contratual não caracteriza descumprimento da aplicação mínima de contratação. 

## Criação do modelo de previsão

O modelo de previsão foi baseado na ideia de construir um modelo de machine learning a partir de dados históricos dos contratos . A base de dados utilizada foi a base da CGU de 2019 a 2024 publicada quadrimestralmente no portal de Dados Abertos com informações enviadas pelos órgãos à Controladoria.

Os relatórios quadrimestrais publicados estão no formato csv e trazem 23 colunas. Entre elas, destacam-se as seguintes: número do contrato com a empresa terceirizada, CNPJ da empresa terceirizada, código da Classificação Brasileira de Ocupações (CBO), quantidade de horas semanais de trabalho do terceirizado, valor mensal do salário, valor mensal do custo e código SIAFI do órgão onde o terceirizado trabalha.

Essas variáveis são consideradas importantes para o produto de previsão de contratação, pois têm impacto na estrutura do agrupamento dos terceirizados, já que o foco é prever o quantitativo de terceirizados por contrato. Para ter mais informações do contrato, o objetivo era tratar os dados, agrupar os terceirizados por contrato e, via API do Portal da Transparência, trazer informações de cada um dos contratos - etapa de validação das informações.

Após diversas tentativas de validação, chegou-se a apenas 918 contratos validados, ou seja, por volta de 3% do universo de contratos do arquivo. Possivelmente os números de contrato do arquivo para validação, mesmo após o tratamento, não tem correspondência na API. Mesmo procurando apenas pelo CNPJ da empresa terceirizada e/ou pelo código SIAFI, não é possível afirmar categoricamente que aquele contrato se refere a determinado terceirizado. 

Ao buscar apenas pelo CNPJ da empresa terceirizada, foram encontrados diversos contratos, inclusive com o mesmo código SIAFI, mas referentes a anos distintos daquele presente no arquivo de validação, o que compromete a precisão na correspondência entre registros. Portanto, a fim de evitar vieses na construção do modelo, optou-se por suspender o projeto do modelo de previsão e buscar protótipos alternativos.

## Documentação do modelo

Este repositório contém os notebooks de extração, limpeza, tratamento e implementação da validação dos dados via API. 

## Desdobramentos para buscar a viabilidade do modelo

Um nova rodada de validação de dados do contrato com a base de dados disponível no Contratos.gov foi realizada em junho/2025 e, mais uma vez, não foram validados dados suficientes para a criação do modelo de previsão.

Há um relatório entregue à equipe de negócios com a descrição do que foi feito, além dos desafios encontrados. 