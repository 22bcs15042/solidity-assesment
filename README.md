contract MyToken {
    // Public variables to store token details
    string public tokenName = "Euth";
    string public tokenAbbrv = "NTT";
    uint public totalSupply = 0;

    //Mapping to store balances of addresses
   
    mapping(address => uint) public balances;

    // Mint function to increase total supply and balance of the given address
    function mint(address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    // Burn function to decrease total supply and balance of the given address
    function burn(address _address, uint _value) public {
        require(balances[_address] >= _value, "Insufficient balance to burn");
        totalSupply -= _value;
        balances[_address] -= _value;
    }
}
