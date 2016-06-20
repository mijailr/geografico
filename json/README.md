Geográfico de Venezuela en JSON
===

Aquí están los geográficos por estados, municipios y parroquias pesado para MongoDB pero es utilizable con cualquier otra base de datos SQL o NOSQL.

Para MongoDB puedes importar usando `mongoimport`
```
mongoimport --db geo_development --collection parroquias --file json/parroquias.json --jsonArray
```

Estados(24)
---
- **\_id:** Del tipo entero ordenado según como lo usa el INE
- **nombre:** El nombre del estado.

  ```
  {
      "_id": 1,
      "nombre": "Distrito Capital"
  }
  ```

Municipios(335):
---
- **\_id:** Del tipo entero ordenado de manera ascendente por el \_id del estado
- **estado_id:** Relacionado con el \_id del estado correspondiente
- **nombre:** El nombre del municipio
- **ine_municipio:** Del tipo entero ordenado según como lo usa el INE

  ```
  {
  	"_id": 315,
  	"estado_id": 21,
  	"nombre": "Rosario de Perijá",
  	"ine_municipio": 13
  }
  ```

Parroquias(1135)
---
- **\_id:** Del tipo entero ordenado de manera ascendente por el \_id del estado y el \_id del municipio
- **estado_id:** Relacionado con el \_id del estado correspondiente
- **municipio_id:** Relacionado con el \_id del municipio correspondiente
- **nombre:** El nombre de la parroquia.
- **ine_municipio:** ID del municipio del tipo entero ordenado según como lo usa el INE
- **ine_parroquia:** ID de la parroquia del tipo entero ordenado según como lo usa el INE

  ```
  {
  	"_id": 838,
  	"estado_id": 18,
  	"municipio_id": 257,
  	"nombre": "Cordero ",
  	"ine_municipio": 18,
  	"ine_parroquia": 1
  }
  ```
