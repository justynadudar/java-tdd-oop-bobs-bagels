# Domain Model

| Classes | Members        | Methods | Scenario | Outputs |
|---------|----------------|---------|----------|---------|
| Product | String sku     |         |          |         |
|         | double price   |         |          |         |
|         | String name    |         |          |         |
|         | String variant |         |          |         |
|         |                |         |          |         |

| Classes | Members        | Methods                        | Scenario                                          | Outputs |
|---------|----------------|--------------------------------|---------------------------------------------------|---------|
| Bagel   | String sku     | chooseFilling(Product product) | if name of product equals "Filling" add to basket | String  |
|         | double price   | chooseFilling(String variant)  | if name of variant does not exist print message   | String  |
|         | String name    |                                |                                                   |         |
|         | String variant |                                |                                                   |         |
|         |                |                                |                                                   |         |

| Classes   | Members                     | Methods                                                 | Scenario                             | Outputs |
|-----------|-----------------------------|---------------------------------------------------------|--------------------------------------|---------|
| Inventory | List<Product> inventoryList | getProductBySKU(String sku)                             | if sku exists                        | Product |
|           |                             |                                                         | if sku does not exist                | null    |
|           |                             | getProductByNameAndVariant(String name, String variant) | if name and variant exists           | Product |
|           |                             |                                                         | if name and variant does not exist   | null    |
|           |                             | getPriceBySKU(String sku)                               | if sku exists                        | double  |
|           |                             |                                                         | if sku does not exist                | null    |
|           |                             | getPriceByNameAndVariant(String name, String variant)   | if name and variant exists           | double  |
|           |                             |                                                         | if name and variant does not exist   | null    |



| Classes | Members                              | Methods                                    | Scenario                                                                                                    | Outputs |
|---------|--------------------------------------|--------------------------------------------|-------------------------------------------------------------------------------------------------------------|---------|
| Basket  | int capacity                         | addProduct(Product product)                | if capacity is not full add product                                                                         | String  |
|         |                                      |                                            | if capacity is full                                                                                         | String  |
|         |                                      | addProduct(String sku)                     |                                                                                                             |         |
|         |                                      | addBagelByVariant(String variant)          | if variant exists and name equals "Bagel" add bagel                                                         | String  |
|         |                                      |                                            | if variant doesn't exist or name is not equal to "Bagel"                                                    | String  |
|         | HashMap<Product, Integer> basketList | removeProduct(Product product)             | if product is in basket remove product from basket                                                          | String  |
|         |                                      |                                            | if product is not in basket                                                                                 | String  |
|         |                                      | removeProduct(String sku)                  |                                                                                                             |         |
|         | int productsQuantity                 | isOverfilled()                             | if basket is full                                                                                           | true    |
|         |                                      |                                            | if basket is not full                                                                                       | false   |
|         |                                      | changeCapacity(int newSize)                | change size if new capacity is bigger than previous one                                                     | String  |
|         |                                      |                                            | if new capacity is smaller than previous check if quantity of products <= new capacity                      | String  |
|         |                                      |                                            | if new capacity is smaller than previous check if quantity of products > new capacity and don't change      | String  |
|         |                                      | totalCost()                                | count cost of whole basket                                                                                  | double  |
|         |                                      | checkPrice(Product product)                | check price of given product                                                                                | double  |
|         |                                      | checkPrice(String sku)                     |                                                                                                             |         |
|         |                                      | checkIfProductInInventory(Product product) | if product in inventory                                                                                     | true    |
|         |                                      | checkIfProductInInventory(String sku)      | if product not in inventory                                                                                 | false   |