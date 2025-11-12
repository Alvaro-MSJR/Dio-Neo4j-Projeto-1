
<p align="center"><h2>Dio-Neo4j-Projeto-1  </h2></p>

<p align="center">
    <img width="80" src="assets/image/iniciorapido.jpg">   
    <img width="100" src="assets/image/Neo4j_ico.JPG">
</p>

<p align="center"><h1>BootCamp : Banco de Dados em Grafo Neo4J 
</h1></p>

# Projeto 1 :

 > **Objetivo:** Este repositório foi desenvolvido durante o BootCamp Banco de Dados em Grafo da NEO4J na plataforma da [DIO](https://dio.me)
 
 > **O Projeto** tem o objetivo de gerar evidência da entrega do desafio do projeto 1 e com isto gerar evidência do conhecimento absorvido no <b>treinamento do módulo:</b>

  ### Descrição do Projeto:  
  Modelagem de Dados em Grafos de um Serviço de Streaming

Para tal iremos demostrar :
   * Utilização do app:  https://arrows.app/  para fazer o desenho em grafo do modelo que iremos construir.


## 💻 Tecnologias utilizadas no projeto

- [Github] 
- [Visual Code Studio]
- [App Arrows.App]
- [Banco Neo4J]
- [Cypher]

##    Desciption

Entendendo o Desafio
Modele e crie um pequeno grafo de conhecimento para este serviço de streamer 😎

Como entregar esse projeto?

1. Crie um modelo;
1.1. Ele deve incluir:
   Entidades(Nós): 
     User;
     Movie;
     Series;
     Genre;
     Actor;
     Director.
   Conexões (Relacionamentos):
     WATCHED (com propriedade "rating") ;
     ACTED_IN ;
     DIRECTED ;
     IN_GENRE .

2. A entrega:

2.1. Um diagrama ou esboço d seu modelo de grafo.

2.2. Um script Cypher(.cypher) que cria constraints para os nós (ex: UNIQUE para IDs) e popula o banco com:
    mínimo de 10 usuários ;
    mínimo de 10 filmes/séries e seus respectivos relacionamentos.

3. Local da entrega:
   Criar um repositorio no github para suportar a entrega.
   Ao final, fazer um pequeno resumo do que foi feito
   Informar o link do repósitorio do gitbub onde foi feita a entrega.

 
## ✨ Solution

  1) Para este desafio iremos utilizar o arrows.app, para desenhar o modelo do banco de dados.
    Com este app, conseguimos ao final gerar tanto o esboço do diagrama quanto o script para ser implementado no banco.

  2) Criamos uma planilha que contem uma relação de filmes e os respctivos dados, esta planilha encontrasse no diretorio assets, neste diretorio temos todos os arquivos que usamos para produção deste projeto.

  3) Aqui apresentamos o esboço do projeto (imagem abaixo):

      <p align="center">
       <img width="400" src="/workspaces/Dio-Neo4j-Projeto-1/assets/image/Projeto_1_Arrows_App_Draft v1.png">
      </p>
<p>&emsp;&emsp;
Temos na figura, acima :</p>
<p>&emsp;&emsp;&emsp;&emsp;	17 filmes</p>
<p>&emsp;&emsp;&emsp;&emsp;	6 séries</p>
<p>&emsp;&emsp;&emsp;&emsp;	6 gêneros</p>
<p>&emsp;&emsp;&emsp;&emsp;	22 atores</p>
<p>&emsp;&emsp;&emsp;&emsp;	22 diretores</p>
<p>&emsp;&emsp;&emsp;&emsp;	21 usuários</p>
<p>&emsp;&emsp;&emsp;&emsp;	Nós = 115</p>
<p>&emsp;&emsp;&emsp;&emsp;	Relações = 92</p>


  4)  Agora vemos como ficou o modelo que foi desenhado no Arrows App, dentro do banco Neo4J. 

