
```mermaid
    erDiagram
        STAFF {
            int id pk
            int provider_id fk
            int address_id fk
            string name
            string mobile
            string citizen_id
        }
        PROVIDERS {
            int id pk
            int address_id fk
            string name
            string mobile
        }
        CAR_MODELS {
            int id pk
            int brand_id fk
            string name
            string type
            double battery_capacity
            double battery_range
            string connector_type
        }
        CAR_BRAND {
            int id pk
            string name
        }
        FACILITIES {
            int id pk
            int nearby_charger_id fk
            string name
            point location
            string type
            float rating
        }
        CHARGERS {
            int id pk
            string name
            double price
            string type
            int charging_speed
            string connector_type
            string status
        }
        STATIONS {
            int id pk
            int provider_id fk
            string name
            point location
            double rating
        }
        ADDRESS {
            int id
            string name
            string postal_code
            string country
            string province
            string district
            string subdistrict
            string street
            string house_no
        }

        STAFF o{--|| PROVIDERS : contains
        STATIONS |{--|| PROVIDERS : contains
        CAR_MODELS |{--|| CAR_BRAND : has
        STATIONS ||--o{ FACILITIES : has
        CHARGERS |{--|| STATIONS : has
        STAFF ||--|| ADDRESS : has
        PROVIDERS ||--|| ADDRESS : has
```     
