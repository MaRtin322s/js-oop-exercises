# js-oop-exercises

1. Library Collection

- Functionality:

- Constructor have these 2 properties:
•	capacity – Number
•	books – Array (empty)
At the initialization of the LibraryCollection class, the constructor accepts the capacity.

- addBook (bookName, bookAuthor): The bookName and bookAuthor are of type string. 
•	If there's not enough space in the collection for the book, error will be thrown;
•	Otherwise, this function will add the book, with the properties: bookName, bookAuthor, payed: default false, to the books array;

- payBook( bookName ):  If the book is not found, error will be thrown. If the book has already paid, error will be thrown, otherwise this function will set paid to true on the found book;

- removeBook( bookName ): If the book is not found, error will be thrown, if the book hasn't paid, again error will be thrown. Otherwise, this function will remove the book from the array;

- getStatistics( bookAuthor ): This method can be called with one parameter or without any. If no parameter is provided, the method will return the full information of the library: At the first line: "The book collection has {count} empty spots left." On the lines, information about will be displayed each book, sorted alphabetically ascending, by their bookName: "{bookName} == {bookAuthor} - {Has Paid / Not Paid}." If the method is called with a parameter for bookAuthor, information about the book from the given bookAuthor will be returned: "{bookName} == {bookAuthor} - {Has Paid / Not Paid}.", if there is no such author’s book found, error will be thrown;

2. Camping

- Functionality:

- Constructor have these 4 properties: organizer - string, location - string, priceForTheCamp - {"child": 150, "student": 300, "collegian": 500} and listOfParticipants - empty array. At the initialization of the SummerCamp class, the constructor accepts the organizer and location.

- registerParticipant ( name, condition, money ): This method register participant to the camping.  If the given condition of participants, is not present in priceForTheCamp object with the specified default values ("child", "student", "collegian"), an error with the following message will be thrown. If the name of the current participant is already present in listOfParticipants array, message will be returned. If the submitted money is less than the price for the stay in the camp, message will be returned. Otherwise, will add the participant, with properties: {name, condition, power: default 100, wins: default 0} to the listOfParticipants array;

- unregisterParticipant (name): This method removes a participant from the camping. The method accepts 1 argument - name (string). If the name of the current participant is not present in listOfParticipants array, an error will be thrown. Otherwise, this function will remove the participant from the listOfParticipants array;

- timeToPlay (typeOfGame, participant1, participant2): This method can take 2 or 3 arguments depending on the type of game: typeOfGame (string), participant1 - name(string), participant2 - name(string) (optional). There are two possible types of games: WaterBalloonFights -> you will get two players, Battleship -> you will get one player. If any of the submitted participants names are not present in listOfParticipants array, an error will be thrown. If two names are submitted, check that the participants' condition matches, if not matched, an error will be thrown. If the type of game is Battleship increase the power property of the participant by a value of 20. If the type of game is WaterBalloonFights, it will check whether the value of the power of one participant is greater than the value of the power of the other participant, and in this case increase the value of the wins property by one per winner (with the bigger power). Otherwise, the function returns the message: `There is no winner.`

- toString (): At the first line: `{organizer} will take {numberOfParticipants} participants on camping to {location}`, On the lines, display information about each participant, sorted in descending order by their wins in the following format: `{name} - {condition} - {power} - {wins}`;

3. Resturant

- Constructor have 4 properties: budgetMoney - number, menu - object, stockProducts - object, history - array. At initialization of the Restaurant class, the constructor accepts only the budget! The rest of the properties are empty!

Functionality: 

- loadProducts(): Accept 1 argument products (array from strings). Every element into this array is information about product in format: "{productName} {productQuantity} {productTotalPrice}". They are separated by a single space. This method appends products into our products in stock (stockProducts) under the following circumstances: If the budget allows us to buy the current product, we add it to stockProducts keeping the name and quantity of the meal and we deduct the price of the product from our budget. If the current product already exists into stockProducts will add the new quantity to the old one, and finally, whether or not we have added a product to stock or not, we record our action in the history. If we were able to add the current product: "Successfully loaded {productQuantity} {productName}", If we not: "There was not enough money to load {productQuantity} {productName}". This method must return all actions joined by a new line!

- addToMenu(): Accept 3 arguments meal (string), needed products (array from strings) and price (number). Every element into needed products is in format: "{productName} {productQuantity}" They are separated by a single space! If the meal is not in our menu, appends a meal into object menu. Must have properties products and price! Check how many meals have in menu and returns one of the following messages: 
-	One meal: "Great idea! Now with the {meal} we have 1 meal in the menu, other ideas?", Zero, Two or more meal: "Great idea! Now with the {meal} we have {the number of all meals in the menu} meals in the menu, other ideas?". Otherwise, if we already have this meal return the message: "The {meal} is already in the our menu, try something different."

- showTheMenu(): This method just return all meals from our menu separated by a new line in format: {meal} - {meal price}. If our menu is empty, just return the message: "Our menu is not ready yet, please come later..."

- makeTheOrder(): Accept 1 argument meal (string). This method searches the menu for a certain meal. If we do not have the given meal, return the following message: "There is not {meal} yet in our menu, do you want to order something else?", otherwise, if we have this meal in the menu, we need to check, if we have the needed products to make it! If we have this meal in the menu and also, we have all needed products to make it. You also need to reduce quantity of all used products from those in stock and add the price of the meal to the total budget.

4. Online - shop

-Functionality:

Constructor have these 3 properties: warehouseSpace – Number, products – Array (empty), sales – Array (empty). At the initialization of the OnlineShop class, the constructor accepts the warehouseSpace.

- loadingStore(product, quantity, spaceRequired): The product is of type string, while the spaceRequired and quantity are of type number. If there is not enough space in the warehouse for the new product, error will be thrown. Otherwise, this function will add the product with the properties: product and quantity to the products array, with reduced space available with the space required by the product.

NOTE: Product names will be unique.

- quantityCheck(product, minimalQuantity): The quantity is of type number. If the product is not found, error will be thrown,
if the received minimalQuantity is less than or equal to 0, error will be thrown, if the received minimalQuantity is less or equal to the product quantity in the warehouse, message will be returned. Otherwise, this function will replace the value of product quantity with a minimalQuantity value and return: "You added {difference} more from the {product} products."
(Difference is the number between the minimum quantity and the product quantity.)

- sellProduct(product): If the product is not found, error will be thrown. Otherwise, this function will decrement by 1 the product quantity from the product in the products array, add it to sales with properties {product} and {1} for quantity, and return: "The {product} has been successfully sold."

- revision()
This method will return the complete information about the shop: If nothing is sold, error will be thrown, otherwise, return how many sales you have: "You sold {sales} products today!", on the second line: "Products in the warehouse:" and on the new line, display information about each product in the warehouse: "{product}-{quantity} more left";