<p align="center">
 <img width="1000" src="/workspaces/Dio-Neo4j-Projeto-1/assets/image/visualisation_0.png"></p>

   5) Agora iremos ver uma imagem gerada pelo Neo4J, nesta imagem foi gerada após termos refatorado o script que foi gerado pelo Arrows.app

 <p align="center">
 <img width="1000" src="/workspaces/Dio-Neo4j-Projeto-1/assets/image/visualisation_Geral.png"></p>

        * Agora ver mais proximo o  grafo, com mais detalhes
<p align="center">
<img width="400" src="/workspaces/Dio-Neo4j-Projeto-1/assets/image/visualisation_1.png"></p>


    * Um pouco mais de detalhes
<p align="center">
           <img width="400" src="/workspaces/Dio-Neo4j-Projeto-1/assets/image/visualisation_Geral_com_foco.png"></p>

6) Script gerado no arrows.app.
<p align="left">

* CREATE (:Director {name: "Vince Gilligan"})-[:DIRECTED]->(n5:Series {title: "Breaking Bad"})<-[:ACTED_IN]-(:Actor {name: "Bryan Cranston"}),
(:User {name: "Ricardo Tavares"})-[:WATCHED {rating: 8}]->(n5)-[:IN_GENRE]->(:Genre {type: "Policial Investigativo"}),
(:Actor {name: "Sandra Bullock"})-[:ACTED_IN]->(n10:Movie {title: "Gravidade"})<-[:DIRECTED]-(:Director {name: "Alfonso Cuarón"}),
(:User {name: "Ricardo Tavares"})-[:WATCHED {rating: 8}]->(n14:Movie {title: "O Justiceiro"})-[:IN_GENRE]->(:Genre {type: "Ação"}),
(:Actor {name: "Jon Bernthal"})-[:ACTED_IN]->(n14)<-[:DIRECTED]-(:Director {name: "Steve Lightfoot"}),
(:User {name: "Sr. Carvalho"})-[:WATCHED {rating: 7}]->(n19:Movie {title: "2001: Uma Odisseia no Espaço"})<-[:ACTED_IN]-(:Actor {name: "Keir Dullea"}),
(:Director {name: "Stanley Kubrick"})-[:DIRECTED]->(n19)-[:IN_GENRE]->(:Genre {type: "Ficção Científica"}),
(:User {name: "Ricardo Tavares"})-[:WATCHED {rating: 9}]->(n10)-[:IN_GENRE]->(:Genre {type: "Ficção Científica"}),
(:Actor {name: "Malcolm McDowell"})-[:ACTED_IN]->(n26:Movie {title: "Laramja Mecânica"})<-[:DIRECTED]-(:Director {name: "Stanley Kubrick"}),
(:User {name: "Ana Silva"})-[:WATCHED {rating: 9}]->(n26)-[:IN_GENRE]->(:Genre {type: "Ficção Científica"}),
(:User {name: "João Mendes"})-[:WATCHED {rating: 8}]->(n32:Movie {title: "O Poderoso Chefão"})-[:IN_GENRE]->(:Genre {type: "Policial Investigativo"}),
(:Actor {name: "Al Pacino"})-[:ACTED_IN]->(n32)<-[:DIRECTED]-(:Director {name: "Francis Ford Coppola"}),
(:Actor {name: "Harrison Ford"})-[:ACTED_IN]->(n36:Movie {title: "Blade Runner: O Caçador de Androides"})<-[:DIRECTED]-(:Director {name: "Ridley Scott"}),
(:User {name: "Pedro Santos"})-[:WATCHED {rating: 9}]->(n36)-[:IN_GENRE]->(:Genre {type: "Ficção Científica"}),
(:Actor {name: "Harrison Ford"})-[:ACTED_IN]->(n41:Movie {title: "Os Caçadores da Arca Perdidar de Androides"})<-[:DIRECTED]-(:Director {name: "Steven Spielberg"}),
(:User {name: "Carla Lima"})-[:WATCHED {rating: 9}]->(n41)-[:IN_GENRE]->(:Genre {type: "Ação"}),
(:Actor {name: "Jim Caviezel"})-[:ACTED_IN]->(n46:Movie {title: "Cruzada"})<-[:DIRECTED]-(:Director {name: "Mel Gibson"}),
(:User {name: "Maria Oliveira"})-[:WATCHED {rating: 9}]->(n46)-[:IN_GENRE]->(:Genre {type: "Cristão"}),
(:Actor {name: "Gael García Bernal"})-[:ACTED_IN]->(n52:Movie {title: "Diários de Motocicleta"})<-[:DIRECTED]-(:Director {name: "Walter Salles"}),
(:User {name: "Paulo Rocha"})-[:WATCHED {rating: 9}]->(n52)-[:IN_GENRE]->(:Genre {type: "Documentário"}),
(:Actor {name: "Wagner Moura"})-[:ACTED_IN]->(n57:Movie {title: "Tropa de Elite"})<-[:DIRECTED]-(:Director {name: "José Padilha"}),
(:User {name: "Juliana Alves"})-[:WATCHED {rating: 9}]->(n57)-[:IN_GENRE]->(:Genre {type: "Policial Investigativo"}),
(:Actor {name: "Brad Pitt"})-[:ACTED_IN]->(n62:Movie {title: "O Curioso Caso de Benjamin Button"})<-[:DIRECTED]-(:Director {name: "David Fincher"}),
(:User {name: "Sofia Ribeiro"})-[:WATCHED {rating: 9}]->(n62)-[:IN_GENRE]->(:Genre {type: "Romance"}),
(:Actor {name: "Owen Wilson (voz)"})-[:ACTED_IN]->(n67:Movie {title: "Carros"})<-[:DIRECTED]-(:Director {name: "John Lasseter"}),
</p>

