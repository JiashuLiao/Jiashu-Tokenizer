# Jiashu-Tokenizer
The tokenizer accept a string as a command-line argument. The string will contain zero or more tokens, where each token is a either a floating-point constant, or an integer constant in hex, decimal or octal. The later definition of tokens will define
what begins each kind of token and how the tokens end. White space is defined as any sequence of blank (0x20), tab (0x09), vertical tab (0x0b), form-feed (0x0c), new-line (0x0a) and carriage return (0x0d) characters. The tokenizer will return the tokens in the string one token at a time.

For a example, while receiving “1234 0x1234 01234”, it divides the string to different type parts. The types are decimal(start with 1-9 and followed by 0-9), hexadecimal(start with 0x or 0X and followed by 0-9 or A-F or a-f), octal(start with 0 and followed by 0-7) and float (Case1: start with 0 then must followed by ‘.’ then n*0-9 then followed by ‘E’ or ’e’ then case1.1 followed by ‘+’’-’ must followed by 0-9 or case 1.2 followed by 0-9. Case 2: start with 1-9 must followed n*0-9 then case 2.1 followed by ‘.’ must followed by n*0-9 then by ‘E’ or ‘e’ or case 2.2 followed by ‘E’ or ’e’ then followed like case 1.1 and 1.2).

All wrong input should be printed as ASCII such as “.” “[0x2e]”.

In the meanwhile, the program frees token after using it (get results and printing).
