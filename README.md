# password
def is_valid_password(password: str) -> int:
    if len(password) < 4:
        return 0
    
    has_digit = False
    has_upper = False
    has_invalid_char = False
    
    if password[0].isdigit():
        return 0
    
    for char in password:
        if char.isdigit():
            has_digit = True
        if char.isupper():
            has_upper = True
        if char == ' ' or char == '/':
            has_invalid_char = True

    if has_digit and has_upper and not has_invalid_char:
        return 1
    
    return 0


print(is_valid_password("aA1_67")) 
print(is_valid_password("a987 abC012"))  
