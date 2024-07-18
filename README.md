# DegenToken Smart Contract

This Solidity program is a demonstration of an ERC-20 token with support for transfer, minting, burning of tokens, and additional gaming features.

## Description

The Solidity program defines an ERC-20 token with essential functionalities and additional gaming features. It includes functions for minting, where only the owner can create new tokens, and burning, which allows any holder to destroy their tokens. The contract supports standard ERC-20 transfer and allowance operations, enabling tokens to be transferred between any accounts on the blockchain. Additionally, it incorporates features for an in-game economy, allowing players to purchase items and participate in games. It imports the ERC20 interface from [OpenZeppelin](https://www.openzeppelin.com/

# Contract Overview
The Token contract is a comprehensive implementation of an ERC-20 token with additional features. It includes the following components:

1) `owner` : The address of owner which gets assigned when the contract is deployed

# Usage
Constructor
The contract constructor initializes the contract with an initial supply of tokens. The deploying address becomes the founder of the contract and holds the entire initial supply.

```solidity
constructor(address initialOwner, uint tokenSupply);
```

# Functions

```solidity
mint(address to, uint256 amount);
// Allows the owner to mint new tokens and add them to a specified address's balance.
```

```solidity
burn(uint256 amount);
// Allows users to burn (destroy) a specific amount of their tokens.
```

```solidity
transferToken(address recipient, uint256 amount);
// Transfers a specified amount of tokens from the sender to the recipient.
```

```solidity
welcomeBonus();
// Grants a welcome bonus of tokens to new players.
```

```solidity
addItem(string memory _name, uint256 _price);
// Adds a new item to the in-game store.
```

```solidity
isLessThanFive(bool _prediction, uint256 _betAmount);
// A game where players bet on whether a randomly generated number is less than five.
```

```solidity
purchaseItem(uint8 _itemId);
// Allows players to purchase items from the in-game store.
```

```solidity
getUserItems(address user) external view returns (uint8[] memory);
// Returns the IDs of items owned by a specified user.
```

```solidity
getItemName(uint8 _id) external view returns (string memory);
// Returns the name of an item by its ID.
```

```solidity
getItemPrice(uint8 _id) external view returns (uint256);
// Returns the price of an item by its ID.
```

```solidity
getBalance() external view returns (uint256);
// Returns the token balance of the caller.
```

```solidity
burnToken(uint256 amount);
// Allows users to burn (destroy) a specific amount of their tokens.
```

## Getting Started

