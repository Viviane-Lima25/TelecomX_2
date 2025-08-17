# 📞 TelecomX - Análise de Churn

Este projeto tem como objetivo analisar e prever o **churn (rotatividade de clientes)** em uma empresa de telecomunicações, a **TelecomX**.  
A análise busca identificar clientes com maior probabilidade de cancelar o contrato, permitindo ações estratégicas de retenção.

---

## 📂 Estrutura do Projeto

- `data/` → Conjunto de dados (pré-processado a partir de features contratuais e de cobrança).  
- `notebooks/` → Jupyter Notebooks com análise exploratória, pré-processamento e modelagem.  
- `models/` → Modelos treinados para previsão de churn.  
- `README.md` → Documentação do projeto.  

---

## 🧾 Dados Utilizados

As variáveis incluem informações demográficas, contratuais e financeiras dos clientes, como:

- `gender`, `SeniorCitizen`, `Partner`, `Dependents`  
- Tipo de contrato: `Contract_Month-to-month`, `Contract_One year`, `Contract_Two year`  
- Método de pagamento: `PaymentMethod_Bank transfer`, `Credit card`, `Electronic check`, `Mailed check`  
- `PaperlessBilling`  
- Histórico de uso: `tenure`, `Charges.Monthly`, `Charges.Total`  

---

## ⚙️ Modelagem

Foram testados dois modelos principais:

### 🔹 Modelo 1 (Conservador)
- **Acurácia:** 77%  
- **Recall churn:** 48%  
- **Precision churn:** 56%  
- Forte em prever **quem não sai**, mas perde quase metade dos churns reais.  

### 🔹 Modelo 2 (Agressivo)
- **Acurácia:** 68%  
- **Recall churn:** 64%  
- **Precision churn:** 42%  
- Melhor em prever **quem sai**, mas com mais falsos positivos.  

---

## 📊 Matrizes de Confusão

| Modelo | Não Churn (corretos) | Falsos Positivos | Churn detectados | Falsos Negativos |
|--------|----------------------|------------------|------------------|------------------|
| 1      | 992                  | 153              | 192              | 205              |
| 2      | 560                  | 248              | 180              | 101              |

---

## ✅ Conclusões e Recomendações

- O **Modelo 1** é indicado caso o objetivo seja **evitar custo excessivo em campanhas de retenção**.  
- O **Modelo 2** é indicado se o foco for **reduzir ao máximo a perda de clientes**, mesmo com falsos positivos.  

### 📌 Próximos Passos
1. **Ajuste de Threshold:** encontrar ponto ótimo via curva Precision-Recall para equilibrar recall e precision da classe churn.  
2. **Balanceamento de Classes:** aplicar SMOTE e/ou `class_weight` para melhorar a detecção da classe minoritária.  
3. **Feature Engineering:** incluir variáveis adicionais de comportamento (uso de internet, chamadas, suporte técnico).  
4. **Validação Cruzada:** aplicar k-fold cross-validation para validar robustez dos resultados.  

---

## 🚀 Tecnologias Utilizadas

- Python 3  
- Pandas, Numpy, Scikit-learn, Imbalanced-learn  
- Matplotlib, Seaborn, Plotly  
- Jupyter Notebook  

 
