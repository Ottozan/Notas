```python
import os, pathlib

os.chdir('/hs/pro')
programas = sorted(pathlib.Path('.').glob('**/*.cbl'))
for programa in programas:
    nm_programa = programa.name
    modulo = nm_programa[0:3]
    print(programa, modulo)
    with open(programa) as file:
        linhas = file.readlines()
        num_linha = 0
        linha_remarks = 0
        for linha in linhas:
            num_linha += 1
            if num_linha > 15:
                break
            if "REMARKS" in linha:
                linha_remarks = num_linha + 1
            if num_linha == linha_remarks:
                print(f"{programa};{modulo};{linha.strip()}")
                break

```



```python
import sys

if __name__ == '__main__':
    if len(sys.argv) < 2:
        print(f"Uso: {sys.argv[0][2:]} <argumento>")
        sys.exit(1) # sai do script
    else:
        for argumento in sys.argv:
            print(argumento)
print(sys.argv)
```



```python
import mysql.connector
import os, pathlib, sys
from mysql.connector import Error

connection = mysql.connector.connect(host='localhost',
                                     database='hs',
                                     user='root',
                                     password='',
                                     port='3307')

cursor = connection.cursor()

def data_ymd(dt_dmy):
    if dt_dmy == '00000000':
        return 'null'
    if len(dt_dmy) != 8:
        return 'null'
    dt_ymd = dt_dmy[-4:]+'-'+dt_dmy[2:4]+'-'+dt_dmy[:2]
    return f"'{dt_ymd}'"

def is_null(var1):
   if var1:
      return f"'{var1}'"
   else:
      return 'null'

def if_null_zero(var1):
   if var1:
      return f"{var1}"
   else:
      return 0




contador = 0
caminho = sys.argv[1]
os.chdir(caminho)
programas = sorted(pathlib.Path('.').glob('**/*.cbl'))
for programa in programas:
    nm_programa = programa.name.split('.')[0]
    modulo = nm_programa[0:3]
    #print(programa, modulo)
    with open(programa, encoding='ansi') as file:
        linhas = file.readlines()
        num_linha = 0
        linha_remarks = 0
        for linha in linhas:
            num_linha += 1
            if num_linha > 15:
                break
            if "REMARKS" in linha:
                linha_remarks = num_linha + 1
            if num_linha == linha_remarks:
               descricao = linha.strip()
               descricao = descricao.replace("'"," ")
               sql = f"INSERT INTO programa(" + \
                  "programa,nm_modulo,descr_resumida)" + \
                  f" values('{nm_programa}','{modulo}','{descricao}')"
               print(f'Sql: {sql}')
               try:
                  cursor.execute(sql)
               except:
                  print(f'Nao foi possivel executar {sql}')
               #print(f"{nm_programa};{modulo};{linha.strip()}")
               contador += 1
               break

print(f"{contador} arquivos encontrados")


#cursor.close()
connection.commit()
connection.close()
```

```python
import json
import pandas as pd
import csv

# Read the data from file
# We now have a Python dictionary
with open('data.json') as f:
    data_listofdict = json.load(f)
    
# Writing a list of dicts to CSV
keys = data_listofdict[0].keys()
with open('saved_data.csv', 'wb') as output_file:
    dict_writer = csv.DictWriter(output_file, keys)
    dict_writer.writeheader()
    dict_writer.writerows(data_listofdict)
```

