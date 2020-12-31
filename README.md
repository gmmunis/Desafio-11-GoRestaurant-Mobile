<h1>🚀 Sobre o desafio</h1>
<p>Nesse desafio, você irá desenvolver mais uma aplicação, a GoRestaurant, só que dessa vez a versão mobile para o cliente. Agora você irá praticar o que você aprendeu até agora no React Native junto com TypeScript, para criar um pequeno app para pedidos de comida.</p>
<p>Essa será uma aplicação que irá se conectar a uma Fake API, e exibir e filtrar os pratos de comida da API e permitir a criação de novos pedidos.</p>
<h3>Utilizando uma fake API</h3>
<p>Antes de tudo, para que você tenha os dados para exibir em tela, criamos um arquivo que você poderá utilizar como fake API para te prover esses dados.</p>
<p>Para isso, deixamos instalado no seu package.json uma dependência chamada json-server, e um arquivo chamado server.json que contém os dados para as seguintes rotas:</p>
<pre>Rota /foods: Retorna todas as comidas cadastradas na API</pre>
<pre>Rota /foods/:id: Retorna um prato de comida cadastradas na API baseado no id</pre>
<pre>Rota /categories: Retorna todas as categorias cadastradas na API</pre>
<pre>Rota /orders: Retorna todas os pedidos que foram cadastrados na API</pre>
<pre>Rota /favorites: Retorna todas as comidas favoritas que foram cadastrados na API</pre>
<pre>yarn json-server server.json -p 3333</pre>
<h3>Funcionalidades da aplicação</h3>
<p>Agora que você já está com o template clonado e pronto para continuar, você deve verificar os arquivos da pasta src e completar onde não possui código, com o código para atingir os objetivos de cada rota.</p>
<ul>
<li><strong>Listar os pratos de comida da sua API:</strong> Sua página Dashboard deve ser capaz de exibir uma listagem, com o campo name, value e description de todos os pratos de comida que estão cadastrados na sua API.</li>
<li><strong>Listar as categorias da sua API:</strong> Sua página Dashboard deve ser capaz de exibir uma listagem, com o campo title e image_url de todas as categorias que estão cadastrados na sua API.</li>
<br />
<p><strong>Dica:</strong> O campo thumbnail_url será utilizada como imagem da categoria, deixamos três categorias como exemplo no arquivo server.json.</p>
<br />
<li><strong>Filtrar pratos de comida por busca ou por categorias:</strong> Em sua página Dashboard permitir que o input de pesquisa e os botões de categoria façam uma busca na API de acordo com o que estiver selecionado ou escrito no input.</li>
<li><strong>Listar os pedidos da sua API:</strong> Sua página Orders deve ser capaz de exibir uma listagem, com o campo as informações do produto pedido, com name e description de todos os pedidos que estão cadastrados na sua API.</li>
<br />
<p>Dica: Por se tratar de uma Fake API e de não possuir usuários, não será necessário cadastrar o campo user_id, considere que deve ser listados todos os pedidos da API como se fossem os seus pedidos.</p>
<br />
<li><strong>Listar os pratos favoritos da sua API:</strong> Sua página Favorites deve ser capaz de exibir uma listagem, com o campo as informações do produto favorito, com name e description de todos os pedidos que estão cadastrados na sua API.</li>
<p><strong>Dica:</strong> Por se tratar de uma Fake API e de não possuir usuários, não será necessário cadastrar o campo user_id, considere que deve ser listados todos os favoritos da API como se fossem os seus favoritos.</p>
<li><strong>Realizar um pedido:</strong> Na sua página Dashboard, ao clicar em um item, você deve redirecionar o usuário para a página FoodDetails, onde será possível realizar um novo pedido, podendo controlar a quantidade desse item pedido, ou adicionar ingredientes extras. Todo o valor deve ser calculado de acordo com a quantidade pedida.</li>
<br />
<p>Dica: Você pode usar o método reduce para somar o valor de todos os extras pedidos e somá-lo com o valor do prato de comida. Depois disso lembre-se de multiplicar tudo pela quantidade pedida do produto.</p>
</ul>
<h3>Específicação dos testes</h3>
<p>Em cada teste, tem uma breve descrição no que sua aplicação deve cumprir para que o teste passe.</p>
<p>Para esse desafio, temos os seguintes testes:</p>
<ul>
<li><strong>should be able to list the food plates:</strong> Para que esse teste passe, sua aplicação deve permitir que sejam listados na sua Dashboard, todos os pratos de comidas que são retornados da sua fake API.</li>
<li><strong>should be able to list the food plates filtered by category:</strong> Para que esse teste passe, sua aplicação deve permitir que sejam listados na sua Dashboard, os pratos de comidas filtrados por categoria da sua fake API.</li>
<br />
<p><strong>Dica:</strong> No json-server você pode usar os query params normalmente para buscar/filtrar de acordo com o valor de um campo do item no arquivo server.json. Por exemplo, para filtrar todos os pratos com a categoria 1, a sua url ficaria como http://localhost:3000/foods?category_like=1.</p>
<br />
<li><strong>should be able to list the food plates filtered by name search:</strong> Para que esse teste passe, sua aplicação deve permitir que sejam listados na sua Dashboard, os pratos de comidas filtrados por nome da sua fake API.</li>
<br />
<p>Dica: No json-server você pode usar os query params normalmente para buscar/filtrar de acordo com o valor de um campo do item no arquivo server.json. Por exemplo, para filtrar todos os pratos com o nome Veggie, a sua url ficaria como http://localhost:3000/foods?name_like=Veggie.</p>
<br />
<li><strong>should be able to navigate to the food details page:</strong> Para que esse teste passe, em sua Dashboard, você deve permitir que ao clicar em um item, seja navegado para a página FoodDetails passando por parâmetro da navegação o id do item clicado.</li>
<li><strong>should be able to list the favorite food plates:</strong> Para que esse teste passe, sua aplicação deve permitir que sejam listados na sua página Favorites, todos os pratos de comidas que estão salvos na rota favorites.</li>
<li><strong>should be able to list the orders:</strong> Para que esse teste passe, sua aplicação deve permitir que sejam listados na sua página Orders, todos os pratos de comidas que estão salvos na rota orders.</li>
<li>should be able to list the food: Para que esse teste passe, sua aplicação deve permitir que seja listado todos os dados de uma comída específica na página FoodDetails, baseado no id recuperado pelos parametros da rota.</li>
<br />
<p><strong>Dica 1:<strong>Use o hook useRoute para pegar o atributo params que conterá o id enviado por parametro.</p>
<p>Dica 2: Com o id recuperado por parametro da navegação, faça uma busca na sua API com os dados atualizados da food na roda /foods/:id.</p>
<br />
<li><strong>should be able to increment food quantity:</strong> Para que esse teste passe, você deve permitir que seja incrementada em 1 a quantidade do item na página FoodDetails.</li>
<li><strong>should be able to decrement food quantity:</strong> Para que esse teste passe, você deve permitir que seja decrementada em 1 a quantidade do item na página FoodDetails.</li>
<br />
<p><strong>Dica:</strong> Não permita que o valor do input seja alterado para menor que 1, para que assim o pedido sempre tenha no mínimo um item.</p>
<li><strong>should not be able to decrement food quantity below than 1:</strong> Para que esse teste passe, você deve impedir que seja decrementado a quantidade de itens até um número menor que 1, assim o número mínimo de itens no pedido é 1.</li>
<li><strong>should be able to increment an extra item quantity:</strong> Para que esse teste passe, você deve permitir que seja incrementada em 1 a quantidade de um ingrediente extra na página FoodDetails baseado no seu id.</li>
<li><strong>should be able to decrement an extra item quantity:</strong> Para que esse teste passe, você deve permitir que seja decrementado em 1 a quantidade de um ingrediente extra na página FoodDetails baseado no seu id.</li>
</ul>
