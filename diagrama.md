```mermaid
erDiagram
    ANIMALS ||--o| OWNERS : "owned by"
    ANIMALS ||--o| SPECIES : "belongs to"
    SPECIALIZATIONS ||--o| VETS : "specialized by"
    SPECIALIZATIONS ||--o| SPECIES : "for"
    VISITS ||--o| VETS : "conducted by"
    VISITS ||--o| ANIMALS : "conducted for"
    
    ANIMALS {
        int ID PK
        string name
        int escape_attempts
        bit neutered
        decimal weight_kg
        int species_id FK
        int owner_id FK
    }
    OWNERS {
        int ID PK
        string full_name
        int age
    }
    SPECIALIZATIONS {
        int vets_id FK
        int species_id FK
    }
    SPECIES {
        int ID PK
        string name
    }
    VETS {
        int ID PK
        string name
        int age
    }
    VISITS {
        int vets_id FK
        int animals_id FK
    }
