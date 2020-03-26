"""A shopping basket contains a number of line items, for example: eggs, rice, flour; each with a specific quantity.
A basket may also have one discount code, for example eggs20. The shop has a standard price list, as well as a set 
of currently valid discount codes, each of which confers a certain percentage discount for a list of eligible products.
Produce a method which accepts a list of baskets, and outputs their values from highest to lowest."""
print("welcome to the store ")
print("------------------------------")
print("\n")
print('THE STANDARD PRICES OF THE STORE ARE :')
standardPrice={'rice_1kg':2,#prices in euros
               'mayo250ml':2,
               'milk_1lit':2,
               'noodles_2pk':1,
               'curd_1kg':1.5,
               'eggs_6':1,
               'wheatflour_1kg':2}

for key,value in standardPrice.items():
    print(str(key)+':'+  "\t"+   str(value))
discounts= {'egg_30':0.2,'wheatflour_4kg':0.2,'rice_20kg':0.2} #eligible discounts
customer1={'rice_1kg':20,'milk_1lit':3,'curd_1kg':1.5}

class shoppingbasket:
    def getprice(product,qty):#for one product
        x=standardPrice[product]*qty
        if (product=='eggs_6'and qty==5):
            discount=x*discounts['eggs_30']
            subtotal=x-discount
        elif product=='wheatflour_4kg' and qty==4:
            discount=x*discounts['wheatflour_1kg']
            subtotal=x-discount
        elif product=='rice_1kg' and qty==20:
            discount=x*discounts['rice_20kg']
            subtotal=x-discount
        else:
            subtotal=x
        return subtotal
    def actualbill():
        bill=0
        for key,value in customer1.items():
            bill = bill + shoppingbasket.getprice(key,value)
        return bill

    
        
        
