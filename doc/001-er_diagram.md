# ER図

``` mermaid
erDiagram
    postal_codes }|--|{ administrative_units: "郵便番号と行政区分は多対多"
    administrative_units }|--|| municipalities: "行政区分と市町村は多対1"
    municipalities }|--|| prefectures: "市町村と都道府県は多対1"
    
    postal_codes {
        string postal_code PK "郵便番号"
    }
    
    administrative_units {
        bigint id PK "行政単位ID"
        string name "行政単位名"
        bigint parent_id FK "親行政単位ID"
    }
    
    municipalities {
        bigint id PK "市町村ID"
        string name "市町村名"
    }
    
    prefectures {
        bigint id PK "都道府県ID"
        string name "都道府県名"
    }
    
```