7) Script refatorado
Neste podemos ver que o modelo cria as dependencias para as relações de USER, DIRECTOR, GENRE.

* 

// LIMPAR O BANCO PRIMEIRO
MATCH (n) DETACH DELETE n;

// CRIAR GÊNEROS
CREATE 
(:Genre {type: "Ficção Científica"}),
(:Genre {type: "Policial Investigativo"}),
(:Genre {type: "Ação"}),
(:Genre {type: "Cristão"}),
(:Genre {type: "Documentário"}),
(:Genre {type: "Romance"});

// CRIAR DIRETORES
CREATE 
(:Director {name: "Vince Gilligan"}),
(:Director {name: "Alfonso Cuarón"}),
(:Director {name: "Steve Lightfoot"}),
(:Director {name: "Stanley Kubrick"}),
(:Director {name: "Francis Ford Coppola"}),
(:Director {name: "Ridley Scott"}),
(:Director {name: "Steven Spielberg"}),
(:Director {name: "Mel Gibson"}),
(:Director {name: "Walter Salles"}),
(:Director {name: "José Padilha"}),
(:Director {name: "David Fincher"}),
(:Director {name: "John Lasseter"}),
(:Director {name: "Denis Villeneuve"}),
(:Director {name: "Fernando Meirelles"}),
(:Director {name: "George Miller"}),
(:Director {name: "Dallas Jenkins"}),
(:Director {name: "Brannon Braga"}),
(:Director {name: "Charlie Brooker"}),
(:Director {name: "Craig Mazin"}),
(:Director {name: "Ronald D. Moore"}),
(:Director {name: "Martin Scorsese"}),
(:Director {name: "Joseph Kosinski"});

// CRIAR ATORES
CREATE 
(:Actor {name: "Bryan Cranston"}),
(:Actor {name: "Sandra Bullock"}),
(:Actor {name: "Jon Bernthal"}),
(:Actor {name: "Keir Dullea"}),
(:Actor {name: "Malcolm McDowell"}),
(:Actor {name: "Al Pacino"}),
(:Actor {name: "Harrison Ford"}),
(:Actor {name: "Jim Caviezel"}),
(:Actor {name: "Gael García Bernal"}),
(:Actor {name: "Wagner Moura"}),
(:Actor {name: "Brad Pitt"}),
(:Actor {name: "Owen Wilson"}),
(:Actor {name: "Amy Adams"}),
(:Actor {name: "Alexandre Rodrigues"}),
(:Actor {name: "Tom Hardy"}),
(:Actor {name: "Andrew Garfield"}),
(:Actor {name: "Jonathan Roumie"}),
(:Actor {name: "Neil deGrasse Tyson"}),
(:Actor {name: "Tom Cruise"}),
(:Actor {name: "Bryce Dallas Howard"}),
(:Actor {name: "Pedro Pascal"}),
(:Actor {name: "Caitríona Balfe"});

