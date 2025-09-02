# CP1 - Análise de Dados de Consumidores de Energia

## 👥 Integrantes
- **Ana Carolina Reis Santana rm556219**
- **Letícia Zago de Souza rm558464**
- **Pedro Henrique Mendonça de Novais rm555276**

---

## 📌 Descrição do Projeto
Este repositório contém a análise do dataset **Individual Household Electric Power Consumption (UCI)**, com:
- **Partes 1–3 (Python/Notebook):** leitura, limpeza, EDA, séries temporais, autocorrelação, PCA, K-Means e regressões.
- **Parte 4 (Orange):** fluxo visual com distribuições, correlações, clusters, PCA e (se aplicável) regressão.

> Dataset (UCI): https://archive.ics.uci.edu/dataset/235/individual+household+electric+power+consumption

---

## 🗂️ Estrutura
```
/
├─ README.md
├─ requirements.txt                 # opcional (ou use a primeira célula %pip)
├─ Trabalho_Consumo_Energia_vf.ipynb   
└─ orange/
   ├─ workflow.ows                 
   └─ prints/                      
```
> Se o nome do seu notebook for outro, ajuste aqui ou renomeie para `Trabalho_Consumo_Energia_v5.ipynb`.

---

## 🗃️ Dados
- **Arquivo esperado:** `household_power_consumption.txt` (delimitador `;`)
- **Colunas chave:** `Date` (dd/mm/yyyy), `Time`
- **Caminho:** coloque o arquivo na **raiz do projeto** ou ajuste o caminho dentro do notebook.

### 📑 Detalhes do dataset (UCI — Individual Household Electric Power Consumption)
- **Período:** 16/12/2006 a 26/11/2010  
- **Frequência de amostragem:** 1 minuto  
- **Instâncias:** ~2.075.259 linhas  
- **Atributos** (delimitador `;`):  
  - `Date` (dd/mm/yyyy) — data da medição  
  - `Time` (hh:mm:ss) — hora da medição  
  - `Global_active_power` (kW) — potência ativa média do minuto para a residência  
  - `Global_reactive_power` (kW) — potência reativa média do minuto  
  - `Voltage` (V) — tensão média do minuto  
  - `Global_intensity` (A) — corrente média do minuto  
  - `Sub_metering_1` (Wh) — submedição 1 *(cozinha: lava-louça, forno, micro-ondas, etc.)*  
  - `Sub_metering_2` (Wh) — submedição 2 *(lavanderia: máquina de lavar, secadora, geladeira, iluminação)*  
  - `Sub_metering_3` (Wh) — submedição 3 *(aquecedor de água elétrico e ar-condicionado)*  
- **Valores faltantes:** marcados como `?` no arquivo original (no notebook tratamos com `na_values=['?','NA','']`)  
- **Variável derivada usada nas análises:** `Total_Sub_metering = Sub_metering_1 + Sub_metering_2 + Sub_metering_3` (Wh)  
- **Download/descrição oficial:** ver página do dataset na UCI (link acima)

---

## 🚀 Como executar (local)
### 1) Ambiente (Python 3.10+)
```bash
python -m venv .venv
# Linux/macOS:
source .venv/bin/activate
# Windows (PowerShell):
# .venv\Scripts\Activate.ps1
pip install -r requirements.txt
```
> Alternativa: rode a **primeira célula** de instalação no notebook (`%pip install ...`) se preferir.

### 2) Executar o notebook
```bash
jupyter notebook
# Abra: Trabalho_Consumo_Energia_v5.ipynb
# Kernel → Restart & Run All
```

---

## ☁️ Como executar (Google Colab)
1. Faça upload de `household_power_consumption.txt` no Colab (ou monte o Google Drive).  
2. Abra `Trabalho_Consumo_Energia_v5.ipynb`.  
3. Rode a célula de instalação (se houver) e depois **Ambiente de execução → Reiniciar e executar tudo**.

---

## 🔧 Notas Técnicas
- **Parsing:** `na_values=['?','NA','']`; `Date` + `Time` → índice `datetime` (`dayfirst=True`)
- **Pré-processamento:** `StandardScaler` antes de PCA/K-Means
- **Reprodutibilidade:** `random_state=42` (modelos e K-Means)
- **Performance:** execute com kernel limpo e evite múltiplas cópias de DataFrames

---

## 📎 Referências
- UCI ML Repository — *Individual Household Electric Power Consumption*  
- Documentação: pandas, scikit-learn, statsmodels, Orange3
