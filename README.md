# test-githint

Repo to use when testing Githint Bot.

Githint checks that your PR abides by team conventions.

The root directory of your repo should contain a .ghint file.

The .ghint file should contain a field called `checks`.

The `checks` object contains checks to be performed.

The `commit` object contains checks that should be performed on the commit that triggered the check.

The `pr` object contains checks that should be performed on the pull request that triggered the check.

The `tree` object contains checks that should be performed on the pull request that triggered the check.

Each check is a key-value pair where the key is the name of the check to perform and the value is either a string, an array of strings or an object that holds the (JavaScript) script to be executed for that check.
* If the value is a string it is expected to be an expression to be evaluated, not a return statement; i.e. it is not expected to have the return keyword.

If the script evaluates to true then the check passes. If not, the check fails.

If the script tag is an array of strings, each array element will be treated as a line of code, and executed without modification; i.e. somewhere in those lines of code there is expected to be a return statement.
