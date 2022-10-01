//SPDX-License-Identifier: MIT
pragma solidity ^ 0.8.7;

interface IERC20 {
function totalSupply() external view returns(uint);
function balanceOf(address tokenOwner) external view returns(uint balance);
function transfer(address to, uint tokens) external returns(bool success);
function allowance(address tokenOwner, address spender) external view returns(uint remaining);
function approve(address spender, uint tokens) external returns(bool success);
function transferFrom(address from, address to, uint tokens) external returns(bool success);

event Transfer(address indexed from, address indexed to, uint tokens);
event Approval(address indexed tokenOwner, address indexed spender, uint tokens);
}

contract Jams is IERC20{
uint public lastUpdate;
uint public timeLimit;
uint public time_minutes;
string public name = "JAMSCoin";
string public symbol = "JC";
string public decimal = "0";
uint public override totalSupply;
address payable public founder;
    mapping(address => uint) public balances;
    mapping(address => mapping(address => uint)) allowed;
    mapping(address => address) public backup;
    mapping(address => bool) public isBackup;

    constructor(){
        totalSupply = 100000;
        founder = payable(msg.sender);
        balances[founder] = totalSupply;
    }

    function balanceOf(address tokenOwner) public view override returns(uint balance){
        return balances[tokenOwner];
    }

    function transfer(address to, uint tokens) public override returns(bool success){
        require(balances[msg.sender] >= tokens);
        balances[to] += tokens;
        balances[msg.sender] -= tokens;
emit Transfer(msg.sender, to, tokens);
        lastUpdate = block.timestamp;
        timeLimit = block.timestamp + time_minutes * 60; // Setting the timelimit in minutes
        return true;
    }

    function approve(address spender, uint tokens) public override returns(bool success){
        require(balances[msg.sender] >= tokens);
        require(tokens > 0);
        allowed[msg.sender][spender] = tokens;
emit Approval(msg.sender, spender, tokens);
        return true;
    }

    function allowance(address tokenOwner, address spender) public view override returns(uint noOfTokens){
        return allowed[tokenOwner][spender];
    }

    function transferFrom(address from, address to, uint tokens) public override returns(bool success){
        require(allowed[from][to] >= tokens);
        require(balances[from] >= tokens);
        balances[from] -= tokens;
        balances[to] += tokens;
        return true;
    }

    function setBackup(address main, address backupAccount, uint _timeLimit) public returns(bool success){
        require(msg.sender == main);
        backup[main] = backupAccount;
        isBackup[backupAccount] = true;
        time_minutes = _timeLimit;
        timeLimit = block.timestamp + _timeLimit * 60; // Setting the timelimit in minutes
        return true;
    }

    function getBackupAccount(address main) public view returns(address backupAccount){
        require(msg.sender == main);
        return backup[main];
    }

    function burn(address main) public returns(bool success){
        require(msg.sender == backup[main]);
        require(timeLimit < block.timestamp, "Time limit not yet expired");
        balances[backup[main]] += balances[main];
        balances[main] -= balances[main];
        return success;
    }

    function buyJams(uint tokens) public payable returns(bool success){
        require(msg.sender.balance >= tokens);
        (bool s, ) = founder.call{ value: tokens } ("");
        balances[founder] -= tokens;
        balances[msg.sender] += tokens;
        timeLimit = block.timestamp + time_minutes * 60; // Setting the timelimit in minutes
        return s;
    }

}
