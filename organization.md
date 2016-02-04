# Organization

## 1 Usage Examples
This section is non-normative.

This section shows how developers can make use of the features of this specification.

### 1.1 Example JSON

```json
{
    "id": "999999",
    "name": {
        "long": "Cuyahoga County Public Library",
        "short": "CCPL"
    },
    "web_address": "http://www.findaway.com",
    "currency": "USD",
    "ils_enabled": false,
    "price_contracts": {
        "playaway_light": 0.25,
        "playaway_view": 0.05,
        "playaway_bookpacks": 0.05,
        "playaway_launchpad": 0.0,
        "accessory": 0.25,
        "service": 0.25,
        "recorded_books": 0.05
    },
    "category": "findaway_direct",
    "shipping_address": {
        "street": ["2111 Snow Road"],
        "city": "Parma",
        "region": "US-OH",
        "postal_code": "44134",
        "country": "US"
    },
    "biling_address": {
        "street": ["2111 Snow Road"],
        "city": "Parma",
        "region": "US-OH",
        "postal_code": "44134",
        "country": "US"
    },
    "phone_number": "2222222222",
    "fax_number": "2222222222",
    "federal_tax_id": "123456789",
    "tax_exempt": true,
    "tax_exempt_number": "123456789",
    "notes": "",
}
```

## 2 Organization and its members

### 2.1 `id` member
The `id` member is a __String__ [Universally unique identifier](https://en.wikipedia.org/wiki/Universally_unique_identifier) (UUID). Meant to represent a canonical ID for the Organization.

### 2.2 `name` member
The `name` member is an __Object__ that represents the Organization's naming information.

#### 2.2.1 `long` member
The `long` member represents the full name of the Organization.

#### 2.2.2 `short` member
The `long` member represents the short or abbreviated name of the Organization. This is provided for use when the full (long) name is not appropriate.

### 2.3 `currency` member
The `currency` member is a __String__ that represents the Organization's default currency as [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) alphabetic code.

### 2.4 `ils_enabled` member
The `ils_enabled` member is a __Boolean__ that identifies if the Organization has ILS grid ordering enabled. If this value is _false_ then it overrides any `ils_enabled` value for the [Customer](customer.md).

### 2.5 `price_contracts` member
The `price_contracts` member is an __Object__ of _key:value_ pairs that identify the price contract discounts for zero or more product types. Each _key_ is a [Product](product.md) `format` member value, and its _value_ is the discount amount as a decimal __Float__.

### 2.6 `category` member
The `category` member is a __String__ that represents the organization type. This value should be all lowercase with special characters removed and spaces converted to underscores.

### 2.7 `address` member
The `address` member is an __Object__ that represents the organization's main address.

#### 2.7.1 `street` member
The `street` member is an __Array__ that contains all street related information for the address. Each street line is a separate item int the __Array__.

#### 2.7.2 `city` member
The `city` member is a __String__ that represents the city name.

#### 2.7.3 `region` member
The `region` member is a __String__ that represents the [ISO 3166-2](https://en.wikipedia.org/wiki/ISO_3166-2) region (subdivision) abbreviation.

#### 2.7.4 `postal_code` member
The `postal_code` member is a __String__ that represents the postal code for the region.

#### 2.7.5 `country` member
The `country` member is a __String__ that represents the [ISO 3166-1](https://en.wikipedia.org/wiki/ISO_3166-2) country abbreviation.
