# **Documentação da Integração da Magnum com a VTEX**

## Produtos
| Método | URL |
| ----------- | ----------- |
| Post | ```https://i4zgsj0ryh.execute-api.us-east-1.amazonaws.com/default/magnumProductIntegration```

### Criação e atualização de produtos

**Exemplo de envio**
``` json
{
    "product_code": "4987654897432165478",
    "name": "Pneu para caminhão de mineração",
    "description": "Michelin 165/70R14",
    "model": "59/80R63",
    "manufacturer": {
        "code": "Michelin",
        "name": "Michelin"
    },
    "unit_measure": {
        "initials": "UN",
        "description": "unidade"
    },
    "dimensions": {
        "height": 16.5,
        "width": 58.66,
        "length": 58.66,
        "weight": 6.573
    },
    "minimum_quantity": 1,
    "multiple_quantity": 1,
    "multiple": 1,
    "package_quantity": 1,
    "ncm": "40111000",
    "stock_attributes_distribution_center": [
        {
            "dc_code": "2007",
            "quantity": 50,
            "bar_code": "7501720523716"
        }
    ],
	"images":[
		{
			"imageName": "Principal",
			"imageUrl": "https://aecbmesvcm.cloudimg.io/v7/https://cxf-prod.azureedge.net/b2b-experience-production/attachments/cleecwyga05cz01nfpl5s7juj-xdr4-vue-3-4.two-thirds.png"
		}
	],
    "list_price": [
        {
            "current_price": 597,
            "marketplace_scope_code": "LST_GO_0"
        }
    ]
}

```
Exemplo de resposta para que a inclusão foi concluida - **200 OK**

``` json
{
	"ProductId": "",
	"ProductName": "Pneus de carro de passeio",
	"NameComplete": "Pneus de carro de passeio - 165/70R14",
	"ProductDescription": "JKT 165/70R14 VECTRA 81T",
	"BrandName": "JK Tyre",
	"SkuName": "Pneus de carro de passeio - 165/70R14",
	"SellerId": 1,
	"Height": 16.5,
	"Width": 58.66,
	"Length": 58.66,
	"Weight": 6.573,
	"Updated": null,
	"RefId": "REF123",
	"SellerStockKeepingUnitId": "000000000000101098",
	"CategoryFullPath": "",
	"Images": [
		{
			"imageName": "Principal",
			"imageUrl": ""
		}
	],
	"ProductSpecifications": [
		{
			"fieldName": "Fabric",
			"fieldValues": [
				"Cotton",
				"Velvet"
			]
		}
	],
	"SkuSpecifications": [
		{
			"fieldName": "Color",
			"fieldValues": [
				"Red",
				"Blue"
			]
		}
	],
	"EAN": "",
	"MeasurementUnit": "",
	"UnitMultiplier": 1,
	"AvailableQuantity": 50,
	"Pricing": {
		"Currency": "BRL",
		"SalePrice": 376.5,
		"CurrencySymbol": "R$"
	}
}
```

## Orders
| Método | URL |
| ----------- | ----------- |
| GET | ```API/Orders/queue/{status_code}``` | 
| GET | ```API/Orders/{order}``` | 

### Buscar lista de ordens {handling}

Exemplo de resposta com a lista de ordens - **200 OK**

``` json
[
  {
    "order_id": "117245290078801776",
    "site_order_code": "Valor fixo",
    "date": "2025-01-17T11:59:54.409Z",
    "status_code": "handling",
    "protocol": "Não tenho ainda",
    "partner_order_code": "Valor fixo",
    "get_datetime": "2025-01-20T12:47:02.009Z"
  },
  {
    "order_id": "117245290078801790",
    "site_order_code": "Valor fixo",
    "date": "2024-02-04T20:09:43.899958+00:00",
    "status_code": "handling",
    "protocol": "Não tenho ainda",
    "partner_order_code": "Valor fixo",
    "get_datetime": "2025-01-20T12:47:02.009Z"
  },
  {
    "order_id": "11724529007880150",
    "site_order_code": "Valor fixo",
    "date": "2024-02-04T20:09:43.899958+00:00",
    "status_code": "handling",
    "protocol": "Não tenho ainda",
    "partner_order_code": "Valor fixo",
    "get_datetime": "2025-01-20T12:47:02.009Z"
  },
  {
    "order_id": "117245290078801761",
    "site_order_code": "Valor fixo",
    "date": "2025-01-17T11:59:54.409Z",
    "status_code": "handling",
    "protocol": "Não tenho ainda",
    "partner_order_code": "Valor fixo",
    "get_datetime": "2025-01-20T12:47:02.009Z"
  },
  {
    "order_id": "11724529007880199",
    "site_order_code": "Valor fixo",
    "date": "2024-02-04T20:09:43.899958+00:00",
    "status_code": "handling",
    "protocol": "Não tenho ainda",
    "partner_order_code": "Valor fixo",
    "get_datetime": "2025-01-20T12:47:02.009Z"
  }
]
```
### Buscar lista de ordens {117245290078801776}

