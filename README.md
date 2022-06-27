# collatz-conjecture
The Collatz conjecture is one of the most famous unsolved problems in mathematics.

## Backdrop

> The Collatz conjecture states that the orbit of every number under $f$ eventually reaches 1. And while no one has proved the conjecture, it has been verified for every number less than $2^{68}$. 

Consider the following operation on an arbitrary positive integer:

- If the number is even, divide it by two.
- If the number is odd, triple it and add one.

In modular arithmetic notation, define the function f as follows:

$$ 
f(n) = \begin{cases} 
n / 2 & \text{if $n$ is even } \\ 
3n+1 & \text{if $n$ is odd } 
\end{cases}\
$$

Now form a sequence by performing this operation repeatedly, beginning with any positive integer, and taking the result at each step as the input at the next.

The Collatz conjecture is: _This process will eventually reach the number 1, regardless of which positive integer is chosen initially._

## Prerequisite

Install [wasmtime](https://wasmtime.dev/), [wasmer](https://wasmer.io/), [wasmedge](https://wasmedge.org/) or any other popular wasm-runtime at your system to execute the `.wasm` file.

## Usage

The program can be executed as

    wasmer collatz-conjecture.wasm <number>

where, 1 $\ge$ `<number>` $\ge$ INT_MAX 

for e.g.,

    wasmer collatz-conjecture.wasm 1234567890

_Note: wasmer could be replaced from any other wasm-runtime._

## Build

Compile the source code 

    grain compile collatz-conjecture.gr

Execute the generated `.wasm` file

    grain run collatz-conjecture.wasm 123

