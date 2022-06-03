<p align="center">
  <img src="https://user-images.githubusercontent.com/76957963/171772753-2ec5e2b4-16a6-46ba-9d15-e2988bd5efc2.png">
</p>

<h1 align="center"> Teste 2 Transformação de dados IntuitiveCare - Backend </h1>

## Descrição do projeto 

Teste 2 Transformação de dados 

Neste teste o candidato deverá criar um código (em uma das linguagens mencionadas no fim desse e-mail) que execute as tarefas de código abaixo. Tarefas de código:

Todas as tarefas deste teste devem ser executadas em código nas linguagens Python ou Java

Tarefas de código:

Extrair do pdf do anexo I do teste 1 acima os dados da tabela Rol de Procedimentos e Eventos em Saúde (todas as páginas);
Salvar dados em uma tabela estruturada, em csv;
e Zipar o csv num arquivo "Teste_{seu_nome}.zip".

Bônus

Com a legenda no rodapé substituir os dados abreviados das colunas OD e AMB para as respectivas descrições.

![image](https://user-images.githubusercontent.com/76957963/171871936-97345a7c-1e0b-4847-a120-c69b28f1a803.png)

## :computer: Tecnologias e Ferramentas 

- `Python 3`

- `Jupyter notebook`

- `Git & Github`

## :hammer: Funcionalidades do projeto

- `Funcionalidade 1`: Obter planilha de dados do site gov.br

- `Funcionalidade 2`: Tratar os dados obtidos 

- `Funcionalidade 2a`: Salvar os dados como cvs e armazenar em uma pasta compactada ZIP

## 📚: Bibliotecas utilizada

- `os`
- `zipfile`
- `pandas`

#### Obtendo dados do site gov.br

    anexo_I_Rol_de_procedimentos = pd.read_excel('https://www.gov.br/ans/pt-br/arquivos/assuntos/consumidor/o-que-seu-plano-deve-cobrir/Anexo_I_Rol_2021RN_465.2021_RN473_RN478_RN480_RN513_RN536.xlsx', sheet_name='Anexo I_Rol de Procedimentos', skiprows=3)

#### Renomeando colunas

    anexo_I_Rol_de_procedimentos.columns = anexo_I_Rol_de_procedimentos.iloc[0]
    anexo_I_Rol_de_procedimentos.head()
    anexo_I_Rol_de_procedimentos.drop(anexo_I_Rol_de_procedimentos.index[0], inplace=True)
    anexo_I_Rol_de_procedimentos

#### Bônus(renomeando colunas OD e AMB)

![image](https://user-images.githubusercontent.com/76957963/171871936-97345a7c-1e0b-4847-a120-c69b28f1a803.png)
    
    anexo_I_Rol_de_procedimentos.rename(columns={'OD': 'Seg.Odontológico', 'AMB': 'Seg.Ambulatorial'})

#### Obtendo o sumario de normas
    
    sumario_de_normas = pd.read_excel('https://www.gov.br/ans/pt-br/arquivos/assuntos/consumidor/o-que-seu-plano-deve-cobrir/Anexo_I_Rol_2021RN_465.2021_RN473_RN478_RN480_RN513_RN536.xlsx', sheet_name='Sumário de Normas')
    sumario_de_normas.head()

#### Realizando o tratamento de dados e obtendos as colunas e linhas necessárias da folha do sumário de normas
    
    sumario_de_normas = pd.read_excel('https://www.gov.br/ans/pt-br/arquivos/assuntos/consumidor/o-que-seu-plano-deve-cobrir/Anexo_I_Rol_2021RN_465.2021_RN473_RN478_RN480_RN513_RN536.xlsx', sheet_name='Sumário de Normas', usecols=[7,9,10], skiprows=1)
        sumario_de_normas
    
#### Salvando os dados em um arquivo csv

    anexo_I_Rol_de_procedimentos.to_csv('Rol_de_procedimentos.csv')

#### Zipando o arquivo salvo 
    
    with ZipFile('Teste_{vinicius_gonzaga}.zip', 'w') as file_zip:
    file_zip.write('Rol_de_procedimentos.csv')
    
## Autor

[<img src="https://user-images.githubusercontent.com/76957963/171774831-f51b4f04-1beb-498a-b7ab-a47a7af1d382.jpeg" width=115><br><sub>Vinícius Rodrigues</sub>](https://github.com/ViniciusRodrigues10)
