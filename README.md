# Project1_group15 </br>

1) Question 1 take an input x and takes the 2's complement of x by taking the invert of x and adding 1. Then z is taken as the invert of y or x, and this value is shifted 31 bits to the right. It then returns z & 1. This is dependent on what input is taken in. If x is anything other than 0, the code will return 0. If the input is 0, then the 2's complement of it to get 32 to bits of 0's because of the +1 overflow, and then we take the invert of 32 bits of 0's to get 32 bits of 1's. Shifting that 31 times to the right gives us 1 as the final value of z, and z & z is equal to 1.
</br>
2) Question 2 takes in an input x and then shifts the value 31 bits to the right. If the value is positive or 0, the mask value will be 32 bits of 0's, and if x is negative, the mask value will be 32 bits of 1's. y is x exclusive or the mask value, so when you have the mask as 32 bits of 0's y would equal x, and when you have 32 bits of 1's y would be the invert of x. Adding 1 to an invert mask equal to 32 bits of 1's would be 32 bits of 0's due to overflow, and adding 1 to the invert mask equal to 32 bits of 0's would give you 1. For the return value, when x is positive, you end up with x + 0 = x, and when x is negative, you end up with the ~x + 1 which is the 2's complement, which would be the absolute value of x. 
</br>
3) 
