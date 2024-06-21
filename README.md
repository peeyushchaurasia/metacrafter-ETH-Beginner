Solidity Assessment Submission: I have submitted this straightforward project for the Solidity assessment. Token minting and burning are permitted under the contract, which also maintains account balances.

Permission to Use
Both the project and the agreement make use of the MIT license.
// SPDX-License-Identifier: MIT


Qualities
The following are included in the contract:

Store token information, including name, abbreviation, and total supply, in the public variables.
Mapping: Monitor individual address balances.
Burn Mint Functions: Make necessary updates to the overall supply and balances.

Commencing
Putting the Program in Motion
Use these actions to run this program:

Proceed to Remix.
Make a new file, such as MyToken.sol, with the.sol extension.
Paste the following code into the file after copying it:

pragma solidity 0.8.18;

contract MyToken {

    // public variables here
    string public mytokenName = "ENGINEER";
    string public mytokenAbbrv = "CODE";
    uint public totalSupply = 0;

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
    function mintToken (address _address, uint _value) public {
      totalSupply += _value;
      balances[_address] += _value;
    }

    // burn function
    function burnToken (address _address, uint _value) public {
      if (balances[_address] >= _value) {
        totalSupply -= _value;
        balances[_address] -= _value;
      }
      }
}

To begin compiling the contract, select the "Solidity Compiler" tab located in the sidebar on the left. After confirming that "Compiler" is set to 0.8.18 (or a compatible version), click the "Compile MyToken.sol" button.
To deploy the contract, select the "Deploy & Run Transactions" tab located in the sidebar on the left. After choosing the MyToken contract from the drop-down menu, press the "Deploy" button.
Utilizing the Contract Mint Tokens: Mint new tokens by using the mintToken function. Give mint the address and the quantity of tokens to be minted.
Destroy Tokens: Tokens can be burned using the burnToken function. Tell us the address and how many tokens you want to burn. Make sure the address has enough balance to burn the given amount.
