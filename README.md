// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract BasicMath {

    // Adder function
    function adder(uint _a, uint _b) public pure returns (uint sum, bool error) {
        unchecked {
            sum = _a + _b;
            // Check for overflow
            if (sum < _a) {
                return (0, true); // Overflow occurred
            }
            return (sum, false); // No error
        }
    }

    // Subtractor function
    function subtractor(uint _a, uint _b) public pure returns (uint difference, bool error) {
        unchecked {
            // Check for underflow
            if (_b > _a) {
                return (0, true); // Underflow occurred
            }
            difference = _a - _b;
            return (difference, false); // No error
        }
    }
}
