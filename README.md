# proj3
# FREEZE CODE BEGIN
###########################################
# FUNCTIONS SECTION TOP                   #
# (Place functions below)                 #
#-----------------------------------------#
# FREEZE CODE END
import csv

def load_customer_data():
  customers = []
  with open(file_name, 'r') as file:
    for line in file:
      customer_number = int(line[0:5])
      customer_name = line[5:35].strip()
      customer_email = line[35:65].strip()
      customer_pin = int(line[65:69])
      customer_balance = float(line[69:77])
      customer_credit_limit = float(line[77:85])

      customer = {
        "customer_number": customer_number,
        "customer_name": customer_name,
        "customer_email": customer_email,
        "customer_pin": customer_pin,
        "customer_balance": customer_balance,
        "customer_credit_limit": customer_credit_limit
      }
      customers.append(customer)
  return customers

def display_customer_list(load_customer_data):
  customer_info = ''
  for customer in customers:
    customer_info += f"{customer['customer_number']} {customer['customer_name']} {customer['customer_email']} {customer['customer_pin']} {customer['customer_balance']:.2f} {customer['customer_credit_limit']:.2f}\n"
  return customer_info
# FREEZE CODE BEGIN
#-----------------------------------------#
# FUNCTIONS SECTION BOTTOM                #
###########################################
if __name__ == '__main__':
# FREEZE CODE END
  file_name = input('Enter customer file name: ')
  transaction_f = input('Enter transaction file name: ')
  print("------------------------")
  print("1. Add Customer")
  print("2. Update Transactions")
  print("3. Print Customer Statement")
  print("4. Display Customer List Information")
  print("5. Display Transaction List Information")
  print("X. Exit Program")
  print("------------------------")
  option = input("Enter menu option: ")
  if option == '4':
    print(display_customer_list)
    