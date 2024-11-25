
## What is Solidity?

- Solidity is a programming language which is used to write smart contracts for Ethereum foundation.
- It is a statically typed language, so the datatype must be defined before use.
- It is based on `Python`, `C++`, and `JavaScript`.

---

## Building Smart Contracts

- Let's see the structure of a smart contract in Solidity:

### **License Specifier**
- The very first line that you will encounter in a smart contract is the License Specifier.
- Example:  
  ```solidity
  // SPDX-License-Identifier: GPL-3.0
  ```
  Specifies that the code is licensed under the GNU GPL license.

### **Version Specifier**
- The second line of the contract specifies the version of the Solidity code to write the contract.
- Example:  
  ```solidity
  pragma solidity ^0.5.2;
  ```

### **Contract**
- The rest of the part is the actual contract.
- Example:  
  ```solidity
  contract <name> {
      // Contract logic
  }
  ```

---

## Datatypes in Solidity

### **Boolean**
- `bool` datatype represents `true` or `false` values.  
  Example:  
  ```solidity
  bool a = true;
  ```

---

### **Integer**
- This datatype is used to store integer values.  
- Two types:
  - **Signed Integers (`int`)**: Can store both positive and negative values.
  - **Unsigned Integers (`uint`)**: Can store only positive values.

---

### **Address**
- Used to store "20-byte Ethereum addresses".  
  Example:  
  ```solidity
  address walletAddress = 0x1234567890abcdef1234567890abcdef12345678;
  ```

---

### **Bytes**
- Used to work with binary data in Solidity.
- **Types**:
  1. **Fixed**: Predefined size.  
     Example:  
     ```solidity
     bytes4 data = 0x12345678; // A fixed-size array with 4 bytes.
     ```
  2. **Dynamic**: Variable size.  
     Example:  
     ```solidity
     bytes memory dynamicData = "Hello, Solidity!";
     ```
     The `memory` keyword indicates temporary storage.

#### **Use Cases of Bytes**
- **Storing Arbitrary Data**: For any binary data like cryptographic hashes or raw transaction details.
- **Interacting with External Contracts**: Frequently used for communication with oracles or external systems.

---

### **Enums**
- Enums are user-defined datatypes to create a set of named values or constants.  
- Improves code readability and simplifies managing related constants.

#### Example:  
```solidity
enum Permission {
    Read, Write, Execute
}

Permission public userPermission;

function setPermission(Permission _permission) public {
    userPermission = _permission;
}
```
- In this example:
  - `Read` is mapped to `0`.
  - `Write` is mapped to `1`.
  - `Execute` is mapped to `2`.

---

### Arrays and maps
- Array in solidity is same as an array in c++. The only difference is in their syntax.
- Syntax to define an array is "< type > [] < name >"
- Ex: 
```solidity
uint[] arr = {1,2,3,4};
```
- Maps are same as dictionaries in python.
- The syntax to define a map is "mapping(< keyType > => < valueType >)".
- Ex:
```solidity
mapping(address => uint) arr;
```

### Others
- Other datatypes include `struct`, `eth units` and `timestamps`.


## Structure of a Function 

- Basically, a function in Solidity is made up of many components.
- The base structure of a function includes the following components:
  1. **Function Name**: Firstly, we define the function using the `function` keyword followed by the function name. Then in round braces, we define function parameters, which can be skipped if the function doesn't need them.
  2. **Visibility**: Visibility determines who can access the function or use it.

      Function visibility is of 4 types:

      1. **public**:
        - If a function is labeled as `public`, it is accessible to everyone. 
        - It can be called by the owner as well as external accounts.

      2. **external**:
        - `external` functions can be called only from outside the contract. 
        - These functions cannot be called by any function directly within the contract.
        - To access this function, use `this.functionName()`.
        - It is more gas efficient than `public`.

      3. **internal**:
        - `internal` functions can be called within the contract or by derived contracts.
        - They cannot be called externally.

      4. **private**:
        - Defined using the `private` keyword, these functions can only be accessed inside the contract they are defined for.
        - They cannot be called by any derived contracts or by any external contracts.

      | Visibility   | Accessible by Same Contract | Accessible by Derived Contracts | Accessible Externally | Gas Efficiency (External Calls) |
      |--------------|------------------------------|----------------------------------|-----------------------|-----------------------------------|
      | `public`     | ✅                          | ✅                              | ✅                    | Slightly less efficient          |
      | `external`   | ❌ (except via `this`)       | ❌                              | ✅                    | More efficient                   |
      | `internal`   | ✅                          | ✅                              | ❌                    | N/A                               |
      | `private`    | ✅                          | ❌                              | ❌                    | N/A                               |
  3. **State Mutability** : Next thing we can define is how can we use the function, i.e, it is only meant for view purpose or not.
  - To define mutability of function, we have 3 mutabilities:
    1. **pure** : it means that function can neither read nor write any state.
    2. **view** : it means that state of the contract can be viewed but not modified.
    3. **payable** : to make function do transactions, it is made payable so that it can recieve ethers for the same.
  - If none of them are defined, it means that function can perform both read and write on data.
  4. **Modifiers** : Instead of repeating the same condition across multiple functions, a modifier can be created to encapsulate the logic or condition, which is then applied to functions to ensure the check is performed before execution.
  - Modifiers are optional, that is , it is not necessary that we declare them.
  - Ex: In the following code, modifier is used to check if the function is called by owner only or not.
  ```solidity
  modifier onlyOwner() {
        require(msg.sender == owner, "Not the contract owner");
        _;
    }

    // Function protected by the onlyOwner modifier
    function changeOwner(address newOwner) public onlyOwner {
        owner = newOwner;
    }
    ```
  5. **Return type** : return type is used to define what type of value is returned by our function, that is, string, integer, address and so on.
  - A Function can return a single value or multiple values depending on the needs.
  6. **Function Body** : Now use the curly braces and define the function body(A piece of logic that is exectued by the function).


