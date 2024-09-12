# Say Cheese
A RESTful API with over 1800 cheeses.  
Originally made by [IllusionMan1212](https://github.com/IllusionMan1212/say-cheese), this is a fork with minor modifications.  

<br>

### Table of Contents:
- [Introduction](#introduction)
- [Routes](#routes)
    - [Parameters](#parameters)
- [Example Success Response](#example-success-response)
- [Example Error Response](#example-error-response)
- [Status Codes](#status-codes)
- [Field Values](#field-values)
    - [`country_codes`](#country_codes-values)
    - [`milks`](#milks-values)
    - [`types`](#types-values)
    - [`textures`](#textures-values)
    - [`color`](#color-values)
- [Notes about the returned data](#notes-about-the-returned-data)

<br>

## Introduction:
You can reach this API under the base URL `https://api.sv443.net/cheese/`  
  
The API is limited to 30 requests per minute per client to prevent abuse and because my server can't handle it lol.

<br>

## Routes:
| Route | Parameters | Description |
| :-- | :-- | :-- |
| `/random` | None | Returns a random cheese |
| `/search` | `q`, `page`, `per_page` | Search for cheeses by name |
| `/today` | None | Returns cheese of the day |
| `/alphabetical` | `letter`, `page`, `per_page` | Find cheeses by their first letter |
| `/vegetarian` | `page`, `per_page` | Returns an array of all vegetarian cheeses |

<br>

### Parameters:
| Parameter | Description |
| :-- | :-- |
| `q` | (required) The search query you want to perform. |
| `letter` | (required) The letter you want to display the cheeses for. |
| `page?` | Pagination number. (default = 1) |
| `per_page?` | Number of cheeses to display in a single page. (max = 50; default = 10) |

<br>

## Example Success Response:
```json
{
    "failed": false,
    "status": "200",
    "cheese": {
        "country_codes": ["IT"],
        "milks": ["sheep"],
        "name": "Pecorino dei Malatesta al Sangiovese",
        "link": "https://cheese.com/pecorino-dei-malatesta-al-sangiovese/",
        "image": "https://cheese.com/media/img/icon-cheese-default.svg",
        "description": "Produced by Romaniae Terrae, Pecorino dei Malatesta al Sangiovese is an Italian cheese made with highly selected sheep's milk pasteurized at optimum temperature. Cheese wheels are first matured in a cold room at 6° - 8°C. Later, during the final stage of maturation they are treated with Sangiovese red wine and kept in a cold room at 8°C for about 30 days.The Sangiovese red wine gives the cheese a dark burgundy rind beneath which lies a smooth white paste with a delicate mouthfeel and a sweet sheep's milk flavour with an aftertaste of wine.",
        "attributes": {
            "made": "Made from pasteurized sheep's milk",
            "countries": ["Italy"],
            "region": "Emilia-Romagna",
            "family": "Pecorino",
            "types": ["semi-soft","artisan"],
            "fat": null,
            "calcium": null,
            "textures": ["smooth"],
            "rind": "natural",
            "color": "white",
            "flavors": ["acidic","smooth","subtle","sweet"],
            "aromas": ["pleasant"],
            "vegetarian": null,
            "producers": ["Romaniae Terrae"],
            "synonyms": [],
            "alternative_spellings": []
            },
        "id": 1273
    }
}
```

| Property | Description |
| --- | --- |
| `failed` | Whether the request failed or not (boolean) |
| `status` | HTTP status code |
| `cheese` | Cheese object |
| `id` | Unique cheese id |

<br>

## Example Error Response:
```json
{
    "failed": true,
    "status": "400",
    "error": "Error message"
}
```

| Property | Description |
| --- | --- |
| `failed` | Whether the request failed or not (boolean) |
| `status` | HTTP status code |
| `error` | Error message |

<br>

## Status Codes:
| Code | Description |
| :-- | :-- |
| `200` (OK) | The request was successful and that is returned. |
| `304` (Not Modified) | You already have the latest data. |
| `400` (Bad Request) | You submitted an invalid or incomplete request. |
| `404` (Not Found) | The requested data does not exist. |
| `500` (Internal Server Error) | Something went wrong on our end, please open an issue on the [github](https://github.com/Sv443/say-cheese/issues) if this persists. |

<br>

## Field Values:

### `country_codes` values:
| Code | Country |
| :-- | :-- |
| `AD` | Andorra |
| `AF` | Afghanistan |
| `AL` | Albania |
| `AM` | Armenia |
| `AR` | Argentina |
| `AT` | Austria |
| `AU` | Australia |
| `AZ` | Azerbaijan |
| `BD` | Bangladesh |
| `BE` | Belgium |
| `BG` | Bulgaria |
| `BR` | Brazil |
| `BY` | Belarus |
| `CA` | Canada |
| `CH` | Switzerland |
| `CL` | Chile |
| `CN` | China |
| `countries-throughout-world` | Other Countries |
| `CY` | Cyprus |
| `CZ` | Czech Republic |
| `DE` | Germany |
| `DK` | Denmark |
| `eastern-mediterranean` | Eastern Mediterranean |
| `EG` | Egypt |
| `england` | England |
| `ES` | Spain |
| `FI` | Finland |
| `FR` | France |
| `GB` | United Kingdom |
| `GE` | Georgia |
| `GR` | Greece |
| `great-britain` | Great Britain |
| `holland` | Holland |
| `HR` | Croatia |
| `HU` | Hungary |
| `IE` | Ireland |
| `IL` | Israel |
| `IM` | Isle of man |
| `IN` | India |
| `IQ` | Iraq |
| `IR` | Iran |
| `IS` | Iceland |
| `IT` | Italy |
| `JO` | Jordan |
| `JP` | Japan |
| `LB` | Lebanon |
| `LT` | Lithuania |
| `mexico-and-caribbean` | Mexico and Caribbean |
| `middle-east` | Middle East |
| `MK` | Macedonia |
| `MN` | Mongolia |
| `MR` | Mauritania |
| `MX` | Mexico |
| `NL` | Netherlands |
| `NO` | Norway |
| `NP` | Nepal |
| `NZ` | New zealand |
| `PK` | Pakistan |
| `PL` | Poland |
| `PS` | Palestine |
| `PT` | Portugal |
| `RO` | Romania |
| `RS` | Serbia |
| `RU` | Russia |
| `scotland` | Scotland |
| `SE` | Sweden |
| `SK` | Slovakia |
| `SY` | Syria |
| `SZ` | Swaziland |
| `tibet` | Tibet |
| `TR` | Turkey |
| `UA` | Ukraine |
| `US` | United States |
| `wales` | Wales |

### `milks` values:
`buffalo`, `camel`, `cow`, `donkey`, `goat`, `mare`, `moose`, `reindeer`, `sheep`, `water-buffalo`, `yak`

### `types` values:
`artisan`, `blue-veined`, `fresh-soft`, `fresh-firm`, `soft`, `semi-soft`, `semi-hard`, `hard`, `semi-firm`, `firm`

### `textures` values:
`brittle`, `buttery`, `chalky`, `chewy`, `close`, `compact`, `creamy`, `crumbly`, `crystalline`, `dense`, `dry`, `elastic`, `firm`, `flaky`, `fluffy`, `grainy`, `oily`, `open`, `runny`, `semi-firm`, `smooth`, `soft`, `soft-ripened`, `spreadable`, `springy`, `sticky`, `stringy`, `supple`

### `color` values:
`blue`, `blue-grey`, `brown`, `brownish-yellow`, `cream`, `golden-orange`, `golden-yellow`, `green`, `ivory`, `orange`, `pale-white`, `pale-yellow`, `pink-and-white`, `red`, `straw`, `white`, `yellow`

<br>

## Notes about the returned data:
- Any property that does not exist or has an undetermined value will default to `null`
- Any array property that does not exist or has an undetermined value will be an empty array (`[]`)
