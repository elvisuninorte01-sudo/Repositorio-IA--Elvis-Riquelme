Sistema Inteligente Multiagente para Gestión y Recuperación de Tickets de Soporte mediante Embeddings y FAISS

Agente 1: Normalizador

Carga el dataset. Detecta valores nulos. Detecta duplicados. Limpia texto. Genera un dataset limpio.

===== ANALISIS INICIAL =====
Filas y columnas: (8469, 17)

Valores nulos:
Ticket ID                          0
Customer Name                      0
Customer Email                     0
Customer Age                       0
Customer Gender                    0
Product Purchased                  0
Date of Purchase                   0
Ticket Type                        0
Ticket Subject                     0
Ticket Description                 0
Ticket Status                      0
Resolution                      5700
Ticket Priority                    0
Ticket Channel                     0
First Response Time             2819
Time to Resolution              5700
Customer Satisfaction Rating    5700
dtype: int64

Duplicados:
0

===== DATASET NORMALIZADO =====
(8469, 17)


Agente 2: Entrenador

Recibe el dataset limpio. Genera embeddings con un Transformer. Construye la base vectorial FAISS.

Pasos realizados

1-Crear texto para los embeddings


0	product setup i'm having an issue with the {pr...
1	peripheral compatibility i'm having an issue w...
2	network problem i'm facing a problem with my {...
3	account access i'm having an issue with the {p...
4	data loss i'm having an issue with the {produc...

dtype: object

2-Instalar librerías del Agente Entrenador
3-Importar librerías
4-Cargar Transformer

Modelo utilizado:
all-MiniLM-L6-v2

Transformer cargado correctamente.

5-Generar embeddings

(8469, 384)
6-Crear Base Vectorial

Vectores almacenados:
8469
7-Implementar búsqueda RAG

[[6600 1816  160 3386  640]]
8-Mostrar resultados recuperados
============================================================
TIPO:
cancellation request

ASUNTO:
account access

DESCRIPCION:
i'm facing issues logging into my {product_purchased} account. it says my account is locked. what should i do to unlock it?

you should open the account immediately and log in, either with username/password or on i've followed online tutorials and community forums to troubleshoot the issue, but no luck so far.
============================================================
TIPO:
product inquiry

ASUNTO:
account access

DESCRIPCION:
i'm facing issues logging into my {product_purchased} account. it says my account is locked. what should i do to unlock it?

the first step is to create a new account using your user name or a password you i've tried troubleshooting steps mentioned in the user manual, but the issue persists.
============================================================
TIPO:
refund request

ASUNTO:
account access

DESCRIPCION:
i'm facing issues logging into my {product_purchased} account. it says my account is locked. what should i do to unlock it?

open the account. you'll find everything you need to do. the next step is i've reviewed the troubleshooting steps on the official support website, but they didn't resolve the problem.
============================================================
TIPO:
technical issue

ASUNTO:
account access

DESCRIPCION:
i'm facing issues logging into my {product_purchased} account. it says my account is locked. what should i do to unlock it?

the solution

start by authenticating with your account provider. it has a couple i've checked the device settings and made sure that everything is configured correctly.
============================================================
TIPO:
technical issue

ASUNTO:
hardware issue

DESCRIPCION:
i'm unable to access my {product_purchased} account. it keeps displaying an 'invalid credentials' error, even though i'm using the correct login information. how can i regain access to my account?

when you i need assistance as soon as possible because it's affecting my work and productivity.

Agente 3: Comunicador Recupera información relevante. Genera un reporte en lenguaje natural.

===== REPORTE GENERAL =====

Cantidad total de tickets:
8469

Tipos de ticket:
Ticket Type
refund request          1752
technical issue         1747
cancellation request    1695
product inquiry         1641
billing inquiry         1634
Name: count, dtype: int64

Prioridades:
Ticket Priority
medium      2192
critical    2129
high        2085
low         2063
Name: count, dtype: int64

Estados:
Ticket Status
pending customer response    2881
open                         2819
closed                       2769
Name: count, dtype: int64

Evaluación del Sistema
Componente	Resultado
Dataset inicial	8469 tickets
Dataset normalizado	8469 tickets
Valores duplicados detectados	0
Embeddings generados	8469
Dimensión de los embeddings	384
Vectores almacenados en FAISS	8469
Consulta de prueba	"cannot login to my account"
Tickets recuperados	5 resultados relevantes

Análisis de Resultados

El sistema procesó correctamente 8469 tickets de soporte. La etapa de normalización permitió identificar valores faltantes y verificar la inexistencia de registros duplicados. Posteriormente, se generaron embeddings de 384 dimensiones mediante el modelo all-MiniLM-L6-v2 y se almacenaron en una base vectorial FAISS.

La búsqueda semántica realizada con la consulta "cannot login to my account" recuperó cinco tickets relacionados con problemas de acceso a cuentas, demostrando la efectividad del sistema para encontrar incidencias similares mediante similitud semántica.


Conclusión

Se desarrolló un sistema multiagente basado en inteligencia artificial capaz de normalizar datos, generar representaciones semánticas mediante embeddings y recuperar información relevante utilizando una base vectorial FAISS. Los resultados obtenidos demuestran que la solución permite mejorar la gestión y análisis de tickets de soporte mediante técnicas modernas de procesamiento de lenguaje natural y búsqueda semántica.



