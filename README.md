## Tabelas ##
- Onde as informações ficam guardadas 
- Nela contém os campos e as informações

    -- Campos => colunas
    -- Informações => linhas, é o que alimenta cada campo

- Nomes das tabelas: 
    -- DEVEM começar por uma letra 
    -- NÃO podem conter os seguintes caracteres: () + - / * " ; = & | # < > ^ ' { } % 
    -- NÃO pode conter espaço 
    -- NÃO pode conter acentuação

## Tipos de campos ##

- Textos => text
- Numeros => number 
- Data e hora => datatime
- chave primaria => primary key // a chave primária é considerada uma informação única entre todos os campos 


# COMANDOS SQL #

## SELECT ##
    - vai selecionar alguma coisa

    - SELECT * FROM nomeTabela // * é para selecionar TODA tabela
    
    - SELECT nomeCampo1, nomeCampo2 FROM nomeTabela // seleciona somente os campos especificados da tabela indicada
   
    - SELECT * FROM nomeTabela WHERE nomeCampo = oQueQuerBuscar // o where serve para buscar as informações onde vai estar escrito o que quero

    - SELECT * FROM nomeTabela WHERE nomeCampo like 'j%' // neste exemplo, o comando vai buscar todas as informações em que o nomeCampo da tabela nomeTabela começa com j. Quando o campo é texto coloca entre ' '. O % diz que o restante após o j é indiferente. 

## Operadores aritméticos ##

    - Igual ( = ) => serve para relacionar alguma coisa ex.: nomeCampo = 124135, isso ele vai pegar a informação do campo que está com este número. O igual busca informações do tipo números

    - Like ( like ) => é a mesma coisa que o igual, porém o like serve para buscar informações do tipo texto. E a informação tipo texto tem que estar entre aspas ' '. 

    - Maior ( > ) => serve para relacionar alguma coisa maior ex.: nomeCampo > 3, isso ele vai pegar as informação do campo que está maior que este número. O maior busca informações do tipo números

    - Menor ( < ) => serve para relacionar alguma coisa menor ex.: nomeCampo < 3, isso ele vai pegar as informação do campo que está menor que este número. O menor busca informações do tipo números

    - Maior ou igual ( >= ) => serve para relacionar alguma coisa maior ou igual ex.: nomeCampo >= 3, isso ele vai pegar as informação do campo que está maior ou igual que este número. O maior ou igual busca informações do tipo números

    - Menor ou igual ( <= ) => serve para relacionar alguma coisa menor ou igual ex.: nomeCampo <= 3, isso ele vai pegar as informação do campo que está menor ou igual que este número. O menor ou igual busca informações do tipo números

    - Não igual a ( <> ) => serve para relacionar alguma coisa  não igual a ex.: nomeCampo <> 3, isso ele vai pegar as informação do campo que não são iguais que este número. Pode ser numero ou texto

    - Diferente de ( != ) => serve para relacionar alguma coisa  diferente de ex.: nomeCampo != 3, isso ele vai pegar as informação do campo que são diferentes a este número. Pode ser número ou texto

    - Adição ( + ) => serve para relacionar alguma coisa em que se possa fazer uma soma ex.: nomeCampo = 1 + 1, isso ele vai pegar as informação do campo 2, porque é a soma de 1 + 1. Pega somente informações do tipo número.

    - Subtração ( - ) => serve para relacionar alguma coisa em que se possa fazer uma subtração ex.: nomeCampo = 2 - 1, isso ele vai pegar as informação do campo 1, porque é a subtração de 2 - 1. Pega somente informações do tipo número.

    - Multiplicação ( * ) => serve para relacionar alguma coisa em que se possa fazer uma multiplicação ex.: nomeCampo = 2 * 1, isso ele vai pegar as informação do campo 2, porque é a multiplicação de 2 * 1. Pega somente informações do tipo número.

    - Divisão ( / ) => serve para relacionar alguma coisa em que se possa fazer uma divisão ex.: nomeCampo = 4 / 2, isso ele vai pegar as informação do campo 2, porque é a divisão de 4 / 2. Pega somente informações do tipo número.

    - Módulo = resto da divisão ( % ) => serve para relacionar alguma coisa em que se possa fazer um módulo ex.: nomeCampo = 5 % 2, isso ele vai pegar as informação do campo 1, porque é o resto de 5 % 2. Pega somente informações do tipo número.