// CRIAR USUÁRIOS
CREATE 
(:User {name: "Ricardo Tavares"}),
(:User {name: "Sr. Carvalho"}),
(:User {name: "Ana Silva"}),
(:User {name: "João Mendes"}),
(:User {name: "Pedro Santos"}),
(:User {name: "Carla Lima"}),
(:User {name: "Maria Oliveira"}),
(:User {name: "Paulo Rocha"}),
(:User {name: "Juliana Alves"}),
(:User {name: "Sofia Ribeiro"}),
(:User {name: "Lucas Martins"}),
(:User {name: "Ana Carla Santos"}),
(:User {name: "Mendes"}),
(:User {name: "Santos"}),
(:User {name: "Oliveira"}),
(:User {name: "Maria Castro"}),
(:User {name: "Ribeiro"}),
(:User {name: "Rocha"}),
(:User {name: "Martins"}),
(:User {name: "Antônio João Mendes"}),
(:User {name: "Fernando Costa"});

// AGORA CRIAR FILMES, SÉRIES E RELACIONAMENTOS COM REFERÊNCIAS EXPLÍCITAS
// Breaking Bad
MATCH (d:Director {name: "Vince Gilligan"})
MATCH (a:Actor {name: "Bryan Cranston"})
MATCH (g:Genre {type: "Policial Investigativo"})
MATCH (u:User {name: "Ricardo Tavares"})
CREATE (bb:Series {title: "Breaking Bad"})
CREATE (d)-[:DIRECTED]->(bb)
CREATE (a)-[:ACTED_IN]->(bb)
CREATE (bb)-[:IN_GENRE]->(g)
CREATE (u)-[:WATCHED {rating: 8}]->(bb);

// Gravidade
MATCH (d:Director {name: "Alfonso Cuarón"})
MATCH (a:Actor {name: "Sandra Bullock"})
MATCH (g:Genre {type: "Ficção Científica"})
MATCH (u:User {name: "Ricardo Tavares"})
CREATE (m:Movie {title: "Gravidade"})
CREATE (d)-[:DIRECTED]->(m)
CREATE (a)-[:ACTED_IN]->(m)
CREATE (m)-[:IN_GENRE]->(g)
CREATE (u)-[:WATCHED {rating: 9}]->(m);

// O Justiceiro
MATCH (d:Director {name: "Steve Lightfoot"})
MATCH (a:Actor {name: "Jon Bernthal"})
MATCH (g:Genre {type: "Ação"})
MATCH (u:User {name: "Ricardo Tavares"})
CREATE (m:Movie {title: "O Justiceiro"})
CREATE (d)-[:DIRECTED]->(m)
CREATE (a)-[:ACTED_IN]->(m)
CREATE (m)-[:IN_GENRE]->(g)
CREATE (u)-[:WATCHED {rating: 8}]->(m);

// 2001: Uma Odisseia no Espaço
MATCH (d:Director {name: "Stanley Kubrick"})
MATCH (a:Actor {name: "Keir Dullea"})
MATCH (g:Genre {type: "Ficção Científica"})
MATCH (u:User {name: "Sr. Carvalho"})
CREATE (m:Movie {title: "2001: Uma Odisseia no Espaço"})
CREATE (d)-[:DIRECTED]->(m)
CREATE (a)-[:ACTED_IN]->(m)
CREATE (m)-[:IN_GENRE]->(g)
CREATE (u)-[:WATCHED {rating: 7}]->(m);

