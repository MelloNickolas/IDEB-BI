# 📊 Documentação do Projeto - Dashboard IDEB Brasil

## 📌 Visão Geral do Projeto

Este projeto consiste em um **sistema de dashboards interativos** para análise e visualização dos dados do **IDEB (Índice de Desenvolvimento da Educação Básica)** no Brasil, abrangendo o período de 2005 a 2023.

O sistema permite análise detalhada do desempenho educacional brasileiro por etapa de ensino (Anos Iniciais, Anos Finais e Ensino Médio), com funcionalidades de upload de dados, visualizações interativas e comparação com metas estabelecidas.

---

## 🎯 Objetivos do Projeto

### Objetivo Geral
Desenvolver uma plataforma web interativa para monitoramento e análise da evolução do IDEB nas diferentes etapas da educação básica brasileira.

### Objetivos Específicos
1. **Visualizar a evolução temporal** do IDEB por etapa de ensino (2005-2023)
2. **Comparar desempenho** com metas projetadas pelo INEP
3. **Permitir upload de dados personalizados** via arquivos Excel
4. **Analisar taxa de aprovação** por série e rede de ensino
5. **Identificar tendências e insights** educacionais relevantes

---

## 🏗️ Estrutura do Projeto

### Arquitetura de Arquivos

```
IDEB-BI/
│
├── 📂 BancoDeDados/
│   └── divulgacao_brasil_ideb_2023.xlsx
│
├── 📂 DadosTratados/
│   ├── modelo_taxa_aprovacao_finais.xlsx
│   ├── modelo_taxa_aprovacao_iniciais.xlsx
│   └── modelo_taxa_aprovacao_medio.xlsx
│
├── 📄 index.html (Página inicial/menu)
├── 📄 ideb-dashboard.html (Dashboard IDEB Geral)
├── 📄 dashboard-aprovacao-iniciais.html (Anos Iniciais)
├── 📄 dashboard-aprovacao-finais.html (Anos Finais)
└── 📄 dashboard-aprovacao-medio.html (Ensino Médio)
```

### Descrição dos Componentes

#### **1. index.html** - Página Inicial
- Menu de navegação principal
- Links para todos os dashboards
- Interface simples e intuitiva
- Design responsivo

#### **2. ideb-dashboard.html** - Dashboard IDEB Geral
- Visão consolidada do IDEB Brasil
- Comparação entre as três etapas de ensino
- Gráficos de evolução temporal (2005-2023)
- Análise de crescimento percentual
- Insights sobre desempenho e tendências

#### **3. dashboard-aprovacao-iniciais.html** - Anos Iniciais (1º ao 5º ano)
- Taxa de aprovação por série (1ª a 5ª)
- Comparação entre redes de ensino (Total, Estadual, Pública, Privada)
- Indicadores de rendimento
- Metas e status de cumprimento

#### **4. dashboard-aprovacao-finais.html** - Anos Finais (6º ao 9º ano)
- Taxa de aprovação por série (6ª a 9ª)
- Análise por rede de ensino
- Evolução temporal dos indicadores
- Comparativo de desempenho entre redes

#### **5. dashboard-aprovacao-medio.html** - Ensino Médio
- Taxa de aprovação por série (1ª, 2ª, 3ª + Supletivo)
- Foco nas redes: Total, Estadual, Pública e Privada
- **Observação importante**: Não inclui rede Municipal (inexistente no Ensino Médio)
- Análise de gargalos na transição do 1º ano

---

## 🛠️ Tecnologias Utilizadas

### Frontend
| Tecnologia | Versão | Finalidade |
|------------|--------|------------|
| **HTML5** | - | Estruturação das páginas |
| **CSS3 / Tailwind CSS** | CDN | Estilização e design responsivo |
| **JavaScript (Vanilla)** | ES6+ | Lógica de interação e manipulação de dados |

### Bibliotecas JavaScript
| Biblioteca | Versão | Uso |
|------------|--------|-----|
| **Chart.js** | CDN (latest) | Criação de gráficos interativos (linha, barra) |
| **SheetJS (xlsx)** | 0.18.5 | Leitura e exportação de arquivos Excel |

