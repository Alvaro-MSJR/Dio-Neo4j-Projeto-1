<p align="center">
    <img width="250" src="assets/BootCamp NEO4J_Projeto1_Alvaro.docx">
</p>
<p align="left"><h1> # Dio-Neo4j-Projeto-1  </h1></p>
<p align="center"><h1>BootCamp : Banco de Dados em Grafo Neo4J </h1></p>


# Projeto 1 : Aqui temos um projeto inicial com o banco em grafos da NEO4J.



 > **Objetivo:** Este repositório foi desenvolvido durante o BootCamp Banco de Dados em Grafo da NEO4J na plataforma da [DIO](https://dio.me)


Projeto tem o objetivo de gerar evidência da entrega do desafio do projeto 1 e com isto gerar evidência do conhecimento absorvido no <b>treinamento do módulo:</b>

  ### Modelagem de Dados em Grafos de um Serviço de Streaming

Para tal iremos demostrar :
   * Utilização do app:  https://arrows.app/  para fazer o desenho em grafo do modelo que iremos construir.


## 💻 Tecnologias utilizadas no projeto

- [Github] 
- [Azure]

##    Desciption

Entendendo o Desafio
Agora é a sua hora de brilhar e construir um perfil de destaque na DIO! Explore todos os conceitos explorados até aqui e replique (ou melhore, porque não?) este projeto prático. Para isso, crie seu próprio repositório e aumente ainda mais seu portfólio de projetos no GitHub, o qual pode fazer toda diferença em suas entrevistas técnicas 😎

Como entregar esse projeto?
Chegou a hora de você construir um portfólio ainda mais rico e impressionar futuros recrutadores, para isso é sempre importante mostrar os resultados do seu esforço
e como você os obteve deixando claro o seu racional, para isso faça da seguinte maneira:

1. Crie um novo repositório no github com um nome a sua preferência
2. Crie um arquivo chamado readme.md;
3.    Deixe alguns prints ;
4.    Descreva o processo, alguns insights e possibilidades que você aprendeu durante o conteúdo;
5.    Após a IA analisar suas sentenças
6. Compartilhe conosco o link desse repositório através do botão 'entregar projeto'

 
## ✨ Solution

  1) Neste desafio navegamos de forma básica pela interface do Azure.
  2) Não usamos uma conta de estudande, usamos uma contra free por 30 dias.
  3) Iremos procurar seguir o desenho da arquitetura (imagem abaixo)
      <p align="center">
       <img width="400" src="asset/desenho_arquitetura.JPG">
      </p>
      <p>&emsp;&emsp;&emsp;&emsp;&nbsp;<b><h4>Não iremos implementar em sua integralidade, somente alguns recursos, visto que não temos também
      em sua integralidade a descrição de arqtuitetura e ainda não temos os recursos como banco de dados local instalado.</h4></b></p>

  4) Veremos os prints do passo a passo da Criação dos recursos, como:

        * Grupo de Recurso
            <p> &emsp; Dedicado ao projeto, que no caso ira demonstrar uma implementacao de arquitetura.</p>

            <p align="center">
            <img width="400" src="asset/01_Grupo_Recurso.JPG">
            </p>

        * Data Factory
            </p> &emsp;&nbsp;&nbsp; Contém os recursos de dados e outros que iremos manipular.
            È uma das fontes de entrada</p>

            <p align="center">
            <img width="400" src="asset/05_Azure_Factory.JPG">
            </p>

        * Events Hubs
           <p> &emsp;&nbsp;&nbsp;  Contém os recursos de dados e outros que iremos manipular.</p>
           <p> &emsp;&nbsp;&nbsp;  É uma das fontes de entrada</p>
           <p> &emsp;&nbsp;&nbsp;  Pontos de atenção e a parte de segurança e thruput </li></p>

            <p align="center">
            <img width="400" src="asset/03_Event_hubs.JPG">
            </p>

        * Azure Databrikcs Service
          <p> &emsp; Iremos manipular os dados e gerar novos ou apenas sanitizar os dados.</p>

            <p align="center">
            <img width="400" src="asset/02_Azure_DataBricks_Service.JPG">
            </p>

        * Data Lake Storage 
           <p> &emsp; Pontos importantes:</p>
           <p> &emsp;&nbsp;&nbsp; Saber o que será armazenado, pois no campo "primary service" seremos</p>
           <p> &emsp;&nbsp;&nbsp; questionados, com isto e importante ver o que o arquiteto realmente almeja para este recurso. Para este recurso iremos criar um ADLS</p>
            <p> &emsp;&nbsp;&nbsp;  Saber o comportamento da rede e um ponto importante, como ficará disponivel o Data Lake.</p>

        * Storage Account
           <p> &emsp; Apos a criação iremos configurar:</p>
            
            <p align="center">
            <img width="400" src="asset/06_Storage_Account.JPG">
            </p>

             <p>&emsp;&nbsp;&nbsp;  Controle de Acesso</p>
             <p>&emsp;&nbsp;&nbsp;&nbsp;&nbsp;  Quem tem acesso e a que e qual o nivel.</p>
            
             <p> &emsp;&nbsp;&nbsp; Containers ( Pastas) </p>
             <p> &emsp;&nbsp;&nbsp;&nbsp;&nbsp; Que irá descrever/informar o status dos dados armazenados. Exemplo bronze, prata, ouro. que segue a linha de um dado sem tratamento, semi tratado e tratado.</p>
            <p align="center">
            <img width="400" src="asset/06_Storage_Account_Containers.JPG">
            </p>
            
             <p> &emsp;&nbsp;&nbsp; Filas</p>
             <p> &emsp;&nbsp;&nbsp;&nbsp;&nbsp; Emfim a estrutura definida pela arquitetura.</p>

        * Azure Machine Learning
            <p> &emsp; Que ira processar os nossos dados de entrada de forma a gerar, seja insights
            ou informações relevantes.</p>

            <p align="center">
            <img width="400" src="asset/07_Azure_Machine_Learning.JPG">
            </p>

        * SQL Database
            <p> &emsp; Aqui vemos as principais caracteristicas da confiuração do SQL Database.</p>

            <p align="center">
            <img width="400" src="asset/08_SQL_Database.JPG">
            </p>

            <p align="center">
            <img width="400" src="asset/08_SQL_Database_properties.JPG">
            </p>

        <h3>Atenção:</h3>
        <p> &emsp;&nbsp; A nossa função e de configuração do ambiente com os dados que são fornecidos pela Arquitetura.</p>
        <p> &emsp;&nbsp; Nos como engenheiro de dados, iremos pegar a definição lógica da arquitetura e implementar no ambiente do Microsoft Azure.</p>
        <p> &emsp;&nbsp; Iremos usar um</p>
	  
  5) Vimos neste configuração de recursos, algumas definições e propriedades, tal qual definido no desenho técnico da arquitetura.
	 Pelos prints, podemos constatar a gama bem diversificada e robusta da solução e suas propriedades diversas por recursos.
	   
## 👨‍💻 Desenvolvedor

<p>
    <p>&nbsp&nbsp&nbspAlvaro Monteiro<br>
    &nbsp&nbsp&nbsp
    <a href="https://github.com/Alvaro-MSJR">
    GitHub</a>&nbsp;|&nbsp;
    <a href="www.linkedin.com/in/alvaro-monteiro-silva">LinkedIn</a>
&nbsp;|&nbsp;</p>
</p>
<br/><br/>
<p>

---
⌨️ conteúdo por [Alvaro Monteiro](https://github.com/Alvaro-MSJR)