// Laranja Mecânica
MATCH (d:Director {name: "Stanley Kubrick"})
MATCH (a:Actor {name: "Malcolm McDowell"})
MATCH (g:Genre {type: "Ficção Científica"})
MATCH (u:User {name: "Ana Silva"})
CREATE (m:Movie {title: "Laranja Mecânica"})
CREATE (d)-[:DIRECTED]->(m)
CREATE (a)-[:ACTED_IN]->(m)
CREATE (m)-[:IN_GENRE]->(g)
CREATE (u)-[:WATCHED {rating: 9}]->(m);

// O Poderoso Chefão
MATCH (d:Director {name: "Francis Ford Coppola"})
MATCH (a:Actor {name: "Al Pacino"})
MATCH (g:Genre {type: "Policial Investigativo"})
MATCH (u:User {name: "João Mendes"})
CREATE (m:Movie {title: "O Poderoso Chefão"})
CREATE (d)-[:DIRECTED]->(m)
CREATE (a)-[:ACTED_IN]->(m)
CREATE (m)-[:IN_GENRE]->(g)
CREATE (u)-[:WATCHED {rating: 8}]->(m);

// Blade Runner
MATCH (d:Director {name: "Ridley Scott"})
MATCH (a:Actor {name: "Harrison Ford"})
MATCH (g:Genre {type: "Ficção Científica"})
MATCH (u:User {name: "Pedro Santos"})
CREATE (m:Movie {title: "Blade Runner: O Caçador de Androides"})
CREATE (d)-[:DIRECTED]->(m)
CREATE (a)-[:ACTED_IN]->(m)
CREATE (m)-[:IN_GENRE]->(g)
CREATE (u)-[:WATCHED {rating: 9}]->(m);

// Os Caçadores da Arca Perdida
MATCH (d:Director {name: "Steven Spielberg"})
MATCH (a:Actor {name: "Harrison Ford"})
MATCH (g:Genre {type: "Ação"})
MATCH (u:User {name: "Carla Lima"})
CREATE (m:Movie {title: "Os Caçadores da Arca Perdida"})
CREATE (d)-[:DIRECTED]->(m)
CREATE (a)-[:ACTED_IN]->(m)
CREATE (m)-[:IN_GENRE]->(g)
CREATE (u)-[:WATCHED {rating: 9}]->(m);

// Cruzada
MATCH (d:Director {name: "Mel Gibson"})
MATCH (a:Actor {name: "Jim Caviezel"})
MATCH (g:Genre {type: "Cristão"})
MATCH (u:User {name: "Maria Oliveira"})
CREATE (m:Movie {title: "Cruzada"})
CREATE (d)-[:DIRECTED]->(m)
CREATE (a)-[:ACTED_IN]->(m)
CREATE (m)-[:IN_GENRE]->(g)
CREATE (u)-[:WATCHED {rating: 9}]->(m);

// Diários de Motocicleta
MATCH (d:Director {name: "Walter Salles"})
MATCH (a:Actor {name: "Gael García Bernal"})
MATCH (g:Genre {type: "Documentário"})
MATCH (u:User {name: "Paulo Rocha"})
CREATE (m:Movie {title: "Diários de Motocicleta"})
CREATE (d)-[:DIRECTED]->(m)
CREATE (a)-[:ACTED_IN]->(m)
CREATE (m)-[:IN_GENRE]->(g)
CREATE (u)-[:WATCHED {rating: 9}]->(m);

// Tropa de Elite
MATCH (d:Director {name: "José Padilha"})
MATCH (a:Actor {name: "Wagner Moura"})
MATCH (g:Genre {type: "Policial Investigativo"})
MATCH (u:User {name: "Juliana Alves"})
CREATE (m:Movie {title: "Tropa de Elite"})
CREATE (d)-[:DIRECTED]->(m)
CREATE (a)-[:ACTED_IN]->(m)
CREATE (m)-[:IN_GENRE]->(g)
CREATE (u)-[:WATCHED {rating: 9}]->(m);

