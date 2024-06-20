Solidity Assessment Submission
This simple project is my submission for the Solidity assessment. The contract allows minting and burning of tokens, keeping track of balances associated with addresses.

Features
The contract includes the following :

Public Variables: Store token details such as name, abbreviation, and total supply.
Mapping: Track balances of different addresses.
Mint and Burn Functions: Update the total supply and balances accordingly.
License
The project and the contract both use the MIT license.

Getting Started
Executing the Program
To execute this program, follow these steps:

Go to Remix.
Create a new file with a .sol extension (e.g., MyToken.sol).
Copy and paste the following code into the file:
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

contract MyToken {
    // Public variables
    string public Mytoken = "Shibaishu";
    string public MyTokAbb = "ISHU";
    uint public TotalSupply = 0;

    // Mapping to track balances
    mapping(address => uint) public TotalBal;

    // Mint function
    function MintF(address _address, uint _value) public {
        TotalSupply += _value;
        TotalBal[_address] += _value;
    }

    // Burn function
    function BurnF(address _address, uint _value) public {
        require(TotalBal[_address] >= _value, "Insufficient balance to burn");
        TotalSupply -= _value;
        TotalBal[_address] -= _value;
    }
}
Compile the contract by clicking on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to 0.8.18 (or another compatible version), and then click on the "Compile MyToken.sol" button.
Deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the MyToken contract from the dropdown menu, and then click on the "Deploy" button.
Interacting with the Contract
Mint Tokens: Use the MintF function to mint new tokens. Provide the address and the amount of tokens to mint.
Burn Tokens: Use the BurnF function to burn tokens. Provide the address and the amount of tokens to burn. Ensure the address has a sufficient balance to burn the specified amount.
Author
Created by: Ishan Kashyap

License
This project is licensed under the MIT License - see the LICENSE.md file for details.
