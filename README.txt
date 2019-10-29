Question 1:
- CRACKME_Part_1.exe will display message (b) no matter what name-serial combinations are put.
- I edited two lines in the original CRACKME.exe to create CRACKME_Part_1:  
  ->  Line 00401389 was changes to "CMP AL, AL" so that any ASCII characters are accepted by the name and serial inputs, ensuring that message (a) is not displayed.
  ->  Line 00401241 was changed to "CMP EAX, EAX" so that the corresponding jump always occurs, ensuring that message (b) is always displayed.

Question 2:
- My Name =  Nick; Serial = 17769;
- Bonus Names:
  ->  shifu; Serial = 17715;
  ->  yujie; Serial = 17866;
  ->  yiming; Serial = 17793; 
- Method for getting the serial of any name/valid char combination:
  Step 1 -> Convert all of the characters in name (input) to uppercase.
  Step 2 -> Take the sum of these characters as a hexadecimal (using ASCII values).
  Step 3 -> Perform an XOR with the sum and 0x5678.
  Step 4 -> Perform an XOR with the answer from the previous step and 0x1234.
  Step 5 -> Convert the answer from the previous step from hexadecimal to decimal. This value is the serial.
