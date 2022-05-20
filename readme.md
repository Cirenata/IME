# Aplicação de Mineração de Regras de Associação ao Banco de Dados do SINASC

Para reprodução, inicialmente, é necessário obter o conjunto de dados de interesse no SINASC. Neste trabalho, foi usado o ano de 2017 dentre os anos fornecidos pela Fundação Oswaldo Cruz (FIOCRUZ)[https://pcdas.icict.fiocruz.br/conjunto-de-dados/sistema-de-informacao-sobre-nascidos-vivos/] (acesso em junho de 2021). O endereço do arquivo utilizado deve ser inserido no lugar das funções db_ano(), para que se abra o arquivo obtido.

De todos os atributos presentes no banco de dados da FIOCRUZ, foram excluídos:
* Códigos, como de localidades, municípios, Estados, regiões administrativas, pacientes
* Nomes de municípios, pois o trabalho se limita ao escopo de Estados
* Coordenadas geográficas do nascimento e da residência da mãe
* área de municípios e regiões
* dados e metadados do registro de nascimento (data, hora, responsável pela declaração, CRM, etc)..

A explicação de todos os atributos encontra-se no [dicionário de dados relativo ao SINASC] (https://pcdas.icict.fiocruz.br/conjunto-de-dados/sistema-de-informacao-sobre-nascidos-vivos/dicionario-de-variaveis/). Os parâmetros excluídos encontram-se na lista prm_excl do notebook, primeira célula de código. Caso não se deseje uma reprodução exata do experimento, é possível alterar os parâmetros a serem considerados, alterando-se a lista. Pode ser necessário, porém, alterar outras partes do código. 

Os parâmetros utilizados estão descritos no início da exploração dos dados (caso desejado, referir-se ao dicionário de dados do SINASC para seu significado):
1.   def_loc_nasc 
2.   IDADEMAE             
3.   def_est_civil        
4.   ESCMAE               
5.   CODOCUPMAE           
6.   QTDFILMORT           
7.   def_gestacao          
8.   def_gravidez          
9.   def_parto             
10.   def_consultas         
11.   data_nasc             
12.   ano_nasc               
13.   dia_semana_nasc       
14.   HORANASC             
15.   def_sexo              
16.   APGAR1               
17.   APGAR5               
18.   def_raca_cor          
19.   PESO                 
20.   def_anomalia          
21.   CODANOMAL             
22.   RACACORMAE           
23.   QTDGESTANT           
24.   QTDPARTNOR           
25.   QTDPARTCES           
26.   IDADEPAI             
27.   MESPRENAT            
28.   TPAPRESENT           
29.   STTRABPART           
30.   STCESPARTO           
31.   TPNASCASSI           
32.   STDNEPIDEM           
33.   CODPAISRES           
34.   TPROBSON               
35.   nasc_AMAZONIA         
36.   nasc_FRONTEIRA        
37.   nasc_CAPITAL          
38.   res_AMAZONIA          
39.   res_FRONTEIRA         
40.   res_CAPITAL           
41.   nasc_SIGLA_UF         
42.   res_SIGLA_UF          
43.   nasc_REGIAO           
44.   res_REGIAO            
45.   codanomal_categoria   
46.   def_parto_prematuro   
