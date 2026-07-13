import pandas as pd
import matplotlib.pyplot as plt

def criar_planilha_vendas():
    dados = {
        'Mês': ['Janeiro', 'Fevereiro', 'Março', 'Abril', 'Maio', 'Junho', 'Julho', 'Agosto', 'Setembro', 'Outubro', 'Novembro', 'Dezembro'],
        'Vendas (R$)': [12000, 15000, 18000, 16000, 21000, 24000, 8000, 25000, 21000, 20000, 19500, 18750]
    }
    df = pd.DataFrame(dados)
    df.to_excel('relatorio_vendas.xlsx', index=False)
    print("📊 Gráfico 'relatorio_vendas.xlsx' gerado com sucesso.")


def analisar_dados():
    # Lendo a planilha
    df = pd.read_excel('relatorio_vendas.xlsx')
    
    total_vendas = df['Vendas (R$)'].sum()
    media_mensal = df['Vendas (R$)'].mean()
    melhor_mes = df.loc[df['Vendas (R$)'].idxmax()]['Mês']
    maior_valor = df['Vendas (R$)'].max()
    
    print("\n--- RELATÓRIO DE NEGÓCIOS ---")
    print(f"Faturamento Total Anual: R$ {total_vendas:,.2f}")
    print(f"Média de Vendas Mensal: R$ {media_mensal:,.2f}")
    print(f"Melhor Mês de Vendas: {melhor_mes} (R$ {maior_valor:,.2f})")
    print("-----------------------------\n")
    
    return df

def gerar_grafico(df):
    plt.figure(figsize=(15, 8))
    plt.bar(df['Mês'], df['Vendas (R$)'], color='darkgreen', edgecolor='black')

    plt.title('Faturamento Mensal (Gráfico)', fontsize=14, fontweight='bold')
    plt.xlabel('Meses (1~12)', fontsize=16)
    plt.ylabel('Faturamento em R$', fontsize=16)
    plt.grid(axis='y', linestyle='--', alpha=0.7)

    plt.show()

criar_planilha_vendas()      
dados_planilha = analisar_dados()
gerar_grafico(dados_planilha)