## Operadores lógicos ##

    - AND => o operador E serve para juntar duas condições
    
    - OR => o operador OU serve para pegar uma condição ou outra
    
    - BETWEEN => o operador ENTRE serve para pegar uma condição entre a outra ex.: WHERE nomeCampo BETWEEN entre1 and entre2 

    - NOT BETWEEN => o operador NÂO ENTRE serve para ignorar uma condição entre a outra ex.: WHERE nomeCampo NOT BETWEEN entre1 and entre2 

    - IN => o operador CONTÉM serve para pegar uma condição que contenha tal informação ex.: WHERE nomeCampo IN (1, 3, 5) pegara as informações que contem os numeros 1, 3 e 5 do campo nomeCampo 

    - NOT IN => o operador CONTÉM serve para pegar uma condição que NÂO contenha tal informação ex.: WHERE nomeCampo NOT IN (1, 3, 5) pegara as informações que não contem os numeros 1, 3 e 5 do campo nomeCampo

    - IS NULL => o operador É NULO serve para pegar uma condição que no campo está nulo ex.: WHERE nomeCampo IS NULL
    
    - IS NOT NULL => o operador NÃO É NULO serve para pegar tudo que não está nulo no campo ex.: WHERE nomeCampo IS NOT NULL
    
## INSERT INTO ##

    - o comando INSERT serve para inserir dados e informações na tabela
    
    - INSERT INTO nomeTabela (campo1, campo2, campo3) VALUES ('text', number, 'text')

## UPDATE ##

    - o comando UPDATE serve para alterar algum valor de dado já inserido na tabela

    - UPDATE nomeTabela SET nomeCampo1='novo dado', nomeCampo2='novo dado' WHERE nomeCampo = linhaASerAlterada

    - pode alterar todos os campos ou somente os necessários

    - lembrar sempre de passar o WHERE, pq se não passar ele vai alterar os dados do campo em toda a tabela

## DELETE ##

    - o comando DELETE permite apagar informações, podendo ser algum dado no campo ou a tabela inteira. MUITO CUIDADO

    - se não colocar o WHERE pode apagar a tabela toda

    - DELETE FROM nomeTabela WHERE nomeCampo=identidadeCampo

## FOREIGN KEY - Chave estrangeira ##

    - É quem faz a relação de uma tabela com a outra
    - PRIMARY KEY jamais pode se repetir em uma tabela
    - FOREIGN KEY pode se repetir na tabela

## UNIQUE ##

    - Quando um campo é único, não pode se repetir

## JOIN ##
    - "Juntar"
    - Conteúdo de duas tabelas que possuem um relacionamento

## JOIN ... WHERE ##
    - Juntar duas tabelas em que elas possuam um relacionamento, porem com o where ele seleciona o que está relacionado
    - Ex.: 
        SELECT * FROM funcionarios
        JOIN departamentos
        ON funcionarios.id_departamento = departamentos.id_dept
        WHERE funcionarios.id_departamento = 1

## Alias ##
    - serve para fazer mudanças usando o 'as' no código
    - Ex.: 
        SELECT func.nome as "Nome", func.cpf as "CPF", dept.id_dept as "Código do departamento", dept.descricao as "Setor"
        FROM funcionarios as func 
        JOIN departamentos as dept
        ON func.id_departamento = dept.id_dept

## LEFT OUTER JOIN ##
    - Mostra todo o conteúdo de uma tabela, mesmo que não tenha relação com a outra. 
    - É left pq prioriza a tabela a esquerda do FROM.
    Ex.:    
        SELECT *
        FROM funcionarios
        LEFT OUTER JOIN departamentos
        ON funcionarios.id_departamento = departamentos.id_dept