### CDNs Utilizados
```html
<!-- Tailwind CSS -->
<script src="https://cdn.tailwindcss.com"></script>

<!-- Chart.js -->
<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>

<!-- SheetJS -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/xlsx/0.18.5/xlsx.full.min.js"></script>
```

---

## 📊 Base de Dados

### Fonte dos Dados
- **Origem**: INEP (Instituto Nacional de Estudos e Pesquisas Educacionais Anísio Teixeira)
- **Arquivo original**: `divulgacao_brasil_ideb_2023.xlsx`
- **Período**: 2005 a 2023 (avaliações bienais)

### Estrutura dos Dados

#### IDEB Geral
```
Ano | Anos_Iniciais | Meta_Iniciais | Anos_Finais | Meta_Finais | Ensino_Medio | Meta_Medio
```

#### Taxa de Aprovação (Anos Iniciais/Finais/Médio)
```
Ano | Rede | Serie_1 | Serie_2 | Serie_3 | Serie_4 | Serie_5 | Indicador_Rendimento | Meta
```

**Redes de Ensino:**
- Total (Brasil)
- Estadual
- Municipal (apenas Anos Iniciais e Finais)
- Pública
- Privada

---

## ⚙️ Funcionalidades Principais

### 1. Visualização de Dados
- ✅ **Gráficos de linha**: Evolução temporal do IDEB
- ✅ **Gráficos de barra**: Comparação de crescimento entre etapas
- ✅ **Tabelas interativas**: Dados completos com destaque de metas atingidas
- ✅ **Cards informativos**: Indicadores resumidos

### 2. Filtros e Interatividade
- 🔹 Filtro por etapa de ensino
- 🔹 Filtro por rede de ensino (nos dashboards específicos)
- 🔹 Filtro por série
- 🔹 Visualização de média geral ou série individual
- 🔹 Hover nos gráficos para detalhes

### 3. Upload de Dados Personalizados
- 📤 **Download de template Excel** padronizado
- 📥 **Upload de arquivo Excel** (.xlsx, .xls)
- 🔄 **Atualização automática** dos gráficos e tabelas
- ✅ **Validação de dados** e feedback visual

### 4. Insights e Análises
- 💡 **Caixas de insights** com contexto educacional
- 📈 **Cálculo automático** de crescimento percentual
- ⚠️ **Alertas sobre metas não atingidas**
- 🎯 **Identificação de gargalos** críticos

---

## 🚀 Como Executar o Projeto

### Pré-requisitos
- Navegador web moderno (Chrome, Firefox, Edge, Safari)
- Conexão com internet (para CDNs)
- **Não requer instalação** de software adicional

### Passo a Passo

#### **Opção 1: Execução Local Simples**

1. **Baixe os arquivos do projeto**
   ```bash
   # Clone ou baixe o repositório
   git clone [URL_DO_REPOSITORIO]
   ```

2. **Navegue até a pasta do projeto**
   ```bash
   cd IDEB-BI
   ```

3. **Abra o arquivo index.html no navegador**
   - **Windows**: Clique duplo em `index.html`
   - **Mac/Linux**: Clique com botão direito → "Abrir com" → Navegador
   - **Ou use**: `open index.html` (Mac) / `start index.html` (Windows)

#### **Opção 2: Servidor Local (Recomendado)**

Para evitar problemas de CORS ao carregar arquivos Excel:

**Usando Python:**
```bash
# Python 3
python -m http.server 8000

# Python 2
python -m SimpleHTTPServer 8000
```

**Usando Node.js (http-server):**
```bash
npx http-server -p 8000
```

**Usando VS Code:**
- Instale a extensão **Live Server**
- Clique com botão direito em `index.html`
- Selecione "Open with Live Server"

4. **Acesse no navegador**
   ```
   http://localhost:8000
   ```

---

## 📖 Guia de Uso

### Navegação Básica

1. **Página Inicial (index.html)**
   - Escolha o dashboard desejado clicando nos botões

2. **Visualizando Dados**
   - Use os **filtros** para selecionar etapa/rede/série
   - Passe o mouse sobre os gráficos para detalhes
   - Role a página para ver tabelas e insights

