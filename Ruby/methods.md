##### <a name="methods">Methods</a>

Method checks to see if an integer is prime. Runs through the numbers 2 through the number minus 1 and divides the number by them. If any of the answers has no remainder, it says it is not prime.  If any have all remainders, it says it is prime.
```
def prime(n)
  puts "That's not an integer." unless n.is_a? Integer
  is_prime = true
  for i in 2..n - 1
    if n % i == 0
      is_prime = false
    end
  end

  if is_prime
    puts "#{n} is prime!"
  else
    puts "#{n} is not prime."
  end
end

prime(2)
prime(9)
prime(11)
prime(51)
prime(97)
prime(18)

// 2 is prime!
// 9 is not prime.
// 11 is prime!
// 51 is not prime.
// 97 is prime!
// 18 is not prime.
```
```
def array_of_10
  puts (1..10).to_a
end

array_of_10

// 1
// 2
// 3
// 4
// 5
// 6
// 7
// 8
// 9
// 10
```

Method that squares a number that is put in.
```
def square(n)
  puts n ** 2
end

square(12)
square(3)
square(8)

// 144
// 9
// 64
```
```
def greeter(name)
  return "Hello, " + name + "!"
end

output = greeter("Nomi")
puts output

// Hello, Nomi!
```
```
def by_three?(number)
  return number % 3 == 0
end

output = by_three?(9)
puts output

output = by_three?(7)
puts output

// true
// false
```

Method that capitalizes a word
```
def capitalize(string)
  puts "#{string[0].upcase}#{string[1..-1]}"
end

capitalize('ryan')      // Ryan
capitalize('jane')      // Jane
capitalize('michAel')   // MichAel
```
```
def alphabetize(arr, rev=false)
  if rev
    arr.sort { |item1, item2| item2 <=> item1 }   # decending order
  else
    arr.sort { |item1, item2| item1 <=> item2 }   # acending order
  end
end

books = ['Pride and Prejudice', 'Sense and Sensibility', 'Emma', 'Mansfield Park']

puts "A-Z: #{alphabetize(books)}"
puts "Z-A: #{alphabetize books, true}"

// A-Z: ["Emma", "Mansfield Park", "Pride and Prejudice", "Sense and Sensibility"]
// Z-A: ["Sense and Sensibility", "Pride and Prejudice", "Mansfield Park", "Emma"]
```

To put numbers in order from smallest to largest
```
def alphabetize(arr, rev=false)
  arr.sort!
end

numbers = [5,6,2,4]

puts alphabetize(numbers)

// 2
// 4
// 5
// 6
```
```
def alphabetize(arr, rev=false)
  arr.sort!
  if rev
    arr.reverse!
  else
    arr.sort!
  end
end

numbers = [5,1,3,8]

puts alphabetize(numbers)

// 1
// 3
// 5
// 8
```
```
def alphabetize(arr, rev=false)
  arr.sort!
  if rev
    arr.reverse!
  else
    arr.sort!
  end
end

numbers = [5,1,3,8]

puts alphabetize(numbers, true)

// 8
// 5
// 3
// 1
```
