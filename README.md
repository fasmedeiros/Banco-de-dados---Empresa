# Banco-de-dados---Empresa

````mermaid
+-------------------+          +-------------------+
|       Dept        |          |        Emp         |
+-------------------+          +-------------------+
| PK DepNume        | 1       N | PK EmpNume        |
| DepNome           |<---------| EmpNome           |
| DepLoca           |          | EmpGere           |  
| DepOrca           |          | FK DepNume        |
+-------------------+          | EmpAdmi           |
                               | EmpSala           |
                               | EmpComi           |
                               +-------------------+
                               | FK EmpGere        |
                               +-------------------+