// Benjamin Button
MATCH (d:Director {name: "David Fincher"})
MATCH (a:Actor {name: "Brad Pitt"})
MATCH (g:Genre {type: "Romance"})
MATCH (u:User {name: "Sofia Ribeiro"})
CREATE (m:Movie {title: "O Curioso Caso de Benjamin Button"})
CREATE (d)-[:DIRECTED]->(m)
CREATE (a)-[:ACTED_IN]->(m)
CREATE (m)-[:IN_GENRE]->(g)
CREATE (u)-[:WATCHED {rating: 9}]->(m);

// Carros
MATCH (d:Director {name: "John Lasseter"})
MATCH (a:Actor {name: "Owen Wilson"})
MATCH (g:Genre {type: "Ação"})
MATCH (u:User {name: "Lucas Martins"})
CREATE (m:Movie {title: "Carros"})
CREATE (d)-[:DIRECTED]->(m)
CREATE (a)-[:ACTED_IN]->(m)
CREATE (m)-[:IN_GENRE]->(g)
CREATE (u)-[:WATCHED {rating: 9}]->(m);

// A Chegada
MATCH (d:Director {name: "Denis Villeneuve"})
MATCH (a:Actor {name: "Amy Adams"})
MATCH (g:Genre {type: "Ficção Científica"})
MATCH (u:User {name: "Ana Carla Santos"})
CREATE (m:Movie {title: "A Chegada"})
CREATE (d)-[:DIRECTED]->(m)
CREATE (a)-[:ACTED_IN]->(m)
CREATE (m)-[:IN_GENRE]->(g)
CREATE (u)-[:WATCHED {rating: 9}]->(m);

// Cidade de Deus
MATCH (d:Director {name: "Fernando Meirelles"})
MATCH (a:Actor {name: "Alexandre Rodrigues"})
MATCH (g:Genre {type: "Policial Investigativo"})
MATCH (u:User {name: "Mendes"})
CREATE (m:Movie {title: "Cidade de Deus"})
CREATE (d)-[:DIRECTED]->(m)
CREATE (a)-[:ACTED_IN]->(m)
CREATE (m)-[:IN_GENRE]->(g)
CREATE (u)-[:WATCHED {rating: 9}]->(m);

// Mad Max
MATCH (d:Director {name: "George Miller"})
MATCH (a:Actor {name: "Tom Hardy"})
MATCH (g:Genre {type: "Ação"})
MATCH (u:User {name: "Santos"})
CREATE (m:Movie {title: "Mad Max: Estrada da Fúria"})
CREATE (d)-[:DIRECTED]->(m)
CREATE (a)-[:ACTED_IN]->(m)
CREATE (m)-[:IN_GENRE]->(g)
CREATE (u)-[:WATCHED {rating: 9}]->(m);

// The Chosen (Série)
MATCH (d:Director {name: "Dallas Jenkins"})
MATCH (a:Actor {name: "Jonathan Roumie"})
MATCH (g:Genre {type: "Cristão"})
MATCH (u:User {name: "Maria Castro"})
CREATE (s:Series {title: "The Chosen"})
CREATE (d)-[:DIRECTED]->(s)
CREATE (a)-[:ACTED_IN]->(s)
CREATE (s)-[:IN_GENRE]->(g)
CREATE (u)-[:WATCHED {rating: 9}]->(s);

// Cosmos (Série)
MATCH (d:Director {name: "Brannon Braga"})
MATCH (a:Actor {name: "Neil deGrasse Tyson"})
MATCH (g:Genre {type: "Documentário"})
MATCH (u:User {name: "Ribeiro"})
CREATE (s:Series {title: "Cosmos: Uma Odisseia no Espaço-Tempo"})
CREATE (d)-[:DIRECTED]->(s)
CREATE (a)-[:ACTED_IN]->(s)
CREATE (s)-[:IN_GENRE]->(g)
CREATE (u)-[:WATCHED {rating: 9}]->(s);

