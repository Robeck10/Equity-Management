# Equity-Management
In this repository i coulbd save the work makes from Equity Management, MSc of Finance in UAI.

# 
*TAREA 2*

import pandas as pd
import matplotlib.pyplot as plt

# Cargar el archivo
ff_data = pd.read_csv('F-F_Research_Data_Factors.csv', skiprows=2)

# Filtrar solo las filas válidas con fechas en formato YYYYMM
ff_data = ff_data[ff_data['Unnamed: 0'].str.match(r'^\d{6}$', na=False)]

# Crear columna de fechas reales
ff_data['Date'] = pd.to_datetime(ff_data['Unnamed: 0'], format='%Y%m')
ff_data = ff_data.drop(columns=['Unnamed: 0'])

# Convertir columnas numéricas a float
for col in ['Mkt-RF', 'SMB', 'HML', 'RF']:
    ff_data[col] = pd.to_numeric(ff_data[col], errors='coerce')

# Calcular el retorno del mercado Rm
ff_data['Rm'] = ff_data['Mkt-RF'] + ff_data['RF']

# Ver los primeros datos
ff_data.head()


#*Visualizar los datos gráficamente

plt.figure(figsize=(12,6))
plt.plot(ff_data['Date'], ff_data['Mkt-RF'], label='Mkt_RF')
plt.plot(ff_data['Date'], ff_data['SMB'], label='SMB')
plt.plot(ff_data['Date'], ff_data['HML'], label='HML')
plt.title('Factores Fama-French')
plt.xlabel('Fecha')
plt.ylabel('Retorno (%)')
plt.legend()
plt.grid(True)
plt.tight_layout()
plt.show()


