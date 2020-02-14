# Abstartups - Backend Challenge

Olá, este é o desafio Abstartups para a vaga de Backend Node.JS, pedimos sua atenção, os detalhes fazem toda a diferença.

O prazo para **conclusão do teste é de 7 dias corridos** contados a partir do recebimento do e-mail, sinta-se a vontade para escolher as tecnologias que deseja utilizar.

**A única questão imprescindível é que seja feito em Node.JS.**

# O Desafio

Seu desfio consiste no desenvolvimento de uma API de usuários, ela deve permitir: Encontrar um usuário pelo UUID e Listar os usuários existentes.

Em **nenhuma hipótese** sua API deve retornar os campos: `birthday`, `email`, `address`, `telephone` e `cellphone`.

O design da API e forma de consumo ficam a seu critério. Não não esqueça que ela será consumida por um `client`, por isso deve ser exposta utilizando o protocolo HTTP.

Os usuários para implementação estão neste repositório no arquivo `peoples.json`, não existem campos com valores nulos e estão como mostrado baixo.

    [
	    ...
	    {
		    "full_name": "Sérgio Oliver Novaes",
		    "birthday": "23/07/1955",
		    "zodiac_sign": "Leão",
		    "email": "sergioolivernovaes-86@piemme.com.br",
		    "zip_code": "68020-598",
		    "street": "Avenida Portugal",
		    "street_number": 253,
		    "neighborhood": "Diamantino",
		    "city": "Santarém",
		    "state": "PA",
		    "telephone": "(93) 2605-1763",
		    "cellphone": "(93) 99753-0686",
		    "height": "1,79",
		    "weight": 53,
		    "blood_type": "B+",
		    "favorite_color": "amarelo"
	    }
	    ...
    ]

   

Sua API deve ler os dados desse arquivo e formatá-los para o padrão indicado.

Essa importação e padronização deve ser realizada antes da sua API estar `ready`, ou seja, deve realizar no `bootstrap` da sua aplicação sem modificar o arquivo original.

**Todos os dados devem ser mantidos em memória, sem uso de qualquer mecanismo de persistência.**

Modificações necessárias:
- Todos os dados de endereço em uma propriedade `address`.
- Adiciona o campo `id` com UUID versão 4 distinto para cada usuário.
- Transformar o campo `height` em `float` (ex: "1,54"  ficará 1.54).
- Partindo do princípio que todos os usuários são brasileiros, adicione ao campo `address` um novo campo chamado `country` e adicione como valor padrão Brasil.
- Remover espaços e qualquer carácter especial dos campos `telephone` e `cellphone` e adicionar o prefixo do país (+55).

[Leia mais sobre UUID na Wikipedia](https://en.wikipedia.org/wiki/Universally_unique_identifier)

### Padrão

Após sua transformação, o resultado deverá estar no padrão o abaixo.


    [
	    ...
	    {
		    "id": "",
			"full_name": "Sérgio Oliver Novaes",
			"birthday": "23/07/1955",
			"zodiac_sign": "Leão",
			"email": "sergioolivernovaes-86@piemme.com.br",
			"telephone": "+559326051763",
			"cellphone": "+5593997530686",
			"height": 1.79,
			"weight": 53,
			"blood_type": "B+",
			"favorite_color": "amarelo",
			"address": {
				"zip_code": "68020-598",
				"street": "Avenida Portugal",
				"street_number": 253,
				"neighborhood": "Diamantino",
				"city": "Santarém",
				"state": "PA",
				"country": "Brasil"
			}
		}
		...
	]

### Páginação

Na listagem de usuários, você **deve implementar paginação** e deve **retornar os resultados no seguinte padrão**:

    {
	    page: number, // Página atual
	    pageSize: number, // Total de páginas
	    totalCount: number, // Total de usuários
	    users: [
		    // Usuários
	    ]
    }
### Tratamento de Erros

Não precisa implementar o que há de mais moderno em design e tratamento de erros, mas faça algo a respeito. Lembre-se:

> O usuário nem sempre sabe exatamente o que quer ou não entende como deve consumir sua API.

Pense em como sua API deve se comportar ao buscar por um UUID ou página que não existe.

## Como deve ser desenvolvido

Para o desenvolvimento do desafio, você deve antes de mais nada, criar um **repositório privado** no [GitHub](https://github.com/), [GitLab](https://about.gitlab.com/) ou [Bitbucket](https://bitbucket.org/product/).

Inicie o projeto com um *commit* e mantenha a prática de *commits* consistentes até a conclusão do projeto.

**Considerações Importantes**

Mantenha seus *commits* **em português** e sinta-se a vontade para escrever suas mensagens, com isso queremos entender sua linha de raciocínio e prática de versionamento.

## O que será avaliado

 - Qualidade de código
 - Resolução do problema proposto
 - Raciocínio desenvolvido
 - Documentação - Escreve um bom README para que possamos executar seu código do modo adequado

## Como deverá ser entregue

Ao finalizar o desafio insira o usuário correspondente no repositório privado (para que possamos analisar seu código) e **responda o e-mail do desafio com o link do seu repositório**.

 - GitHub - **@abstartups-oficial**
 - GitLab - **@abstartups-oficial**
 - Bitbucket - **@abstartups-oficial**