## ORDER BY ##
    - Organização alfabética crescente por padrão
    - Organização numérica crescente por padrão
    Ex.: 
        SELECT * FROM funcionarios
        ORDER BY id_departamento // crescente
        
        SELECT * FROM funcionarios
        ORDER BY id_departamento DESC // decrescente

## LIMIT ##
    - Mostra somente a quantidade de campos especificadas no limit. é equivalente ao top do Microsoft SQL server
    Ex.: 
        SELECT * FROM funcionarios LIMIT 2

## OFFSET ##
    - Ignora os primeiros resultados que encontrar de acordo com a numeração desejada. 
    Ex.: 
        SELECT * FROM funcionarios LIMIT 4 OFFSET 3

## COUNT ##
    - conta quantos registros, válidos, tem 
    Ex.: 
         SELECT COUNT(nome) FROM funcionarios  

## GROUP BY ##
    - serve para agrupar os elementos em análise
    Ex.: 
        SELECT id_departamento, COUNT(id_departamento) 
        FROM funcionarios 
        GROUP BY id_departamento
 
 ## JOIN, GROUP BY e COUNT juntos ##
    Ex.:
        SELECT departamentos.descricao, COUNT(id_departamento)
        FROM funcionarios
        JOIN departamentos
        ON funcionarios.id_departamento = departamentos.id_dept
        GROUP BY departamentos.id_dept

## HAVING ##
    - Faz uma comparação com agrupamentos 
    Ex.:
        SELECT departamentos.descricao, count(funcionarios.id_departamento)
        FROM funcionarios
        JOIN departamentos
        ON funcionarios.id_departamento = departamentos.id_dept
        GROUP BY departamentos.id_dept
        HAVING count(funcionarios.id_departamento) >= 2

## CREATE TABLE ##
    - Criação de uma nova tabela
    Ex.: 
    CREATE TABLE alunos (
	    matricula INTEGER PRIMARY KEY AUTOINCREMENT,
        nome TEXT,
        cpf INTEGER UNIQUE, 
        responsavel TEXT	
    )

    CREATE TABLE aulas (
	    d_professor INTEGER,
        matricula INTEGER,
        FOREIGN KEY(id_professor) REFERENCES professores(id_professor),
        FOREIGN KEY(matricula) REFERENCES alunos(matricula)
    )

## ALTER TABLE ##
    - Altera uma tabela já existente
    Ex.:
        ALTER TABLE aluno RENAME TO alunos

        ALTER TABLE alunos RENAME COLUMN matricula TO matricula_aluno

## DROP TABLE ##
    - Deleta uma tabela
    Ex.: 
        DROP TABLE aulas







SELECT SRA010.RA_CODFUNC, SRJ010.RJ_FUNCAO, SRA010.RA_NOME, SRJ010.RJ_DESC 
FROM SRA010 
JOIN SRJ010 
ON SRA010.RA_CODFUNC = SRJ010.RJ_FUNCAO 


WHERE SRA010.D_E_L_E_T_ <> '*' and 
SRA010.RA_ADMISSA >= '20230801'



SELECT 
'ADMISSAO' AS TIPO,  
SRA010.RA_CODFUNC,
SRJ010.RJ_FUNCAO, 
SRA010.RA_NOME, 
SRJ010.RJ_DESC, 
SRA010.RA_ADMISSA AS DATA

FROM SRA010 
JOIN SRJ010 
ON SRA010.RA_CODFUNC = SRJ010.RJ_FUNCAO 


WHERE SRA010.D_E_L_E_T_ <> '*' and 
SRA010.RA_ADMISSA >= '20230101'


-- WHERE SRA010.RA_CODFUNC = SRJ010.RJ_FUNCAO

--RA_NOME, RA_CODFUNC 

--SELECT RJ_FUNCAO, RJ_DESC FROM SRJ010

--SELECT * FROM funcionarios
--        JOIN departamentos
--        ON funcionarios.id_departamento = departamentos.id_dept
--        WHERE funcionarios.id_departame



## ---------------------------- GREAT --------------------------------- ##

