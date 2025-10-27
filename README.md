# HTML5 - Tutorial Completo sobre Tabelas

## 📚 Índice

1. [Introdução](#introdução)
2. [Estrutura Básica de uma Tabela](#estrutura-básica-de-uma-tabela)
3. [Elementos Fundamentais](#elementos-fundamentais)
4. [Cabeçalhos e Legendas](#cabeçalhos-e-legendas)
5. [Seções de Tabela](#seções-de-tabela)
6. [Mesclagem de Células](#mesclagem-de-células)
7. [Acessibilidade em Tabelas](#acessibilidade-em-tabelas)
8. [Exemplos Práticos](#exemplos-práticos)
9. [Boas Práticas](#boas-práticas)
10. [Recursos Adicionais](#recursos-adicionais)

---

## Introdução

As tabelas HTML são elementos fundamentais para organizar e exibir dados de forma estruturada em páginas web. Elas permitem apresentar informações em formato de linhas e colunas, facilitando a leitura e compreensão de dados relacionados.

### Quando usar tabelas?

✅ **Use tabelas para:**
- Exibir dados tabulares (planilhas, relatórios, estatísticas)
- Comparar informações organizadas em linhas e colunas
- Apresentar horários, preços, especificações técnicas
- Mostrar resultados de pesquisas ou análises

❌ **NÃO use tabelas para:**
- Layout de página (use CSS Grid ou Flexbox)
- Posicionar elementos na página
- Criar estruturas visuais não relacionadas a dados

---

## Estrutura Básica de uma Tabela

Uma tabela HTML básica é composta por três elementos principais:

```html
<table>
  <tr>
    <td>Linha 1, Célula 1</td>
    <td>Linha 1, Célula 2</td>
  </tr>
  <tr>
    <td>Linha 2, Célula 1</td>
    <td>Linha 2, Célula 2</td>
  </tr>
</table>
```

### Resultado:

| Linha 1, Célula 1 | Linha 1, Célula 2 |
| Linha 2, Célula 1 | Linha 2, Célula 2 |

---

## Elementos Fundamentais

### `<table>`
Elemento raiz que define o início e fim de uma tabela.

```html
<table>
  <!-- conteúdo da tabela -->
</table>
```

### `<tr>` (Table Row)
Define uma linha na tabela. Cada linha pode conter múltiplas células.

```html
<tr>
  <td>Célula 1</td>
  <td>Célula 2</td>
</tr>
```

### `<td>` (Table Data)
Define uma célula de dados comum na tabela.

```html
<td>Conteúdo da célula</td>
```

### `<th>` (Table Header)
Define uma célula de cabeçalho. Por padrão, o texto fica em negrito e centralizado.

```html
<th>Nome da Coluna</th>
```

---

## Cabeçalhos e Legendas

### Exemplo com Cabeçalhos

```html
<table>
  <tr>
    <th>Nome</th>
    <th>Idade</th>
    <th>Cidade</th>
  </tr>
  <tr>
    <td>Ana Silva</td>
    <td>25</td>
    <td>São Paulo</td>
  </tr>
  <tr>
    <td>João Santos</td>
    <td>30</td>
    <td>Rio de Janeiro</td>
  </tr>
</table>
```

### Adicionando uma Legenda com `<caption>`

A tag `<caption>` adiciona um título descritivo à tabela:

```html
<table>
  <caption>Lista de Alunos - Turma 2024</caption>
  <tr>
    <th>Nome</th>
    <th>Matrícula</th>
    <th>Curso</th>
  </tr>
  <tr>
    <td>Maria Oliveira</td>
    <td>2024001</td>
    <td>Engenharia</td>
  </tr>
</table>
```

---

## Seções de Tabela

Para tabelas mais complexas, é recomendado dividir o conteúdo em seções semânticas:

### `<thead>` - Cabeçalho da Tabela
Agrupa as linhas de cabeçalho.

### `<tbody>` - Corpo da Tabela
Agrupa as linhas de dados principais.

### `<tfoot>` - Rodapé da Tabela
Agrupa as linhas de rodapé (totais, resumos, etc.).

### Exemplo Completo

```html
<table>
  <caption>Relatório de Vendas - 1º Trimestre 2024</caption>
  
  <thead>
    <tr>
      <th>Mês</th>
      <th>Produto</th>
      <th>Vendas (R$)</th>
    </tr>
  </thead>
  
  <tbody>
    <tr>
      <td>Janeiro</td>
      <td>Notebook</td>
      <td>15.000,00</td>
    </tr>
    <tr>
      <td>Fevereiro</td>
      <td>Mouse</td>
      <td>2.500,00</td>
    </tr>
    <tr>
      <td>Março</td>
      <td>Teclado</td>
      <td>3.200,00</td>
    </tr>
  </tbody>
  
  <tfoot>
    <tr>
      <th colspan="2">Total</th>
      <th>20.700,00</th>
    </tr>
  </tfoot>
</table>
```

---

## Mesclagem de Células

### `colspan` - Mesclar Colunas

Permite que uma célula ocupe múltiplas colunas:

```html
<table>
  <tr>
    <th colspan="3">Informações do Produto</th>
  </tr>
  <tr>
    <td>Nome</td>
    <td>Preço</td>
    <td>Estoque</td>
  </tr>
  <tr>
    <td>Cadeira</td>
    <td>R$ 250,00</td>
    <td>15 unidades</td>
  </tr>
</table>
```

### `rowspan` - Mesclar Linhas

Permite que uma célula ocupe múltiplas linhas:

```html
<table>
  <tr>
    <th>Categoria</th>
    <th>Produto</th>
    <th>Preço</th>
  </tr>
  <tr>
    <td rowspan="2">Eletrônicos</td>
    <td>Smartphone</td>
    <td>R$ 1.500,00</td>
  </tr>
  <tr>
    <td>Tablet</td>
    <td>R$ 800,00</td>
  </tr>
  <tr>
    <td rowspan="2">Livros</td>
    <td>Romance</td>
    <td>R$ 45,00</td>
  </tr>
  <tr>
    <td>Técnico</td>
    <td>R$ 120,00</td>
  </tr>
</table>
```

### Combinando `colspan` e `rowspan`

```html
<table>
  <tr>
    <th colspan="2" rowspan="2">Produto</th>
    <th colspan="2">Vendas</th>
  </tr>
  <tr>
    <th>Janeiro</th>
    <th>Fevereiro</th>
  </tr>
  <tr>
    <td>Categoria A</td>
    <td>Item 1</td>
    <td>100</td>
    <td>150</td>
  </tr>
</table>
```

---

## Acessibilidade em Tabelas

A acessibilidade é crucial para garantir que todos os usuários, incluindo aqueles que utilizam tecnologias assistivas, possam compreender o conteúdo das tabelas.

### Atributo `scope`

Define se um cabeçalho se aplica a uma linha ou coluna:

```html
<table>
  <tr>
    <th scope="col">Nome</th>
    <th scope="col">Email</th>
  </tr>
  <tr>
    <th scope="row">Contato 1</th>
    <td>joao@email.com</td>
  </tr>
</table>
```

Valores possíveis:
- `scope="col"` - cabeçalho de coluna
- `scope="row"` - cabeçalho de linha
- `scope="colgroup"` - cabeçalho de grupo de colunas
- `scope="rowgroup"` - cabeçalho de grupo de linhas

### Atributos `id` e `headers`

Para tabelas complexas, use `id` nos cabeçalhos e `headers` nas células:

```html
<table>
  <tr>
    <th id="nome">Nome</th>
    <th id="idade">Idade</th>
  </tr>
  <tr>
    <td headers="nome">Carlos</td>
    <td headers="idade">28</td>
  </tr>
</table>
```

### Sempre use `<caption>`

A legenda ajuda a identificar o propósito da tabela:

```html
<table>
  <caption>Horário de Aulas - Semana 1</caption>
  <!-- conteúdo da tabela -->
</table>
```

---

## Exemplos Práticos

### Exemplo 1: Tabela de Horários

```html
<table>
  <caption>Horário de Aulas - 2º Semestre 2024</caption>
  <thead>
    <tr>
      <th scope="col">Horário</th>
      <th scope="col">Segunda</th>
      <th scope="col">Terça</th>
      <th scope="col">Quarta</th>
      <th scope="col">Quinta</th>
      <th scope="col">Sexta</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">08:00 - 10:00</th>
      <td>Matemática</td>
      <td>Português</td>
      <td>Matemática</td>
      <td>História</td>
      <td>Geografia</td>
    </tr>
    <tr>
      <th scope="row">10:00 - 12:00</th>
      <td>Física</td>
      <td>Química</td>
      <td>Física</td>
      <td>Biologia</td>
      <td>Inglês</td>
    </tr>
    <tr>
      <th scope="row">14:00 - 16:00</th>
      <td>Informática</td>
      <td>Educação Física</td>
      <td>Arte</td>
      <td>Filosofia</td>
      <td>Sociologia</td>
    </tr>
  </tbody>
</table>
```

### Exemplo 2: Tabela de Preços

```html
<table>
  <caption>Planos de Assinatura - Streaming Online</caption>
  <thead>
    <tr>
      <th scope="col">Recurso</th>
      <th scope="col">Básico</th>
      <th scope="col">Padrão</th>
      <th scope="col">Premium</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">Preço Mensal</th>
      <td>R$ 19,90</td>
      <td>R$ 34,90</td>
      <td>R$ 49,90</td>
    </tr>
    <tr>
      <th scope="row">Qualidade de Vídeo</th>
      <td>HD</td>
      <td>Full HD</td>
      <td>4K Ultra HD</td>
    </tr>
    <tr>
      <th scope="row">Telas Simultâneas</th>
      <td>1</td>
      <td>2</td>
      <td>4</td>
    </tr>
    <tr>
      <th scope="row">Download</th>
      <td>Não</td>
      <td>Sim</td>
      <td>Sim</td>
    </tr>
  </tbody>
</table>
```

### Exemplo 3: Tabela de Resultados Esportivos

```html
<table>
  <caption>Classificação - Campeonato Brasileiro 2024</caption>
  <thead>
    <tr>
      <th scope="col">Posição</th>
      <th scope="col">Time</th>
      <th scope="col">Pontos</th>
      <th scope="col">Jogos</th>
      <th scope="col">Vitórias</th>
      <th scope="col">Empates</th>
      <th scope="col">Derrotas</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">1º</th>
      <td>Flamengo</td>
      <td>45</td>
      <td>20</td>
      <td>14</td>
      <td>3</td>
      <td>3</td>
    </tr>
    <tr>
      <th scope="row">2º</th>
      <td>Palmeiras</td>
      <td>42</td>
      <td>20</td>
      <td>13</td>
      <td>3</td>
      <td>4</td>
    </tr>
    <tr>
      <th scope="row">3º</th>
      <td>São Paulo</td>
      <td>38</td>
      <td>20</td>
      <td>11</td>
      <td>5</td>
      <td>4</td>
    </tr>
  </tbody>
</table>
```

### Exemplo 4: Tabela com Dados Financeiros

```html
<table>
  <caption>Demonstrativo Financeiro - Empresa XYZ Ltda</caption>
  <thead>
    <tr>
      <th scope="col">Descrição</th>
      <th scope="col">2022</th>
      <th scope="col">2023</th>
      <th scope="col">2024</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">Receita Bruta</th>
      <td>R$ 500.000,00</td>
      <td>R$ 650.000,00</td>
      <td>R$ 800.000,00</td>
    </tr>
    <tr>
      <th scope="row">Despesas Operacionais</th>
      <td>R$ 200.000,00</td>
      <td>R$ 250.000,00</td>
      <td>R$ 300.000,00</td>
    </tr>
    <tr>
      <th scope="row">Impostos</th>
      <td>R$ 80.000,00</td>
      <td>R$ 100.000,00</td>
      <td>R$ 120.000,00</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <th scope="row">Lucro Líquido</th>
      <td>R$ 220.000,00</td>
      <td>R$ 300.000,00</td>
      <td>R$ 380.000,00</td>
    </tr>
  </tfoot>
</table>
```

---

## Boas Práticas

### 1. **Estrutura Semântica**
- Sempre use `<thead>`, `<tbody>` e `<tfoot>` quando apropriado
- Use `<th>` para cabeçalhos e `<td>` para dados
- Adicione `<caption>` para descrever a tabela

### 2. **Acessibilidade**
- Use o atributo `scope` em células de cabeçalho
- Adicione `id` e `headers` para tabelas complexas
- Forneça textos alternativos descritivos
- Evite usar tabelas apenas para layout visual

### 3. **Organização**
- Mantenha a estrutura da tabela simples e clara
- Use mesclagem de células (`colspan` e `rowspan`) apenas quando necessário
- Organize dados de forma lógica e intuitiva

### 4. **Estilização**
- Use CSS para estilizar tabelas, não atributos HTML obsoletos
- Evite usar atributos como `border`, `cellpadding`, `cellspacing`
- Considere responsividade para dispositivos móveis

### 5. **Performance**
- Para tabelas muito grandes, considere paginação
- Evite tabelas aninhadas (tabela dentro de tabela)
- Use JavaScript para funcionalidades avançadas (ordenação, filtros)

### Exemplo de CSS Básico para Tabelas

```css
table {
  width: 100%;
  border-collapse: collapse;
  margin: 20px 0;
}

th, td {
  padding: 12px;
  text-align: left;
  border-bottom: 1px solid #ddd;
}

th {
  background-color: #4CAF50;
  color: white;
  font-weight: bold;
}

tr:hover {
  background-color: #f5f5f5;
}

caption {
  font-size: 1.5em;
  margin: 10px 0;
  font-weight: bold;
}
```

---

## Recursos Adicionais

### Documentação Oficial
- [MDN Web Docs - HTML Table](https://developer.mozilla.org/pt-BR/docs/Web/HTML/Element/table)
- [W3C - Tables in HTML](https://www.w3.org/WAI/tutorials/tables/)
- [HTML Living Standard - Tables](https://html.spec.whatwg.org/multipage/tables.html)

### Ferramentas Úteis
- [HTML Table Generator](https://www.tablesgenerator.com/html_tables)
- [Validador HTML da W3C](https://validator.w3.org/)
- [Lighthouse - Teste de Acessibilidade](https://developers.google.com/web/tools/lighthouse)

### Tutoriais Complementares
- Responsividade em tabelas
- Ordenação de tabelas com JavaScript
- Tabelas dinâmicas com frameworks (React, Vue, Angular)
- Exportação de tabelas para PDF/Excel

---

## 🎯 Exercícios Práticos

Para fixar o aprendizado, tente criar as seguintes tabelas:

1. **Tabela Simples**: Crie uma tabela com 3 colunas e 4 linhas contendo informações sobre seus filmes favoritos (título, ano, diretor).

2. **Tabela com Seções**: Crie uma tabela de notas escolares com cabeçalho, corpo e rodapé calculando a média final.

3. **Tabela com Mesclagem**: Crie um cardápio de restaurante usando `colspan` e `rowspan` para organizar categorias e itens.

4. **Tabela Acessível**: Crie uma tabela de produtos com todos os atributos de acessibilidade (`scope`, `caption`, etc.).

5. **Tabela Complexa**: Crie um calendário mensal usando tabelas HTML.

---

## 📝 Conclusão

As tabelas HTML são ferramentas poderosas para apresentar dados estruturados de forma clara e acessível. Seguindo as boas práticas e utilizando os elementos semânticos corretos, você criará tabelas profissionais e acessíveis para seus projetos web.

Lembre-se:
- ✅ Use tabelas para dados tabulares
- ✅ Priorize acessibilidade
- ✅ Mantenha a estrutura semântica
- ✅ Estilize com CSS
- ✅ Teste em diferentes dispositivos

---

## 📄 Licença

Este material é disponibilizado para fins educacionais. Consulte o arquivo LICENSE para mais detalhes.

---

**Última atualização**: Outubro de 2024
