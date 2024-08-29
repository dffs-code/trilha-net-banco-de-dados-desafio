Para resolver o desafio proposto, vamos construir as consultas SQL necessárias com base na descrição fornecida. Suponho que você já tenha criado o banco de dados `Filmes` e que ele esteja populado com os dados necessários conforme o script `Script Filmes.sql`. 

Aqui estão as consultas SQL para cada um dos 12 pedidos:

### 1. Buscar o nome e ano dos filmes

```sql
SELECT Nome, Ano
FROM Filmes;
```

### 2. Buscar o nome e ano dos filmes, ordenados por ordem crescente pelo ano

```sql
SELECT Nome, Ano
FROM Filmes
ORDER BY Ano ASC;
```

### 3. Buscar pelo filme "De Volta para o Futuro", trazendo o nome, ano e a duração

```sql
SELECT Nome, Ano, Duracao
FROM Filmes
WHERE Nome = 'De Volta para o Futuro';
```

### 4. Buscar os filmes lançados em 1997

```sql
SELECT Nome, Ano
FROM Filmes
WHERE Ano = 1997;
```

### 5. Buscar os filmes lançados APÓS o ano 2000

```sql
SELECT Nome, Ano
FROM Filmes
WHERE Ano > 2000;
```

### 6. Buscar os filmes com a duração maior que 100 e menor que 150, ordenando pela duração em ordem crescente

```sql
SELECT Nome, Duracao
FROM Filmes
WHERE Duracao > 100 AND Duracao < 150
ORDER BY Duracao ASC;
```

### 7. Buscar a quantidade de filmes lançados no ano, agrupando por ano, ordenando pela quantidade em ordem decrescente

```sql
SELECT Ano, COUNT(*) AS Quantidade
FROM Filmes
GROUP BY Ano
ORDER BY Quantidade DESC;
```

### 8. Buscar os Atores do gênero masculino, retornando o PrimeiroNome, UltimoNome

```sql
SELECT PrimeiroNome, UltimoNome
FROM Atores
WHERE Genero = 'Masculino';
```

### 9. Buscar os Atores do gênero feminino, retornando o PrimeiroNome, UltimoNome, e ordenando pelo PrimeiroNome

```sql
SELECT PrimeiroNome, UltimoNome
FROM Atores
WHERE Genero = 'Feminino'
ORDER BY PrimeiroNome ASC;
```

### 10. Buscar o nome do filme e o gênero

```sql
SELECT f.Nome AS Filme, g.Nome AS Genero
FROM Filmes f
JOIN FilmesGenero fg ON f.Id = fg.FilmeId
JOIN Generos g ON fg.GeneroId = g.Id;
```

### 11. Buscar o nome do filme e o gênero do tipo "Mistério"

```sql
SELECT f.Nome AS Filme, g.Nome AS Genero
FROM Filmes f
JOIN FilmesGenero fg ON f.Id = fg.FilmeId
JOIN Generos g ON fg.GeneroId = g.Id
WHERE g.Nome = 'Mistério';
```

### 12. Buscar o nome do filme e os atores, trazendo o PrimeiroNome, UltimoNome e seu Papel

```sql
SELECT f.Nome AS Filme, a.PrimeiroNome, a.UltimoNome, ef.Papel
FROM Filmes f
JOIN ElencoFilme ef ON f.Id = ef.FilmeId
JOIN Atores a ON ef.AtorId = a.Id;
```

### Resumo das Consultas:

1. **Nome e ano dos filmes.**
2. **Nome e ano dos filmes ordenados por ano.**
3. **Informações do filme "De Volta para o Futuro".**
4. **Filmes lançados em 1997.**
5. **Filmes lançados após o ano 2000.**
6. **Filmes com duração entre 100 e 150 minutos, ordenados pela duração.**
7. **Quantidade de filmes lançados por ano, ordenados pela quantidade.**
8. **Atores do gênero masculino.**
9. **Atores do gênero feminino, ordenados pelo primeiro nome.**
10. **Nome do filme e o gênero.**
11. **Nome do filme e gênero "Mistério".**
12. **Nome do filme e os atores, incluindo o papel.**

Cada uma dessas consultas reflete o que foi solicitado no desafio e deve fornecer os resultados esperados conforme o diagrama e as descrições fornecidas. Certifique-se de ajustar qualquer nome de tabela ou coluna se eles diferirem no seu banco de dados real.
