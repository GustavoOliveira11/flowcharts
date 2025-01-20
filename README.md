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

Exemplo de resposta para que a inclusão foi concluida - **200 OK**

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
    "date: "2024-02-04T20:09:43.899958+00:00",
    "status_code": "handling",
    "protocol": "Não tenho ainda",
    "partner_order_code": "Valor fixo",
    "get_datetime": "2025-01-20T12:47:02.009Z"
  }
]
```
