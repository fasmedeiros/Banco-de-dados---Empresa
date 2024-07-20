# Banco-de-dados---Empresa


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

```mermaid
erDiagram
    Dept {
        int DepNume PK "Número do Departamento"
        string DepNome "Nome do Departamento"
        string DepLoca "Localização do Departamento"
        int DepOrca "Orçamento do Departamento"
    }
    Emp {
        int EmpNume PK "Número do Empregado"
        string EmpNome "Nome do Empregado"
        int EmpGere FK "Número do Gerente"
        string EmpServ "Serviço do Empregado"
        int DepNume FK "Número do Departamento"
        date EmpAdmi "Data de Admissão"
        int EmpSala "Número da Sala"
        int EmpComi "Comissão"
    }

    Dept ||--o{ Emp : "Contém"
    Emp ||--o| Emp : "Gerenciado por"
    Emp }o--|| Dept : "Pertence a"
