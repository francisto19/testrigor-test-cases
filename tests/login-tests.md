#Login Test Cases

## Test: Successful Login
open url "https://dm.automanager.com/"
enter stored value "username" into "Username"
enter stored value "password" into "Password"
click "Sign In"
check that page contains "Support"

## Test: Invalid Login
open url "https://dm.automanager.com/"
enter stored value "username" into "Username"
enter "password" into "Password"
click "Sign In"
check that page contains "Sign In Failed"
