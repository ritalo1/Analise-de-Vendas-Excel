# Analise-de-Vendas-Excel
import pandas as pd
import matplotlib.pyplot as plt

dados = {
    'Mês': ['Janeiro', 'Fevereiro', 'Março', 'Abril', 'Maio', 'Junho', 'Julho', 'Agosto', 'Setembro', 'Outubro', 'Novembro', 'Dezembro'],
    'Vendas (R$)': [12000, 15000, 18000, 16000, 21000, 24000, 8000, 25000, 21000, 20000, 19500, 18750]
}

df = pd.DataFrame(dados)

df.to_excel('relatorio_vendas.xlsx', index=False)
print("📊 Gráfico gerado com sucesso.")

planilha_lida = pd.read_excel('relatorio_vendas.xlsx')

plt.figure(figsize=(15, 8))
plt.bar(planilha_lida['Mês'], planilha_lida['Vendas (R$)'], color='darkgreen', edgecolor='black')

plt.title('Faturamento Mensal (Gráfico)', fontsize=14, fontweight='bold')
plt.xlabel('Meses (1~12)', fontsize=16)
plt.ylabel('Faturamento em R$', fontsize=16)
plt.grid(axis='y', linestyle='--', alpha=0.7)

plt.show()