SELECT	SR7010.R7_DATA, 
		SR7010.R7_MAT, 
		SRA010.RA_MAT, 
		SRA010.RA_NOME, 
		SR7010.R7_FUNCAO, 
		SRA010.RA_CODFUNC, 
		SRA010.RA_CARGO, 
		SRJ010.RJ_FUNCAO, 
		SRJ010.RJ_DESC, 
		SR7010.R7_DESCFUN,
		SR7010.R7_CARGO, 
		SRA010.RA_ADMISSA, 
		SRA010.RA_DEMISSA, 
		SRA010.RA_SITFOLH AS FERIAS
FROM SR7010
INNER JOIN SRA010
ON SRA010.RA_CODFUNC = SR7010.R7_FUNCAO AND SR7010.R7_MAT = SRA010.RA_MAT
INNER JOIN SRJ010
ON SRA010.RA_CODFUNC = SRJ010.RJ_FUNCAO

--WHERE SR7010.R7_FUNCAO = 00072 AND SR7010.R7_MAT = 000178

--SELECT RJ_FUNCAO, RJ_DESC FROM SRJ010


--SELECT SRA010.RA_CODFUNC, SRJ010.RJ_FUNCAO, SRA010.RA_NOME, SRJ010.RJ_DESC 
--FROM SRA010 
--JOIN SRJ010 
--ON SRA010.RA_CODFUNC = SRJ010.RJ_FUNCAO 

--SELECT 
--'ADMISSAO' AS TIPO,  
--SRA010.RA_CODFUNC,
--SRJ010.RJ_FUNCAO, 
--SRA010.RA_NOME, 
--SRJ010.RJ_DESC, 
--SRA010.RA_ADMISSA AS DATA
--FROM SRA010 
--JOIN SRJ010 
--ON SRA010.RA_CODFUNC = SRJ010.RJ_FUNCAO 
--WHERE SRA010.D_E_L_E_T_ <> '*' and 
--SRA010.RA_ADMISSA >= '20230101'



## ---------------------------- NÂO TEM EM DETERMINADA DATA --------------------------------- ##

SELECT 
	c.empresa_id, 
	(CASE 
		WHEN g.empresa_id = 1 THEN 'PROLUMINAS VARGINHA' 
        WHEN g.empresa_id = 3 THEN 'PROLUMINAS SENADOR CANEDO' 
        WHEN g.empresa_id = 4 THEN 'PROLUMINAS OSASCO' 
        WHEN g.empresa_id = 5 THEN 'PROLUMINAS COLOMBO' 
        WHEN g.empresa_id = 6 THEN 'PROLUMINAS DUQUE DE CAXIAS' 
        WHEN g.empresa_id = 7 THEN 'PROLUMINAS BETIM' 
        WHEN g.empresa_id = 8 THEN 'PROLUMINAS JARDINÓPOLIS' 
        ELSE '' 
	END) AS base_coletora,
    g.id AS gerador_id,
    g.razao_social AS razao_social,
    g.nome_fantasia AS nome_fantasia,
    g.cep,
	g.logradouro AS endereco,
	g.numero,
	g.bairro,
	g.cidade,
	g.estado,
	g.telefone,
	g.celular,
    c.numero AS CCO,
    c.coletor_id,
	(CASE WHEN proluminas.coletor.nome <> '' THEN proluminas.coletor.nome ELSE proluminas.coletor.razao_social END) AS coletor,
    c.volume_coletado,
	c.valor_pago,
    MAX(c.data_coleta) AS data_ultima_coleta
FROM 
    proluminas.gerador g
INNER JOIN 
    proluminas.certificado c ON c.gerador_id = g.id
LEFT JOIN 
	proluminas.coletor ON c.coletor_id = proluminas.coletor.id
WHERE 
    g.id NOT IN (
        SELECT 
            gerador_id 
        FROM 
            proluminas.certificado
        WHERE 
            data_coleta >= '2023-01-01' AND 
            data_coleta <= '2023-11-30'
    )
GROUP BY 
    g.id;

