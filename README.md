# Task

Recreate a vending machine. You will be given a json file of inventory, and "money" to import into your machine.

The user should input two things to get an item:

1. Code (`A01`)
2. Amount of money the user inserts into the machine (`0.75`)

There should also be two maintenance methods:

1. Check on inventory of a specific item (by code)
2. The amount of money currently in the machine

Demonstrate the following rules using a test harness like PyTest, Unittest, etc.

## Rules

1. If the money given to the machine is less than the item cost return `Not enough money!`
2. If the quantity is 0 for an item return `<item name>: Out of Stock!`. Where <item name> is the name of the item selected.
3. If an item is correctly selected return `Vending <item name> with <change> change.` Where <item name> is the name of the item selected and change, if any, 0 otherwise.
4. If an item is correctly selected and there is no change needed then return "Vending <item name>".Where <item name> is the name of the item selected.
5. If an invalid item is selected return `Invalid selection!`.
6. If a selection is successful then the quantity should be updated.
7. For simplicity, denomitions of bills and coins is not taken into consideration, but the vending machine can run out of 'money', so you must keep track of the amount of money availble to return.
8. Change is always given to 2 decimal places (e.g. `7.00`)

## Example

```python3
candy_machine = MyVendingMachine(json) # json = {"items": [{"name": "skittles", "code": "A01", "price": 0.60, "quantity": 11}], "money": 12.00}

candy_machine.vend('A01', 0.60)
# "Vending Skittles"
candy_machine.inventory('A01')
# "Skittles Inventory: 10"
candy_machine.money()
# "Change Available: 12.00"
```
