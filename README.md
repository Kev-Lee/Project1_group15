# Project1_group15 </br>

1) Question 1 take an input x and takes the 2's complement of x by taking the invert of x and adding 1. Then z is taken as the invert of y or x, and this value is shifted 31 bits to the right. It then returns z & 1. This is dependent on what input is taken in. If x is anything other than 0, the code will return 0. If the input is 0, then the 2's complement of it to get 32 to bits of 0's because of the +1 overflow, and then we take the invert of 32 bits of 0's to get 32 bits of 1's. Shifting that 31 times to the right gives us 1 as the final value of z, and z & z is equal to 1.

2) Question 2 takes in an input x and then shifts the value 31 bits to the right. If the value is positive or 0, the mask value will be 32 bits of 0's, and if x is negative, the mask value will be 32 bits of 1's. y is x exclusive or the mask value, so when you have the mask as 32 bits of 0's y would equal x, and when you have 32 bits of 1's y would be the invert of x. Adding 1 to an invert mask equal to 32 bits of 1's would be 32 bits of 0's due to overflow, and adding 1 to the invert mask equal to 32 bits of 0's would give you 1. For the return value, when x is positive, you end up with x + 0 = x, and when x is negative, you end up with the ~x + 1 which is the 2's complement, which would be the absolute value of x. 

3) Question 3 takes in an input of x. y would equal the logical negation of x, which would mean that any number value that is not equal to 0 would become a 0 and a value equal to 0 would become 1. If x is positive or 0, z will be 32 bits of 0's and if x is negative, z will be 32 bits of 1's. Given the x value, if it is positive, you have the z value equaling 0 or 0 which is 0, if x is negative you have the z value equaling 1 or 0 which is 1, and if x is 0 you have the z value equaling 0 or 1 which is 1. The final line returns the logical negation of z, which would be 0 for negative numbers and 0, and 1 for positive numbers.

4) Question 4 takes in an input of n. It first changes the value to a 0 or 1 depending on if it is equal to 0 or not equal to 0. When it is equal to 0, n becomes 0 and then is shifted 31 times to the left giving us 32 bits of 0's. If n is not equal to 0, n becomes 1 and then is shifted 31 times to the left giving us 1 followed by 31 bits of 0's. x is then shifted to the right 31 times, giving us 32 bits of 0's for when n is 0 and 32 bits of 1's for when n is not equal to 0. y will always be 1 followed by 31 0's after the left shift. It then shifts to the right based on (n + (~0)) which is equivalent to just n-1. This means that including the 1 already in y, the shift would make y equal to n number of 1's followed by 0's to finish off the 32 bits. The final line for a n value not equal to zero would just return y because x is 32 bits of 1's and would not be dependent on x, and when n is equal to 0, the return value would always be 0 because x is equal to 32 bits of 0's.

5) Question 5 takes in a value x. The code then shifts the value 31 times to the left to get the value of result. This is dependent on whether the number is odd or even because that determines if there is a 1 on the right most bit. If x is odd, then there would be a 1 in the right most bit, and the 31 bit shift to the left would leave us with 1 followed by 31 bits. If x is even (assuming 0 is also even), then there would be a 0 in the right most bit, and the 31 bit shift to the left would leave us with just 32 bits of 0's. The code then shifts the result back right 31 times. If x was even, then this would result in a return value of 0, and if x was odd, then this would result in a return value of -1 because it shift would make result equal 32 bits of 1's and in 2's complement that is -1.

6) Question 6 intializes byte as 0x55 which is equivalent to 0101 0101. Then the code takes byte and shifts it to the left 8 bits filled with 0's and ors it with byte which gives us 0101 0101 or 0101 0101 0000 0000 which is is equivalent to 0101 0101 0101 0101. The same concept is used in the next line, just with a 16 bit shift, effectively doubling the bit value again giving us 8 blocks of 0101.

7) Question 7 takes an input of x. ~x+1 is equlivalent to the 2's complement of x. With bitwise and, if you and x and its 2's complement, you get a bit value equal to sets of 0's followed by a 1 in the slot where the rightmost 1 is located on x, followed by more 0's.

8) Question 8 takes in an input of x. Depending on x, if it is negative y is equal to 32 bits of 1's or -1 because it would be a 1 in the 32nd bit shifted over 31 times filling the rest of the slots with 1's, and if it is 0 or positive y is equal to 32 bits of 0's or 0 because there would be a 0 in the 32nd slot and shifted of 31 times to the right would just be 0. z, which also depends on x, is 0 if x is equal to 0 and is 1 if x is not equal to 0. Bitwise or'ing y and z would give us 32 bits of 1's when x is negative because it is only dependent on y when x is 0, equaling -1. Bitwise or'ing y and z would give us 32 bits of 0's when x is 0 because it would just be 32 bits of 0 or 0. Bitwise or'ing y and z would give us 1 bit of 1 when x is positive because z would be 1 and y is still 32 bits of 0's, thus only being dependant on the 1 bit of 1. 

9) 

10) Question 10 takes in an input of x. y is equal to 0 if x is equal to 0 and is equal to 1 if x is not equal to 0. This is because the y is the double logical negation, returning only 1 or 0 instead of what x really is. z is dependant on multiple factors. If x is equal to 0, than z is equal to 1 because the logical negation of 0 is 1. When x is positive or negative, z would equal 0 because the logical negation of any number would be 0, and adding two positive numbers or two negative numbers would never result in 0. There is one case however, where a value not equal to zero would be 1 which is when x is equal to 1 followed by 31 0's. This is because when you add 1 followed by 31 0's to itself, it would overflow the memory because 32 bits is the maximum amount of memory we can store in an int, and that would overflow to the 33rd bit, which means x + x would be equal to 32 bits of 0's, and logically negating that would give us 1. The return value for all cases would be 0 except for the maximum sized number in memory we can store equaling x (1 followed by 31 0's) would return 1. 

11) 

12) Question 12 takes in three inputs, x , m, and n. The code initializes a to be equal to the 2's complement of m or the negated value of m with ~m+1, and the code also initializes b to be equal to the 2's complement of x which is equal to the negated value of x with ~x+1. When trying to figure out what a and b are equal to, you can look at a and b as negated values, so x+a is equivalent to x-m and b+n is equivalent to -x+n. The return value is fully dependent on whether there is a 1 in the 32nd bit because when shifting the number 31 times to the left, that would make it 32 bits of 1's instead of 0's making the return value 0 instead of 1 after the logical negation. The 1 will only be in the 32nd bit when the you or a and b and one of them are negative, so in the cases where x-m and n-x are negative, the return value will be 0 and for the rest, the return value will be 1. 

13) 

14) Question 14 takes in an input x, and then initializes result to equal 0 and an int i. For the loop, it has an exclusive or assignment to result taking the last bit and comparing it to 1 and constantly shifting once to the right, basically checking every bit for 32 bits. If you have a 1, you and that with a 1, getting a 1, and then exculsive or assignment to the existing 0 to to get a 1 as result. Following this pattarn, the code is looking for you if you have either an even or odd amount of 1's in the bit equivalent of the number. The code would print 0 if there are an even number of 1 bits and print 1 if there are an odd number of 1 bits.

15) 
