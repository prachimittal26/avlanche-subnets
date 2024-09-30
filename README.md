Setup Guide
Step 1: Set Up the EVM Subnet
Follow the official Avalanche documentation to set up a custom EVM Subnet. This will be the foundation for deploying the DeFi Kingdom's smart contracts.

Step 2: Define Your Native Currency
Create a custom ERC20 token contract (sample provided below). This token will act as the in-game currency for players to earn, trade, and spend.

solidity
Copy code
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.17;

contract ERC20 {
    uint public totalSupply;
    mapping(address => uint) public balanceOf;
    mapping(address => mapping(address => uint)) public allowance;
    string public name = "Solidity by Example";
    string public symbol = "SOLBYEX";
    uint8 public decimals = 18;

    event Transfer(address indexed from, address indexed to, uint value);
    event Approval(address indexed owner, address indexed spender, uint value);

    function transfer(address recipient, uint amount) external returns (bool) {
        balanceOf[msg.sender] -= amount;
        balanceOf[recipient] += amount;
        emit Transfer(msg.sender, recipient, amount);
        return true;
    }

    function approve(address spender, uint amount) external returns (bool) {
        allowance[msg.sender][spender] = amount;
        emit Approval(msg.sender, spender, amount);
        return true;
    }

    function transferFrom(
        address sender,
        address recipient,
        uint amount
    ) external returns (bool) {
        allowance[sender][msg.sender] -= amount;
        balanceOf[sender] -= amount;
        balanceOf[recipient] += amount;
        emit Transfer(sender, recipient, amount);
        return true;
    }

    function mint(uint amount) external {
        balanceOf[msg.sender] += amount;
        totalSupply += amount;
        emit Transfer(address(0), msg.sender, amount);
    }

    function burn(uint amount) external {
        balanceOf[msg.sender] -= amount;
        totalSupply -= amount;
        emit Transfer(msg.sender, address(0), amount);
    }
}
Step 3: Connect to Metamask
Once your EVM Subnet is set up, follow the Avalanche guide to connect it to Metamask. This will allow you to interact with your contracts directly from the browser.

Step 4: Deploy Smart Contracts
Deploy the basic contracts that will serve as the building blocks of the game, such as contracts for battling, exploring, and trading. You can use Remix or a local development environment for this.

Step 5: Interact with Contracts
Once deployed, players can interact with the contracts to battle, explore, and trade. These activities will use the native token as rewards, providing incentives for participation.
