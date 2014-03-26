Store Inventory and Point of Sale System

- Admin should be able to create a store
- Store should be able to add managers, employees, products, and customers
- Manager should be able to add new employees and products to inventory
- Inventory should have product categories and products. Inventory should be able to track quanitity of items in inventory
- Employees should be able to process a sale
- Customer should be able to make a purchase
- A sale should calculate the transaction total and generate a receipt
- Store should track customer purchases and make relevant suggestions based on buying history

classes to define & possible methods:
Store
  has_many :products, through :inventory
  has_many :product_categories, through :inventory
  has_many :managers, through :employees
  has_many :cashiers, through :employees
Inventory
  has_many :products
  has_many :product_categories
Employee
  belongs_to :store
  has_many :managers
  has_many :cashiers
Departments???
  belongs_to :store
  has_many :products, through :inventory
  has_many :product_categories, through :inventory
  has_one :manager
Manager
  belongs_to :department
Customer
belongs_to :store
  has_many transactions, through :sale