3. **Upload de Dados Personalizados**
   
   a. **Baixar Template**
   - Clique em "⬇️ Baixar Modelo Excel"
   - Abra o arquivo no Excel/Google Sheets
   
   b. **Preencher Dados**
   - Mantenha os cabeçalhos originais
   - Preencha as células com seus dados
   - Respeite o formato numérico
   
   c. **Fazer Upload**
   - Clique em "⬆️ Carregar Arquivo Excel"
   - Selecione seu arquivo preenchido
   - Aguarde a mensagem de confirmação
   
   d. **Visualizar Resultados**
   - Os gráficos serão atualizados automaticamente
   - Os cards mostrarão os novos indicadores
   - A tabela refletirá os dados carregados

### Interpretando os Gráficos

#### **Linhas Sólidas** 🔷
- Representam valores reais do IDEB/Taxa de Aprovação

#### **Linhas Tracejadas** 🔷---
- Representam metas projetadas

#### **Cores dos Indicadores**
- 🟢 **Verde**: Meta atingida
- 🔴 **Vermelho**: Meta não atingida
- ⚪ **Cinza**: Sem meta definida

---

## 🔍 Metodologia de Análise

### 1. Coleta e Preparação dos Dados
- Dados obtidos da base oficial do INEP
- Limpeza e padronização das variáveis
- Organização por etapa de ensino e rede
- Validação de consistência temporal

### 2. Cálculos Realizados

#### **Média Geral (Taxa de Aprovação)**
```javascript
media = (serie_1 + serie_2 + serie_3 + serie_4 + ...) / quantidade_series
```

#### **Crescimento Percentual**
```javascript
crescimento = ((valor_final - valor_inicial) / valor_inicial) × 100
```

#### **Status de Meta**
```javascript
atingiu_meta = valor_obtido >= meta_projetada
```

### 3. Visualizações Geradas
- **Evolução temporal**: Séries históricas 2005-2023
- **Comparações**: Entre redes, etapas e séries
- **Rankings**: Ordenação por desempenho
- **Tendências**: Identificação de padrões

### 4. Insights Extraídos
- Principais avanços e retrocessos
- Gargalos na transição entre séries
- Impacto de eventos (ex: pandemia 2021)
- Diferenças entre redes de ensino

---

## 📈 Principais Resultados e Insights

### IDEB Geral (2005-2023)

#### **Anos Iniciais** 🟢
- **Crescimento**: 57.9% (3.8 → 6.0)
- **Status**: Melhor desempenho geral
- **Observação**: Única etapa que consistentemente superou metas até 2019

#### **Anos Finais** 🟡
- **Crescimento**: 42.9% (3.5 → 5.0)
- **Status**: Crescimento moderado
- **Desafio**: Transição Fundamental I → Fundamental II

#### **Ensino Médio** 🔴
- **Crescimento**: 26.5% (3.4 → 4.3)
- **Status**: Maior desafio educacional
- **Observação**: Nunca atingiu as metas estabelecidas

### Taxa de Aprovação - Ensino Médio (2023)

#### **Gargalo Crítico** ⚠️
- **1º ano**: Menor taxa de aprovação (88.0% - Rede Pública)
- **Causa**: Dificuldade na transição Fundamental → Médio

#### **Metas Superadas** ✅
- **Total**: 0.92 (meta: 91.3%) ✓
- **Pública**: 0.91 (meta: 90.5%) ✓

#### **Alerta - Rede Privada** 🚨
- **Indicador**: 0.96 (meta: 97.1%) ✗
- **Problema**: Instabilidade no Supletivo/EJA (91.2%)

#### **Evolução Histórica** 📈
- **3º ano (Rede Pública)**: 79.6% (2005) → 93.8% (2023)
- **Ganho**: +14.2 pontos percentuais

### Impacto da Pandemia (2021)
- **Todas as etapas**: Queda ou estagnação
- **2023**: Recuperação visível em todos os níveis

---

## 🐛 Problemas Conhecidos e Soluções

