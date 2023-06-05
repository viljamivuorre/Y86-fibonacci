# Y86-fibonacci
The goal of the project was to translate this sequence of code to y86-64 assembly and optimize it.

bool isPerfectSquare(int x) {
    int s = sqrt(x);
    return (s*s == x);
}  

// Returns true if n is a Fibonacci Number, else false
bool isFibonacci(int x) {
    return isPerfectSquare(5*x*x + 4) || isPerfectSquare(5*x*x - 4);
}

The program checks the values in the array to see if they are Fibonacci numbers. The program stops and returns the first non-Fibonacci number in the register %rax
number. At the end of the array there is 0, which the program returns if all the numbers in the array are Fibonacci numbers.

Esim. alustus:
.pos 0
irmovq array,%r11
irmovq $233,%r12
rmmovq %r12,(%r11)
irmovq $377,%r12
rmmovq %r12,8(%r11)
irmovq $610,%r12
rmmovq %r12,16(%r11)
irmovq $987,%r12
rmmovq %r12,24(%r11)
irmovq $0,%r12
rmmovq %r12,32(%r11)

Y86 simulaattori netissä: https://boginw.github.io/js-y86-64/
