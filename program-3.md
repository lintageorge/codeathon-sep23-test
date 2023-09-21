# Program 3: Validate IP Address

Write a program to validate an IP address. Given a string, write a function to check if it is a valid IP address or not. If valid, return true, otherwise return false.

### samples
Input | output
------|-------
255.255.0.0 | true
555.555.555.555 | false
256.255.0.0 | false

### Tasks
- Develop the program using your choice of programming language
- Create test script covering all scenarios (min 5 test cases)
- Add exception bloacks to the code to handle invalid inputs

import re

def validate_ip_address(ip):
    # Regular expressions for IPv4 and IPv6 patterns
    ipv4_pattern = r'^\d{1,3}(\.\d{1,3}){3}$'
    ipv6_pattern = r'^([0-9a-fA-F]{1,4}:){7}[0-9a-fA-F]{1,4}$'

    if re.match(ipv4_pattern, ip):
        # Check IPv4 address
        parts = ip.split('.')
        for part in parts:
            if not (0 <= int(part) <= 255):
                return False
        return True

    elif re.match(ipv6_pattern, ip):
        # Check IPv6 address
        return True

    else:
        return False

# Example usage:
ip_address1 = "192.168.1.1"
ip_address2 = "2001:0db8:85a3:0000:0000:8a2e:0370:7334"
ip_address3 = "256.256.256.256"  # Invalid IPv4 address
ip_address4 = "2001:0db8:85a3:0000:0000:8a2e:0370:7334:extra"  # Invalid IPv6 address

print(validate_ip_address(ip_address1))  # True
print(validate_ip_address(ip_address2))  # True
print(validate_ip_address(ip_address3))  # False
print(validate_ip_address(ip_address4))  # False
