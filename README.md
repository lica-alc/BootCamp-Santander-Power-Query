<h1 align="center">:file_cabinet: Desafio PowerQuery Bootcamp</h1>

## :memo: Descrição
Nesse projeto foi solicitado um passo a passo de manutenção(transformação) que deveria ser feito em um banco de dados fornecidos pela Dio.me

## 📖 Criação do banco de dados, hospedagem e integração com o power bi
* Foi necessário a criação de uma instância no Azure para MySQL.

 <img src="https://github.com/lica-alc/BootCamp-Santander-Power-Query/blob/main/Imagens/Azure.png" width="400" />

 * No Azure só criei a instância achei melhor criar o banco e tabelas no Workbend.

   <img src="https://github.com/lica-alc/BootCamp-Santander-Power-Query/blob/main/Imagens/workebend.png" width="400" />

* Na integração do Power Bi não consegui configurar direto no mysql, então criei no fontes de dados odbc na minha maquina e utilizei no power bi.
 
## 💻 Transformação dos Dados
* Foi feito todo os passos que foram solicitados (modificação de tipo de dados, analisar campos nulos, etc...), será citados alguns:
  
  **Separar colunas complexas** - Foi separado o campo endereço da tabela employee. Nele tinha um campo com endereço completo com rua, numero, cidade e estado, então foi divida em 4.

  
 <img src="https://github.com/lica-alc/BootCamp-Santander-Power-Query/blob/main/Imagens/Endereco.png" width="400" />

  **Mescle as colunas de Nome e Sobrenme para ter apenas uma coluna** - com a tabela employee selecionada cliquei no menu Adicionar Coluna \ Colunas personalizadas e dentro do campo formula de coluna personalizada digitei o comando: [Fname] & " " & [Lname]. Fiz manutenção nos cabeçalhos e exclui a coluna antiga.

 <img src="https://github.com/lica-alc/BootCamp-Santander-Power-Query/blob/main/Imagens/mescla.png" width="400" />

  **Mesclar consultas employee e dapartament** - Cliquei  na guia Pagina Inicial \ Combinar \ Mesclar Consultas\Mesclar Consultas como novas - Então criei a consulta ColaboradorXDepartamento.

  <img src="https://github.com/lica-alc/BootCamp-Santander-Power-Query/blob/main/Imagens/colaborador-departamento.png" width="400" />

  **Mesclar e trazer a junção do nome dos colaboradores e respectivos nomes dos gerentes** - Utilizei o mesmo menu acima porém utilizei duas vezes a tabela employee utilizando os campos ssn e super_ssn. Foi criado a nova consulta GerenteXColaborador.

  <img src="https://github.com/lica-alc/BootCamp-Santander-Power-Query/blob/main/Imagens/colaborador-gerente.png" width="400" />

  **Mesclar os nomes de departamentos e localização** - Utilizei o mesmo menu acima, mas com as tabelas departament e dept_locations. Foi criada a consulta localizacaoXdepartamento.

 <img src="https://github.com/lica-alc/BootCamp-Santander-Power-Query/blob/main/Imagens/dep-local.png" width="400" />

  **Agrupar os dados a fim de saber quantos colaboradores existem por gerente** - Utiliziei a consulta GerenteXColaborador e agrupei por gerente. Menu utilizado: Pagina Inicial \ Agrupar por.

  <img src="https://github.com/lica-alc/BootCamp-Santander-Power-Query/blob/main/Imagens/gerente-ncol.png" width="400" />

  **Depois de toda a manutenção limpei campos desnessários em todas as tabelas.**


## ⁉️ Diferença entre mesclar e atribuir no power query
* Mesclar - Serve para fazer combinações entre duas ou mais tabelas, onde é necessário um campo em comum entre as tabelas. Exemplo trazer o nome do funcionario com o nome do departamento em que trabalha.

* Atribuir - Serve para empilhar dados de varias tabelas em uma só. Exemplo: trazer todas as vendas do primeiro trimestre na mesma tabela.

  Ambas funções são importantes para a transformação de dados e deve ser usada de acordo com a sua necessidade.
  

## :wrench: Relatório no power bi
Feito um relatório simples, afim de trazer visualização dos dados que foi trabalhado. Optei por fazer uma gestão dos projetos. Pois no banco de dados exisitia originalmente 5 tabelas: **funcionários, departamento, localização de departamento, projetos, e trabalhos.**
Na tabela funcionários contém informações cadastrais de funcionarios, na departamentos contém sobre o departamento, localização o nome já fiz, projetos contém nome do projeto e departamento responsável, na de trabalho contém identificação de projeto, funcionario e horas utilizadas.

No relatório coloquei **cartões** informando maior salário, menor salário, quantidade de funcionarios feminino, quantidade de funcionários masculinos e total de horas utilizadas em todos os projetos. Para fazer os cartões femininos e masculinos utilizei medida com dax, mesmo não sendo abordado no curso.

Utilizei 4 **graficos, pizza, barras, colunas e treemap**. Cada um com seu respectivo assunto: projeto por localização, quantidade de projetos por funcionários, soma de horas por departamento e contagem  de projetos por departamentos.

<img src="https://github.com/lica-alc/BootCamp-Santander-Power-Query/blob/main/Imagens/Relat%C3%B3rio.png" width="400" />

**Ps: Projeto no power bi em anexo**



## :handshake: Colaboradores
<table>
  <tr>
    <td align="center">
      <a href="http://github.com/lica-alc">
        <sub>
          <b>Liliane</b>
        </sub>
      </a>
    </td>
  </tr>
</table>

## :dart: Status do projeto
* Em andamento
