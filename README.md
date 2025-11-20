# 1-ETL-PLANILHAS-EXCEL 📊📁

Projeto de estudo de Engenharia de Dados focado em **ETL de múltiplas planilhas Excel**.

A ideia é pegar ~50 arquivos `.xlsx` de entrada, consolidar tudo em um conjunto único e, ao mesmo tempo, aplicar boas práticas de:

- organização de projeto
- gerenciamento de dependências com **Poetry**
- uso de **pyenv**
- padrões de código (blue + isort)
- testes automatizados com **pytest**
- automações com **taskipy** e **pre-commit**
- documentação com **MkDocs** (com tema **mkdocs-material**)

---

## 🎯 Objetivos do Projeto

- Praticar a **estruturação completa** de um projeto de dados do zero.
- Implementar um **pipeline ETL** simples, mas bem organizado.
- Usar ferramentas que são comuns no dia a dia de um engenheiro de dados.
- Servir como **projeto 1** da minha jornada em engenharia de dados, registrando a evolução no GitHub.

---

## 🧱 Arquitetura / Estrutura de Pastas

Estrutura geral do projeto (simplificada):

```bash
1-etl-planilhas-excel/
├── data/
│   ├── input/      # ~50 arquivos Excel de entrada
│   └── output/     # arquivos consolidados gerados pelo ETL
├── src/
│   └── 1_etl_planilhas_excel/
│       ├── __init__.py
│       ├── main.py        # ponto de entrada do pipeline
│       ├── extract.py     # funções de extração (ler os Excels)
│       ├── transform.py   # funções de limpeza e transformação
│       └── load.py        # funções de carga (salvar o resultado)
├── tests/
│   └── __init__.py
├── .gitignore
├── .python-version
├── pyproject.toml
└── README.md
```

---

## 🔧 Tecnologias e Ferramentas

- **Python** (gerenciado com `pyenv`)
- **Poetry** para gerenciamento de dependências e virtualenv
- **Pandas** (para manipulação das planilhas Excel) – a ser adicionado
- **Pytest** para testes automatizados – a ser configurado
- **Blue** para formatação de código
- **isort** para organização de imports
- **Taskipy** para criar tarefas de automação
  (`task test`, `task lint`, `task format`, `task run`, etc.) – a ser configurado
- **Pre-commit** para rodar checagens automáticas antes dos commits – a ser configurado
- **MkDocs** + **mkdocs-material** para documentação do projeto – a ser configurado

---

## 🚀 Como rodar o projeto (visão geral)

> Esses passos são um guia geral. Os comandos exatos podem variar de acordo com o ambiente, mas a ideia é essa:

1. **Clonar o repositório**
2. **Definir a versão do Python** com `pyenv` (por ex.: `3.14.0`).
3. **Criar/usar o ambiente virtual** com o Poetry.
4. **Instalar as dependências** definidas no `pyproject.toml`.
5. Colocar os arquivos Excel na pasta `data/input/`.
6. Rodar o script principal (por exemplo, o módulo `main` do pacote) para executar o ETL.

Conforme o projeto evoluir, esta seção será atualizada com os comandos exatos.

---

## 🧬 Desenho do ETL (alto nível)

O pipeline segue a clássica divisão **Extract → Transform → Load**:

1. **Extract (`extract.py`)**
   - Ler todos os arquivos Excel em `data/input/`.
   - Padronizar colunas básicas (nomes, tipos etc.).

2. **Transform (`transform.py`)**
   - Limpar dados (valores nulos, tipos incorretos, etc.).
   - Padronizar formatos (datas, números, categorias).
   - Unir as tabelas em um único DataFrame consolidado.

3. **Load (`load.py`)**
   - Salvar o resultado consolidado em `data/output/`.
   - Formatos possíveis: `.csv`, `.parquet` ou `.xlsx` consolidado.

4. **Orquestração (`main.py`)**
   - Ponto de entrada que chama `extract`, depois `transform`, depois `load`.

---

## 🧪 Testes

Os testes serão escritos usando **pytest**. A ideia é:

- testar funções individuais de extração, transformação e carga;
- garantir que o pipeline funciona mesmo se a estrutura de arquivos mudar um pouco;
- facilitar refatorações futuras sem medo.

No início, os testes serão simples (ex.: testar se a função consegue ler 1 planilha exemplo). Conforme o projeto evoluir, os testes ficam mais completos.

---

## 🧹 Padrões de Código

Este projeto vai usar principalmente:

- **Blue** para formatação automática do código;
- **isort** para organizar imports.

A ideia é automatizar isso via:

- **taskipy** (tarefas como `task format` e `task lint`);
- **pre-commit** (para rodar essas checagens antes dos commits).

Assim, o foco fica na lógica de dados, e não em brigar com estilo de código.

---

## 📚 Documentação (MkDocs)

A documentação deste projeto será construída usando **MkDocs**, com o tema **mkdocs-material**.

A ideia é ter:

- uma visão geral do projeto e do pipeline ETL;
- explicação das funções principais (`extract`, `transform`, `load`, `main`);
- exemplos de uso;
- instruções de instalação e execução mais detalhadas.

A estrutura planejada é algo como:

- `docs/`
  - `index.md` — página inicial da documentação
  - `etl.md` — detalhes do pipeline de ETL
  - `setup.md` — guia de instalação e configuração do ambiente
  - `faq.md` — dúvidas frequentes (opcional)

No futuro, a documentação poderá ser publicada usando **GitHub Pages**, permitindo acessar tudo via navegador.

---

## ✅ Status do Projeto

- [x] Estrutura inicial do projeto criada
- [x] Organização das pastas (`src`, `tests`, `data`)
- [ ] Configuração completa do `pyproject.toml` (dependências)
- [ ] Implementação do ETL (extract/transform/load)
- [ ] Testes automatizados com pytest
- [ ] Taskipy + pre-commit configurados
- [ ] Documentação com MkDocs (estrutura e publicação)

Este README será atualizado conforme cada etapa for concluída.

---

## 💬 Sobre o autor

Projeto criado para estudos por **Rômulo**, como parte da jornada para se tornar **Engenheiro de Dados**, inspirado no workshop *"Como Estruturar um Projeto de Dados do Zero"* do curso **Jornada de Dados**.

Sinta-se à vontade para abrir issues/sugestões ou apenas usar este repositório como referência de estudo.
