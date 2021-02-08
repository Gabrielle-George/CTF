Some possible SQL injection strategies:

To overcome manual escaping:
- input payload as an array-- to avoid "if [some commonly malicious char] in input str then exit" type sqli mitigation strategies
- unicode homoglyphs:  sometimes inputting a unicode value that is not recognized by the software but looks like a malicious char (such as single quote vs apostrophe) could result in it being automatically transformed to the malicious char
- putting the HTML escape value in- ex: %27 rather than '