### Installation
[Open in Remix](https://remix.ethereum.org/?code=Ly8gU1BEWC1MaWNlbnNlLUlkZW50aWZpZXI6IE1JVApwcmFnbWEgc29saWRpdHkgXjAuOC4xODsKCmltcG9ydCAiQG9wZW56ZXBwZWxpbi9jb250cmFjdHMvdG9rZW4vRVJDMjAvRVJDMjAuc29sIjsKaW1wb3J0ICJAb3BlbnplcHBlbGluL2NvbnRyYWN0cy9hY2Nlc3MvT3duYWJsZS5zb2wiOwppbXBvcnQgIkBvcGVuemVwcGVsaW4vY29udHJhY3RzL3Rva2VuL0VSQzIwL2V4dGVuc2lvbnMvRVJDMjBCdXJuYWJsZS5zb2wiOwoKY29udHJhY3QgRGVnZW5Ub2tlbiBpcyBFUkMyMCwgT3duYWJsZSwgRVJDMjBCdXJuYWJsZSB7CgogICAgc3RydWN0IEl0ZW0gewogICAgICAgIHN0cmluZyBuYW1lOwogICAgICAgIHVpbnQ4IGl0ZW1JZDsKICAgICAgICB1aW50MjU2IHByaWNlOwogICAgfQogICAgbWFwcGluZyAodWludDg9Pkl0ZW0pIGl0ZW1zOwogICAgbWFwcGluZyAoYWRkcmVzcz0+SXRlbVtdKSBwbGF5ZXJJdGVtczsKICAgIHVpbnQ4IHB1YmxpYyB0b2tlbklkOwogICAgCiAgICBldmVudCBJdGVtUHVyY2hhc2VkKGFkZHJlc3MgaW5kZXhlZCBidXllciwgdWludDggaXRlbUlkLCBzdHJpbmcgaXRlbU5hbWUsIHVpbnQyNTYgcHJpY2UpOwogICAgZXZlbnQgR2FtZU91dGNvbWUoYWRkcmVzcyBpbmRleGVkIHBsYXllciwgdWludDI1NiBudW0sIGJvb2wgd29uLCBzdHJpbmcgcmVzdWx0KTsKCiAgICBjb25zdHJ1Y3RvciAoYWRkcmVzcyBpbml0aWFsT3duZXIsIHVpbnQgdG9rZW5TdXBwbHkpIEVSQzIwKCJEZWdlbiIsICJER04iKSBPd25hYmxlKGluaXRpYWxPd25lcikgewogICAgICAgIG1pbnQoaW5pdGlhbE93bmVyLCB0b2tlblN1cHBseSk7CiAgICAgICAgCiAgICAgICAgaXRlbXNbMV0gPSBJdGVtKCJOb3ZpY2UgTmF2aWdhdG9yIiwxLCAxMDApOwogICAgICAgIGl0ZW1zWzJdPUl0ZW0oIk15dGhpYyBNYXZlcmljayIsIDIsIDcwMCk7CiAgICAgICAgaXRlbXNbM109SXRlbSgiQ2VsZXN0aWFsIENydXNoZXIiLCAzLCAxMjAwKTsKICAgICAgICBpdGVtc1s0XT1JdGVtKCJBc3RyYWwgQWNlIiwgNCwgMjIwMCk7CiAgICAgICAgaXRlbXNbNV09SXRlbSgiRGl2aW5lIERvbWluYXRvciIsIDUsIDI0MDApOwogICAgICAgIHRva2VuSWQ9NjsKCiAgICB9CgogICAgZnVuY3Rpb24gZGVjaW1hbHMoKSBvdmVycmlkZSBwdWJsaWMgcHVyZSByZXR1cm5zICh1aW50OCl7CiAgICAgICAgcmV0dXJuIDA7CiAgICB9CgogICAgLy8gTWludGluZyB0b2tlbnMKCiAgICBmdW5jdGlvbiBtaW50KGFkZHJlc3MgdG8sIHVpbnQyNTYgYW1vdW50KSBwdWJsaWMgb25seU93bmVyIHsKICAgICAgICBfbWludCh0bywgYW1vdW50KTsKICAgIH0KCiAgICAvLyBUcmFuc2ZlcnJpbmcgdG9rZW5zCgogICAgZnVuY3Rpb24gdHJhbnNmZXJUb2tlbihhZGRyZXNzIF9yZWNpcGllbnQsIHVpbnQgX2Ftb3VudCkgZXh0ZXJuYWwgewogICAgICAgIHJlcXVpcmUoYmFsYW5jZU9mKG1zZy5zZW5kZXIpPj1fYW1vdW50LCAiSW5zdWZmaWNpZW50IGJhbGFuY2UiKTsKICAgICAgICB0cmFuc2ZlcihfcmVjaXBpZW50LCBfYW1vdW50KTsKICAgIH0KCiAgICAvLyBSZWRlZW1pbmcgdG9rZW5zCgogICAgZnVuY3Rpb24gd2VsY29tZUJvbnVzKCkgcHVibGljIHsKICAgICAgICByZXF1aXJlKGJhbGFuY2VPZihtc2cuc2VuZGVyKSA9PSAwLCAiWW91J3ZlIGFscmVhZHkgY2xhaW1lZCB5b3VyIHdlbGNvbWUgYm9udXMiKTsKICAgICAgICBfbWludChtc2cuc2VuZGVyLCA1MCk7CiAgICB9CgogICAgZnVuY3Rpb24gYWRkSXRlbShzdHJpbmcgbWVtb3J5IF9uYW1lLCB1aW50MjU2IF9wcmljZSkgcHVibGljIG9ubHlPd25lciB7CiAgICAgICAgaXRlbXNbdG9rZW5JZF0gPSBJdGVtKF9uYW1lLCB0b2tlbklkLF9wcmljZSk7CiAgICAgICAgdG9rZW5JZCsrOwogICAgfSAKCiAgICBmdW5jdGlvbiBpc0xlc3NUaGFuRml2ZShib29sIF9wcmVkaWN0aW9uLCB1aW50MjU2IF9iZXRBbW91bnQpIHB1YmxpYyB7CiAgICAgICAgdWludCByYW5kb21OdW1iZXIgPSB1aW50KGtlY2NhazI1NihhYmkuZW5jb2RlUGFja2VkKGJsb2NrLnRpbWVzdGFtcCwgbXNnLnNlbmRlcikpKSAlIDEwOwoKICAgICAgICBpZiAoX3ByZWRpY3Rpb24gPT0ocmFuZG9tTnVtYmVyPDUpKSB7CiAgICAgICAgICAgIF9taW50KG1zZy5zZW5kZXIsIF9iZXRBbW91bnQqMik7CiAgICAgICAgICAgIGVtaXQgR2FtZU91dGNvbWUobXNnLnNlbmRlciwgcmFuZG9tTnVtYmVyLCB0cnVlLCAid29uIik7CgogICAgICAgIH0gZWxzZSB7CiAgICAgICAgICAgIGJ1cm4oX2JldEFtb3VudCk7CiAgICAgICAgICAgIGVtaXQgR2FtZU91dGNvbWUobXNnLnNlbmRlciwgcmFuZG9tTnVtYmVyLCBmYWxzZSwgImxvc3QiKTsKICAgICAgICB9CiAgICB9CiAgICAKICAgIGZ1bmN0aW9uIHB1cmNoYXNlSXRlbSh1aW50OCBfaXRlbUlkKSBleHRlcm5hbCB7CiAgICAgICAgcmVxdWlyZShpdGVtc1tfaXRlbUlkXS5wcmljZSAhPSAwLCAiSXRlbSBub3QgZm91bmQiKTsKICAgICAgICByZXF1aXJlKGJhbGFuY2VPZihtc2cuc2VuZGVyKSA+PSBpdGVtc1tfaXRlbUlkXS5wcmljZSwgIkluc3VmZmljaWVudCBiYWxhbmNlIik7CgogICAgICAgIGJ1cm4oaXRlbXNbX2l0ZW1JZF0ucHJpY2UpOwogICAgICAgIHBsYXllckl0ZW1zW21zZy5zZW5kZXJdLnB1c2goaXRlbXNbX2l0ZW1JZF0pOwoKICAgICAgICBlbWl0IEl0ZW1QdXJjaGFzZWQobXNnLnNlbmRlciwgX2l0ZW1JZCwgaXRlbXNbX2l0ZW1JZF0ubmFtZSwgaXRlbXNbX2l0ZW1JZF0ucHJpY2UpOwogICAgfQoKICAgIGZ1bmN0aW9uIGdldFVzZXJJdGVtcyhhZGRyZXNzIHVzZXIpIGV4dGVybmFsIHZpZXcgcmV0dXJucyAodWludDhbXSBtZW1vcnkpIHsKICAgICAgICBJdGVtW10gbWVtb3J5IGl0ZW1zTGlzdCA9IHBsYXllckl0ZW1zW3VzZXJdOwogICAgICAgIHVpbnQgbGVuZ3RoID0gaXRlbXNMaXN0Lmxlbmd0aDsKCiAgICAgICAgdWludDhbXSBtZW1vcnkgX2lkcyA9IG5ldyB1aW50OFtdKGxlbmd0aCk7CgogICAgICAgIGZvciAodWludCBpID0gMDsgaSA8IGxlbmd0aDsgaSsrKSB7CiAgICAgICAgICAgIF9pZHNbaV0gPSBpdGVtc0xpc3RbaV0uaXRlbUlkOwogICAgICAgIH0KCiAgICAgICAgcmV0dXJuIF9pZHM7CiAgICB9CiAgICBmdW5jdGlvbiBnZXRJdGVtTmFtZSh1aW50OCBfaWQpIGV4dGVybmFsICB2aWV3IHJldHVybnMgKHN0cmluZyBtZW1vcnkpIHsKICAgICAgICByZXR1cm4gaXRlbXNbX2lkXS5uYW1lOwogICAgfQogICAgZnVuY3Rpb24gZ2V0SXRlbVByaWNlKHVpbnQ4IF9pZCkgZXh0ZXJuYWwgIHZpZXcgcmV0dXJucyh1aW50KXsKICAgICAgICByZXR1cm4gaXRlbXNbX2lkXS5wcmljZTsKICAgIH0KCgogICAgLy8gQ2hlY2tpbmcgdG9rZW4gYmFsYW5jZQoKICAgIGZ1bmN0aW9uIGdldEJhbGFuY2UoKSBleHRlcm5hbCB2aWV3IHJldHVybnModWludDI1Nil7CiAgICAgICAgcmV0dXJuIGJhbGFuY2VPZihtc2cuc2VuZGVyKTsKICAgIH0KCiAgICAvLyBCdXJuaW5nIHRva2VucwoKICAgIGZ1bmN0aW9uIGJ1cm5Ub2tlbih1aW50IF9hbW91bnQpIGV4dGVybmFsIHsKICAgICAgICByZXF1aXJlKGJhbGFuY2VPZihtc2cuc2VuZGVyKT49X2Ftb3VudCwgIkluc3VmZmljaWVudCBhbW91bnQiKTsKICAgICAgICBidXJuKF9hbW91bnQpOwogICAgfQoKfQ==)

### Executing Program
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at [Remix Ethereum](https://remix.ethereum.org/).


```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.18;

import "@openzeppelin/contracts/token/ERC20/ERC20.sol";
import "@openzeppelin/contracts/access/Ownable.sol";
import "@openzeppelin/contracts/token/ERC20/extensions/ERC20Burnable.sol";

contract DegenToken is ERC20, Ownable, ERC20Burnable {

    struct Item {
        string name;
        uint8 itemId;
        uint256 price;
    }
    mapping (uint8=>Item) items;
    mapping (address=>Item[]) playerItems;
    uint8 public tokenId;
    
    event ItemPurchased(address indexed buyer, uint8 itemId, string itemName, uint256 price);
    event GameOutcome(address indexed player, uint256 num, bool won, string result);

    constructor (address initialOwner, uint tokenSupply) ERC20("Degen", "DGN") Ownable(initialOwner) {
        mint(initialOwner, tokenSupply);
        
        items[1] = Item("Novice Navigator",1, 100);
        items[2]=Item("Mythic Maverick", 2, 700);
        items[3]=Item("Celestial Crusher", 3, 1200);
        items[4]=Item("Astral Ace", 4, 2200);
        items[5]=Item("Divine Dominator", 5, 2400);
        tokenId=6;

    }

    function decimals() override public pure returns (uint8){
        return 0;
    }

    // Minting tokens

    function mint(address to, uint256 amount) public onlyOwner {
        _mint(to, amount);
    }

    // Transferring tokens

    function transferToken(address _recipient, uint _amount) external {
        require(balanceOf(msg.sender)>=_amount, "Insufficient balance");
        transfer(_recipient, _amount);
    }

    // Redeeming tokens

    function welcomeBonus() public {
        require(balanceOf(msg.sender) == 0, "You've already claimed your welcome bonus");
        _mint(msg.sender, 50);
    }

    function addItem(string memory _name, uint256 _price) public onlyOwner {
        items[tokenId] = Item(_name, tokenId,_price);
        tokenId++;
    } 

    function isLessThanFive(bool _prediction, uint256 _betAmount) public {
        uint randomNumber = uint(keccak256(abi.encodePacked(block.timestamp, msg.sender))) % 10;

        if (_prediction ==(randomNumber<5)) {
            _mint(msg.sender, _betAmount*2);
            emit GameOutcome(msg.sender, randomNumber, true, "won");

        } else {
            burn(_betAmount);
            emit GameOutcome(msg.sender, randomNumber, false, "lost");
        }
    }
    
    function purchaseItem(uint8 _itemId) external {
        require(items[_itemId].price != 0, "Item not found");
        require(balanceOf(msg.sender) >= items[_itemId].price, "Insufficient balance");

        burn(items[_itemId].price);
        playerItems[msg.sender].push(items[_itemId]);

        emit ItemPurchased(msg.sender, _itemId, items[_itemId].name, items[_itemId].price);
    }

    function getUserItems(address user) external view returns (uint8[] memory) {
        Item[] memory itemsList = playerItems[user];
        uint length = itemsList.length;

        uint8[] memory _ids = new uint8[](length);

        for (uint i = 0; i < length; i++) {
            _ids[i] = itemsList[i].itemId;
        }

        return _ids;
    }
    function getItemName(uint8 _id) external  view returns (string memory) {
        return items[_id].name;
    }
    function getItemPrice(uint8 _id) external  view returns(uint){
        return items[_id].price;
    }


    // Checking token balance

    function getBalance() external view returns(uint256){
        return balanceOf(msg.sender);
    }

    // Burning tokens

    function burnToken(uint _amount) external {
        require(balanceOf(msg.sender)>=_amount, "Insufficient amount");
        burn(_amount);
    }

}
```

## Help
To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile Token.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "Token" contract from the dropdown menu, and then click on the "Deploy" button.

## Authors
Ankush Kumar

## License
This project is licensed under the MIT License - see the LICENSE.md file for details
