#Add Vehicle

## Test: Get Random Vin
open tab
open url "https://randomvin.com/"
wait 5 sec
click "Random Real VIN"
reload
wait 10 sec
double click XPath "/html/body/form/div[1]/span/h2"
copy to clipboard
close tab

## Test: Successful Login
enter stored value "username" into "Username"
enter stored value "password" into "Password"
click "Sign In"
check that page contains "Support"

## Test: Add Vehicle into Inventory
click "Inventory"
click "Add Vehicle"
click "Vin"
paste
click "Mileage"
enter "12345"
click XPath "//*[@id='btnNewVehicleContinue']"
wait 10 sec
if page contains "Select Vin Style" then
wait 10 sec
  click XPath "//*[@id='VinStyle']"
  select second option from "VinStyle"
  click "Continue"
  wait 20 sec
  check that page contains "Stock Number"
else
  check that page contains "Stock Number"
end
