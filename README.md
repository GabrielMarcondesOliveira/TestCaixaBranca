# TestCaixaBranca
Como descreve a etapa 1 do exercício de Teste de Caixa Branca, os erros encontrados dentro do código são:

- O uso da classe "Class.forName("com.mysql.Driver").newInstance()" não é utilizado, e considerado desnecessário, pois nas versões mais atuais do java basta apenas utilizar a classe "Class.forName" que já estará fazendo a mesma função que a primeira sintaxe;

- Consequentemente, se deixar os blocos de "catch" vazio significa que, caso haja falhas, o sistema não terá retorno de mensagem úteis para a depuração do código (processo de identificar problemas, corrigir erros ou bugs dentro do código fonte do software);

- Concatenar valores diretamente na query SQL "sql += "where login = '" + login + "'";", deixa o sistema vulnerável a ataques de SQL Injection. Tendo em vista que uma falha dessa permita que algum tipo de invasor utilize comandos maliciosas dentro do banco de dados;

- Recursos como Connection, Statement e ResultSet necessitam ser fechados após sua inserção. para assim evitar vazamentos de recursos;

- O método utilizado "conectarBD" pode retornar um valor "null" caso a conexão falhar, pois isso não foi tratado dentro da programação no método "verificarUsuário";

- Armazenar senhas em texto no banco de dados é uma prática considerada como insegura. É aconselhado que utilize senhas hashadas antes de serem salvas nele;

- É inseguro deixar de forma visível informações críticas, como o nome de usuário e a senha do banco de dados diretamente no código;
  
- A saída de mensagem no "  System.err.println("Erro ao executar a query: " + e.getMessage());" pode ser facilmente confundida pelo usuário no momento que for necessário fazer uma manutenção/correção do código.
  
