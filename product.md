# Product

## 1 Usage Examples
This section is non-normative.

This section shows how developers can make use of the features of this specification.

### 1.1 Example JSON

```json
{
    "id": "cf230493-3c8c-459b-a99b-30b137b350cd",
    "title": "The Hunger Games",
    "author": [
        "Suzanne Collins"
    ],
    "narrator": [
        "Carolyn McCormick"
    ],
    "description": "Katniss is a 16-year-old girl living with her mother and younger sister in the poorest district of Panem, the remains of what used be the United States. Long ago the districts waged war on the Capitol and were defeated. As part of the surrender terms, each district agreed to send one boy and one girl to appear in an annual televised event called, \"The Hunger Games.\" The terrain, rules, and level of audience participation may change but one thing is constant: kill or be killed. When Kat's sister is chosen by lottery, Kat steps up to go in her place. You can also buy this title as part of a series collection. Please search \"Hunger Games Trilogy\" to buy the entire series at a discounted rate!",
    "slug": "the-hunger-games",
    "isbn": 9781606406823,
    "sku": "2846",
    "publisher": [
        "Scholastic"
    ],
    "audience": "Young Adult",
    "age_level": [18,35],
    "grade_level": [6,12],
    "genre": ["Fiction", "Young Adult", "Science Fiction"],
    "abridgment": "Unabridged",
    "duration": "11:10:57",
    "release_date": "2008-10-01",
    "series": "Hunger Games Trilogy",
    "price" : 74.99,
    "release_type": "Simultaneous Release with Audio",
    "awards": [],
    "is_available": true,
    "format": "playaway_light",
    "package_type": null,
    "package_size": null
}
```

## 2 Product and its members

### 2.1 `id` member
The `id` member is a __String__ [Universally unique identifier](https://en.wikipedia.org/wiki/Universally_unique_identifier) (UUID). Meant to represent a canonical ID for the Product.

### 2.2 `title` member
The `title` member is a __String__ that represents the product title.

### 2.3 `author` member
The `author` member is an __Array__ with one or more author names as __String__.
_Note: should this be a more verbose object? should we link to an Author record?_

### 2.4 `narrator` member
The `narrator` member is an __Array__ with one or more narrator names as __String__.
_Note: should this be a more verbose object? should we link to an Narrator record?_

### 2.5 `description` member
The `description` member is a __String__ of the Product's description.
_Note: should this be Markdown? HTML? Plain Text?_

### 2.6 `slug` member
The `slug` member is a __String__ that represents a unique URL path for the Product. The slug should be created using the `title` member. All characters should be lowercase and all non word characters be converted to hyphen.

### 2.7 `isbn` member
The `isbn` member is an __Integer__ that represents the Product's ISBN number. If the Product does not have an ISBN this value should be __null__.

### 2.8 `sku` member
The `sku` member is a __String__ that represents the unique Product SKU. Because not all product types use numeric SKUs this is a string to create consistency.

### 2.9 `publisher` member
The `publisher` member is an __Array__ of one or more __Strings__ that represent a publisher. This member represents "studio" for video or application content.
_Note: should this be a more verbose object? should we link to an Publisher record?_

### 2.10 `audience` member
The `audience` member is a __String__ that represents the "human readable" name for the Product's intended audience.

### 2.11 `age_level` member
The `age_level` member is an __Array__ that contains one or more values. The values in the array represent the low and high values of the level range. The value at index 0 is the lowest, and value at index 1 is the highest. If only one value is provided the high value is infinity.

### 2.11 `grade_level` member
The `grade_level` member is an __Array__ that contains one or more __Integer__ values. The values in the array represent the low and high values of the level range. The value at index 0 is the lowest, and value at index 1 is the highest. If only one value is provided the high value is infinity.

### 2.12 `genre` member
The `genre` member is an __Array__ that contains one or more __String__ values. The values represent the name of a genre.
_Note: should this link to a Genre record?_

### 2.13 `abridgement` member
The `abridgement` member is a __String__ that represents the abridgement type of the Product.

### 2.14 `duration` member
The `duration` member is a __String__ that represents the total playing time of the Product in "hh:mm:ss" format.

### 2.15 `release_date` member
The `release_date` member is a __String__ that represents the ISO 8601 formatted date of release for the Product.

### 2.16 `series` member
The `series` member is a __String__ that represents the title of the series the Product belongs to. If the Product does not belong to a series this value should be __null__.

### 2.17 `price` member
The `price` member is a __Float__ that represents the base price of the Product. The value should never exceed the Hundredths decimal place. This value should not include any discounts for subscription or contract.

### 2.18 `release_type` member
The `release_type` member is a __String__ that represents the Product's special release type. If the Product does not have a release type, the value should be __null__.

Possible non-null values:

- Simultaneous Release with Audio
- Simultaneous Release with Print
- Recent Release
- Backlist
- New Release
- Simultaneous Release
- Simultaneous Release with Re-Issue

### 2.19 `awards` member
The `awards` member is an __Array__ that contains zero or more __String__ values that represent the award name.

### 2.20 `is_available` member
The `is_available` member is a __Boolean__ that represents if the Product is available for order. This could be related to release date, or inventory. Since we do not track actual inventory, this is the only way to restrict a product's purchase after release.

### 2.21 `format` member
The `format` member is a __String__ that represents the format the Product is available in. This can also loosely be referred to as "product type".

Possible non-null values:

- playaway_light
- playaway_view
- playaway_launchpad
- playaway_bookpacks
- service
- accessory
- recorded_books

### 2.21 `package_type` member
The `package_type` member is a __String__ that represents the Product's package type. Since each package type for as title is tracked as a separate SKU this is a human readable value for the package type. If the product does not have a specific package type, the value should be __null__ which equates to standard.

Possible non-null values:

- portfolio_case
- hanging_bag
