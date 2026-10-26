# iShopping

Aplicação desktop para planear compras, registar o que se comprou e controlar o orçamento mensal.

Projeto de grupo (3 alunos) das unidades curriculares de **Desenvolvimento de Aplicações** e **Metodologias de Desenvolvimento de Software**, TeSP em Programação de Sistemas de Informação, Politécnico de Leiria (2025/26). Gerido em Scrum, com sprints no Jira. Todos os elementos participaram em todas as fases.

![Modo compra](docs/modo-compra.png)

## O que faz

- **Login** com password guardada em hash (SHA-256)
- **Gestão de utilizadores, artigos e tipos de artigo**
- **Listas de compras** com estado (Aberta / Fechada) e filtro por estado
- **Modo compra**: durante a compra regista quantidades e preços, permite juntar artigos não previstos e fechar a lista no fim
- **Orçamento mensal**: define um valor máximo e mostra em tempo real quanto já foi gasto
- Registo de quem criou e quem alterou cada lista e orçamento

## Como está organizado

Separação em **Models / Views / Controllers**:

- **Models**: classes mapeadas para a base de dados com Entity Framework (Code First). `ItemCompra` é uma classe abstrata com duas subclasses, `ItemPrevisto` e `ItemNaoPrevisto` (herança)
- **Views**: formulários Windows Forms
- **Controllers**: a lógica e o acesso aos dados (por exemplo `ListaCompraController`, `OrcamentoController`)

## Tecnologias

C# · .NET Framework 4.8 · Windows Forms · Entity Framework 6 (Code First) · LINQ · SQL Server LocalDB · Git/GitHub · Jira (Scrum)

## Como executar

1. Abrir `Projeto DA MDS.sln` no Visual Studio 2022
2. Restaurar os pacotes NuGet
3. Executar. A base de dados é criada automaticamente na primeira execução, com dados iniciais
4. Entrar com o utilizador de teste `admin1` e a password `1234`

## O que melhoraria

- Juntar um salt às passwords antes do hash
- Testes automáticos aos controllers
