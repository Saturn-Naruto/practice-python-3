store_info = ("FreshMart", "Astana, Respublika Ave 1", "+7 700 000 0000")

print("=" * 30)
print(store_info[0])
print(store_info[1])
print(store_info[2])
print("=" * 30)

names = []
prices = []

while True:
    name = input("Enter product name (or 'done' to finish): ")
    if name == "done":
        break
    price = float(input("Enter price: "))
    names.append(name)
    prices.append(price)

print("-" * 30)
print("Your cart (" + str(len(names)) + " items):")
print("-" * 30)

for i in range(len(names)):
    print(names[i], "-", prices[i], "KZT")

print("-" * 30)

weekly_products = set()

while True:
    p = input("Enter product name (or 'done' to finish): ")
    if p == "done":
        break
    weekly_products.add(p)

print("Unique products:", len(weekly_products))
print(weekly_products)

customer = input("Enter customer name: ")

subtotal = sum(prices)

if subtotal < 3000:
    discount = 0
    label = "No discount"
elif subtotal < 7000:
    discount = subtotal * 0.05
    label = "Standard discount"
else:
    discount = subtotal * 0.15
    label = "Premium discount"

total = subtotal - discount

receipt = {
    "customer": customer,
    "items": len(names),
    "subtotal": subtotal,
    "discount": discount,
    "total": total
}

print("=" * 30)
print("RECEIPT - " + store_info[0])
print("=" * 30)
print("Customer :", receipt["customer"])
print("Items :", receipt["items"])
print("-" * 30)

for i in range(len(names)):
    print(names[i], "-", prices[i], "KZT")

print("-" * 30)
print("Subtotal :", receipt["subtotal"], "KZT")
print("Discount :", receipt["discount"], "KZT (" + label + ")")
print("Total :", receipt["total"], "KZT")
print("=" * 30)
