# :sparkles: Tutorial - Manipulação de Arrays em JS (Map, Filter, Reduce)

# :green_circle: MAP

A função `map()` é utilizada para transformar dados. Ela percorre cada elemento de um array original e cria um **novo array** com os resultados de uma função aplicada a cada item. o `map()` não altera o array original e o novo array terá sempre o mesmo tamanho do original.

## :green_circle: EXEMPLO | DOBRANDO VALORES

    const numeros = [1, 2, 3, 4];
    const dobrados = numeros.map(n => n * 2);
    
    console.log(dobrados); // [2, 4, 6, 8]

## :green_circle: EXEMPLO | MANIPULANDO OBJETOS

    const produtos = [
        { nome: 'Teclado', preco: 150 },
        { nome: 'Mouse', preco: 80 }
    ];
    
    const apenasNomes = produtos.map(p => p.nome);
    console.log(apenasNomes); // ["Teclado", "Mouse"]


# :yellow_circle: FILTER

O `filter()` é usado para criar um novo array contendo apenas os elementos que satisfazem uma condição. O callback que você passa para ele como parametro deve retornar um valor booleano (`true` para manter o item, `false` para descartar).

## :yellow_circle: EXEMPLO | FILTRANDO PARES

    const valores = [1, 2, 3, 4, 5, 6];
    const pares = valores.filter(n => n % 2 === 0);
    
    console.log(pares); // [2, 4, 6]

## :yellow_circle: EXEMPLO | FILTRANDO OBJETOS

    const alunos = [
        { nome: 'Ana', nota: 9 },
        { nome: 'Joao', nota: 5 }
    ];
    
    const aprovados = alunos.filter(a => a.nota >= 7);
    console.log(aprovados); // [{ nome: 'Ana', nota: 9 }]


# :red_circle: REDUCE

O `reduce()` é a função mais versátil e "poderoso". Ele serve para reduzir todos os elementos de um array a um **único valor final** (que pode ser um número, uma string, um objeto ou até outro array). Ele utiliza um "acumulador" que guarda o resultado das operações anteriores.

## :red_circle: EXEMPLO | SOMATÓRIO

    const carrinho = [10, 20, 30];
    const total = carrinho.reduce((acc, atual) => acc + atual, 0);
    
    console.log(total); // 60

## :red_circle: EXEMPLO | CONTANDO OCORRÊNCIAS

    const frutas = ['maçã', 'banana', 'maçã'];
    const contagem = frutas.reduce((acc, fruta) => {
        acc[fruta] = (acc[fruta] || 0) + 1;
        return acc;
    }, {});

    console.log(contagem); // { maçã: 2, banana: 1 }
