Automação de Relatórios e Geração de Gráficos (Python & Excel).

Este projeto demonstra a integração prática entre Python e Excel para automatizar tarefas comuns de análise de dados. O script cria uma planilha de vendas do zero, exporta os dados para um arquivo real do Excel (`.xlsx`) e, em seguida, consome esse arquivo para gerar um gráfico de barras altamente legível e estilizado.

Quais foram as Tecnologias Utilizadas?
Python 3
Pandas: Para a criação, manipulação e exportação da tabela de dados de forma estruturada.

Matplotlib: Para a plotagem e customização visual do gráfico de faturamento mensal.

OpenPyXL: Engine utilizada em segundo plano para gravação de arquivos Excel.

Como o Projeto Funciona?
1. Geração de Dados: O script simula uma tabela com o faturamento mensal de Janeiro a Dezembro.
2. Exportação para Excel: Os dados são estruturados em um DataFrame do Pandas e salvos automaticamente no arquivo `relatorio_vendas.xlsx`.
3. Análise Visual: O Python lê a planilha gerada e desenha um gráfico de barras customizado (utilizando a paleta de cores `darkgreen` e tamanho otimizado de tela) para facilitar a tomada de decisão.

Como Executar?

Você pode rodar este projeto localmente ou diretamente no Google Colab:

1. Copie o código presente no arquivo `main.py` deste repositório.
2. Certifique-se de ter as bibliotecas instaladas executando:
   ```bash
   pip install pandas matplotlib openpyxl    maior_valor = df['Vendas (R$)'].max()
    
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