```
{
  "note_observation": "string",
  "discount_value": 0,
  "affiliate_order": true,
  "delivery_forecast": "2024-03-09T10:13:40.1020453+00:00",
  "tracking": [
    {
      "carrier": "Rodonaves Transportes e Encomendas LTDA",
      "carrier_document": "44.914.992/0001-38",
      "tracking_code": "701-1947797-1739404_DBA",
      "tratracking_link": "https://storeName.vtexcommercestable.com.br/api/integration-amazon/logistic-program/dba/labels?orderId=d9xsHobRJCIWbbub0"
    }
  ],
  "status_description": "Preparando Entrega",
  "intermediate_registration_id": "string",
  "document_payment_institution": "string",
  "delivery_shedule": [
    {
      "field_description": "Enderço de entrega",
      "field_name": "delivery_address",
      "field_value": "Avenida Lúcio Costa,126 - Rio de Janeiro, null"
    }
  ],
  "discount_list": [],
  "status_record": "{"purchased_at":"2024-02-04T20:09:43.899958+00:00"}",
  "partner_order_code": "1172452900788-01",
  "payment": { "plot_amount": 0, "flag": "string", "payment_options": "string" },
  "document_intermediator": "4574467654",
  "total_amount_undiscounted": 39.9,
  "xped": "string",
  "shipping_company": "Rodonaves Transportes e Encomendas LTDA",
  "delivery_forecast_mplace": "2024-03-09T10:13:40.1020453+00:00",
  "tracking_code": "string",
  "site_order_code": "string",
  "items": [
    {
      "sku_seller_id": "fixo",
      "sku_partner_id": "fixo",
      "quantity": 0,
      "quantity_gift": 0,
      "sale_price_undiscounted": 39.9,
      "price_without_current_tax": 39.9,
      "discount": {},
      "sale_price": 0,
      "discount_list": [],
      "freight_value": 3000,
      "variation_option_id": 0
    }
  ],
  "freight_value": 30,
  "status_code": "handling",
  "order_date": "2024-02-04T20:09:43.899958+00:00",
  "effective_delivery_date": "2025-01-17T11:59:54.410Z",
  "tax_engine": "string",
  "customer": {
    "name": "Rodrigo Smith",
    "gender": '',
    "type": 'cpf',
    "document_number": "845.134.270-19",
    "identity_number": "845.134.270-19",
    "email": "rodrigo.smith@email.com",
    "corporate_name": null,
    "state_registration": null,
    "born_at": '',
    "billing": {
      "postal_code": "22630-011",
      "address": "Avenida Lúcio Costa",
      "number": "126",
      "complement": "10",
      "city": "Rio de Janeiro",
      "city_ibge_code": "04557",
      "neighborhood": "Barra da Tijuca",
      "reference": "apartment",
      "country_id": "BRA",
      "state": "RJ"
    },
    "phones": { "office": "+5561992227222", "mobile": "+5561992227222" }
  },
  "order_id": "11724529007880199",
  "invoice": "string",
  "total_amount": 39.9,
  "delivery_address": {
    "postal_code": "22630-011",
    "address": "Avenida Lúcio Costa",
    "number": "126",
    "complement": "126",
    "city": "Rio de Janeiro",
    "city_ibge_code": null,
    "neighborhood": "Barra da Tijuca",
    "reference": "apartment",
    "country_id": "BRA",
    "state": "RJ"
  }
}
```