// Black Mirror (Série)
MATCH (d:Director {name: "Charlie Brooker"})
MATCH (a:Actor {name: "Bryce Dallas Howard"})
MATCH (g:Genre {type: "Ficção Científica"})
MATCH (u:User {name: "Martins"})
CREATE (s:Series {title: "Black Mirror"})
CREATE (d)-[:DIRECTED]->(s)
CREATE (a)-[:ACTED_IN]->(s)
CREATE (s)-[:IN_GENRE]->(g)
CREATE (u)-[:WATCHED {rating: 9}]->(s);

// The Last of Us (Série)
MATCH (d:Director {name: "Craig Mazin"})
MATCH (a:Actor {name: "Pedro Pascal"})
MATCH (g:Genre {type: "Ação"})
MATCH (u:User {name: "Antônio João Mendes"})
CREATE (s:Series {title: "The Last of Us"})
CREATE (d)-[:DIRECTED]->(s)
CREATE (a)-[:ACTED_IN]->(s)
CREATE (s)-[:IN_GENRE]->(g)
CREATE (u)-[:WATCHED {rating: 9}]->(s);

// Outlander (Série)
MATCH (d:Director {name: "Ronald D. Moore"})
MATCH (a:Actor {name: "Caitríona Balfe"})
MATCH (g:Genre {type: "Romance"})
MATCH (u:User {name: "Fernando Costa"})
CREATE (s:Series {title: "Outlander"})
CREATE (d)-[:DIRECTED]->(s)
CREATE (a)-[:ACTED_IN]->(s)
CREATE (s)-[:IN_GENRE]->(g)
CREATE (u)-[:WATCHED {rating: 9}]->(s);


// O Silêncio (Filme)
MATCH (d:Director {name: "Martin Scorsese"})
MATCH (a:Actor {name: "Andrew Garfield"})
MATCH (g:Genre {type: "Cristão"})
MATCH (u:User {name: "Oliveira"})
CREATE (m:Movie {title: "O Silêncio"})
CREATE (d)-[:DIRECTED]->(m)
CREATE (a)-[:ACTED_IN]->(m)
CREATE (m)-[:IN_GENRE]->(g)
CREATE (u)-[:WATCHED {rating: 7}]->(m);

// Top Gun: Maverick (Filme)
MATCH (d:Director {name: "Joseph Kosinski"})
MATCH (a:Actor {name: "Tom Cruise"})
MATCH (g:Genre {type: "Ação"})
MATCH (u:User {name: "Rocha"})
CREATE (m:Movie {title: "Top Gun: Maverick"})
CREATE (d)-[:DIRECTED]->(m)
CREATE (a)-[:ACTED_IN]->(m)
CREATE (m)-[:IN_GENRE]->(g)
CREATE (u)-[:WATCHED {rating: 8}]->(m);

MATCH p=()-[]->() RETURN p LIMIT 450;


<h3>Conclusão:</h3>

	O script do Arrow App cria exatamente a estrutura do desenho feito no app, ou seja, temos redundâncias de entidades.

	Já o script refatorado cria a imagem que apresentamos acima, nesta imagem podemos ver que temos o produto cartesiano feito da relação de gênero x diretor e ainda de diretor x filme, logo temos um menor número de entidades.

	Acreditamos que para o trabalho em questão podemos observar as versões e aplicações dos 2 scripts.

<p><p align="left">
<img width="25" src="/workspaces/Dio-Neo4j-Projeto-1/assets/image/extra_icone.JPG"> EXTRAS
</p></p> 

### Arquivos compilados

* Aqui temos um arquivo do tipo word com todo o projeto.

<iframe src="/workspaces/Dio-Neo4j-Projeto-1/assets/BootCamp NEO4J_Projeto1_Alvaro.docx" width="400" height="400"></iframe>

// code .. 

<iframe src="/workspaces/Dio-Neo4j-Projeto-1/assets/BootCamp NEO4J_Projeto1_Alvaro.docx" width="400" height="400" frameborder="1"></iframe>

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