### 1. Erro de CORS ao Carregar Arquivos
**Problema**: Navegador bloqueia leitura de arquivos locais

**Solução**: 
- Use um servidor local (http-server, Live Server)
- Ou configure o navegador para permitir file:// protocol

### 2. Gráficos Não Carregam
**Problema**: CDN do Chart.js não acessível

**Solução**:
- Verifique sua conexão com internet
- Baixe Chart.js localmente e ajuste o caminho

### 3. Upload Excel Não Funciona
**Problema**: Formato de arquivo incorreto

**Solução**:
- Use o template fornecido
- Mantenha os nomes das colunas exatamente como no modelo
- Salve como .xlsx (não .xls ou .csv)

### 4. Dados Incorretos Após Upload
**Problema**: Células vazias ou formato inválido

**Solução**:
- Preencha todas as células obrigatórias
- Use números (não texto) nas células de dados
- Para valores nulos, deixe em branco (não use 0)

---

## 🔧 Customização e Extensão

### Adicionar Novos Anos
1. Edite o array `currentData` no arquivo JavaScript
2. Adicione objeto com estrutura:
```javascript
{ ano: 2025, rede: "Total", s1: 90.0, s2: 92.0, ... }
```

### Modificar Cores dos Gráficos
```javascript
const colors = {
    'Total': '#3b82f6',     // Azul
    'Estadual': '#8b5cf6',  // Roxo
    'Pública': '#f59e0b',   // Amarelo
    'Privada': '#ec4899'    // Rosa
};
```

### Adicionar Novos Filtros
1. Crie botões HTML
2. Implemente função `filter[NomeFiltro]()` no JavaScript
3. Atualize o gráfico com `createChart()`

---

## 📝 Contribuindo com o Projeto

### Como Contribuir
1. Fork o repositório
2. Crie uma branch para sua feature (`git checkout -b feature/NovaFuncionalidade`)
3. Commit suas mudanças (`git commit -m 'Adiciona nova funcionalidade'`)
4. Push para a branch (`git push origin feature/NovaFuncionalidade`)
5. Abra um Pull Request

### Diretrizes
- Mantenha o código limpo e comentado
- Teste em múltiplos navegadores
- Atualize a documentação
- Siga os padrões de código existentes

---

## 📄 Licença e Créditos

### Créditos
- **Dados**: INEP (Instituto Nacional de Estudos e Pesquisas Educacionais Anísio Teixeira)
- **Desenvolvimento**: [Seu Nome/Equipe]
- **Bibliotecas**: Chart.js, SheetJS, Tailwind CSS

### Licença
Este projeto é disponibilizado para fins educacionais e de pesquisa.

---

## 📞 Suporte e Contato

### Dúvidas ou Problemas?
- Abra uma **Issue** no repositório
- Consulte a documentação do INEP: [https://www.gov.br/inep/pt-br/areas-de-atuacao/pesquisas-estatisticas-e-indicadores/ideb](https://www.gov.br/inep/pt-br/areas-de-atuacao/pesquisas-estatisticas-e-indicadores/ideb)

---

## 🎓 Referências

1. **INEP** - Índice de Desenvolvimento da Educação Básica (IDEB)
2. **Chart.js Documentation** - [https://www.chartjs.org/docs/](https://www.chartjs.org/docs/)
3. **SheetJS Documentation** - [https://docs.sheetjs.com/](https://docs.sheetjs.com/)
4. **Tailwind CSS** - [https://tailwindcss.com/docs](https://tailwindcss.com/docs)

---

## 📅 Histórico de Versões

| Versão | Data | Descrição |
|--------|------|-----------|
| 1.0.0 | 2024 | Versão inicial com dashboards completos |

---

## ✅ Checklist de Validação do Projeto

- [x] Todos os dashboards funcionando
- [x] Upload de Excel operacional
- [x] Gráficos responsivos
- [x] Dados validados com fonte oficial (INEP)
- [x] Insights contextualizados
- [x] Documentação completa
- [x] Testes em múltiplos navegadores
- [x] Interface intuitiva e acessível

---

**Desenvolvido com 💙 para análise da educação brasileira**