*   Migrate from the dirty current schemas to [standard JSON schema](http://json-schema.org) 
    by following [draft-04 specification](http://json-schema.org/draft-04/schema).

*   Improve the current json-documents schemas by adding additional 
    (`description`, `default`, `minItems`, `minimum`, `uniqueItems`, `required`, `items` and `enum`) properties.
    For more information about this properties refer to the [link](http://json-schema.org/documentation.html). 

    e.g.
    ```json
        {
            "$schema": "http://json-schema.org/draft-04/schema#",
            "title": "Product",
            "description": "A product from Acme's catalog",
            "type": "object",
            "properties": {
                "id": {
                    "description": "The unique identifier for a product",
                    "type": "integer"
                },
                "name": {
                    "description": "Name of the product",
                    "type": "string"
                },
                "price": {
                    "type": "number",
                    "minimum": 0,
                    "exclusiveMinimum": true
                },
                "tags": {
                    "type": "array",
                    "items": {
                        "type": "string"
                    },
                    "minItems": 1,
                    "uniqueItems": true
                }
            },
            "required": ["id", "name", "price"]
        }
    ```

*   Add `ad` document's property for a negotiable, free, paid, etc ad's type.

*   Add `placement_period` property to `ad` document for holding time period.
    e.g. a day, a week, 2 weeks, a month, 2 months, ...

*   Add sample data with utility test validation for the schemas.
    For more information about the utility refer to the [link](http://json-schema.org/implementations.html)

*   Rename project to `elasticad-json-schemas`.

*   Add example samples for each schema definitions.
    e.g. For `ad` document.
    ```json
    {
      "taxon_id": ObjectId("5280afc77562003afc0e0000"),
      "title": "Book by Ruby on Rails programming",
      "description": "Wonderful book written by smarter authors",
      "type": "FOR_SALE",
      "placement_period": "2.weeks",
      "activation_hash": "5280afc77562003afc0e0000"
    }
    ```
