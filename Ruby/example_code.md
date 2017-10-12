# <a name="top">Topics</a>

### [Loops and Iterators](loops_iterators.md)
  * [.each iterator](loops_iterators.md#each_iterator)
  * [.times iterator](loops_iterators.md#times_iterator)
  * [while loop](loops_iterators.md#while_loop)
  * [until loop](loops_iterators.md#until_loop)
  * [for loop](loops_iterators.md#for_loop)
  * [upto](loops_iterators.md#upto)
  * [collect](loops_iterators.md#collect)

  - [array.sort](arrays.md#array.sort)

### [Hashes](hashes.md#hashes)
  - [literal notation](#literal_notation)

### [Histogram](#histogram)
### [Methods](methods.md#methods)
### [Splat Arguments](#splat_arguments)
### [Return](#return)
### [Operators](operators.md#operators)
  - [Compair Operators](Ruby/operators.md#compair_operators)
  - [Conditional Assignment](Ruby/operators.md#conditional_assignment)

### [respond_to?](#respond_to?)
### [bank account example](#bank_account)


## Examples :point_up:[top](#top)

```
print "Integer please: "
user_num = Integer(gets.chomp)

if user_num < 0
  puts "You picked a negative integer!"
elsif user_num > 0
  puts "You picked a positive integer!"
else
  puts "You picked zero!"
end
```
```
print "Thtring, pleathe!: "
user_input = gets.chomp
user_input.downcase!

if user_input.include? "s"
  user_input.gsub!(/s/, "th")
else
  puts "nothing to do here!"
end

puts "Your string is: #{user_input}"
```
```
counter = 1
while counter < 11
  puts counter
  counter = counter + 1
end

OR

counter = 1
until counter > 10
  puts counter
  counter += 1
end
```
`+=` assignment operator. Add 1 to counter, then assign the new value back to counter

When you know exact number of loops
```
for num in 1...10
  puts num
end
```
`...` - don't include highest number in range
`..` - include highest number in range

```
def a
  puts "A was evaluated!"
  return true
end

def b
  puts "B was also evaluated!"
  return true
end

puts a || b
puts "-------------"
puts a && b

# A was evaluated!
# true
# -------------
# A was evaluated!
# B was also evaluated!
# true
```


##### Hiding information :point_up:[top](#top)

```
puts "Text to search through: "
text = gets.chomp
puts "Word to redact: "
redact = gets.chomp

words = text.split(" ")

words.each do |word|
  if word != redact
    print word + " "
  else
    print "REDACTED"
  end
end
```



##### <a name="histogram">Histogram</a> :point_up:[top](#top)
```
puts "Text please: "
text = gets.chomp

words = text.split(" ")

frequencies = Hash.new(0)

words.each { |word| frequencies[word] += 1 }

frequencies = frequencies.sort_by { |a, b| b }

frequencies.reverse!

frequencies.each { |word, frequency| puts word + " " + frequency.to_s }

// Text please:
// sit in the car and sit in the house
// the 2
// in 2
// sit 2
// house 1
// and 1
// car 1
```



##### <a name="splat_arguments">Splat Arguments</a> :point_up:[top](#top)

`*` splat signals to Ruby that we don't know how many there are going to be, but it could be more than one.
```
def friend(*name)
  puts "My friend is " + name.to_s + "."
end

friend("Bob", "Sammy", "Eric", "Ralph")

// My friend is ["Bob", "Sammy", "Eric", "Ralph"].

def what_up(greeting, *bros)
  bros.each { |bro| puts "#{greeting}", "#{bro}!" }
end

what_up("What up", "Justin", "Ben", "Kevin Sorbo")

// What up
// Justin!
// What up
// Ben!
// What up
// Kevin Sorbo!
```
Only one greeting `"What up"`, multiple names `"Justin", "Ben", "Kevin Sorbo"`


##### <a name="return">Return</a> :point_up:[top](#top)

```
def double(n)
  return n * 2
end

output = double(6)
output += 2
puts output

// 14
```
```
def multiple_of_three(n)
  return n % 3 == 0? "True" : "False"
end

def multiple_of_three(n)
  n % 3 == 0? "True" : "False"
end

puts multiple_of_three(9)   # True
puts multiple_of_three(10)  # False
```

##### <a name="respond_to?">respond_to?</a> :point_up:[top](#top)

```
[1,2,3].respond_to?(:push)
```
would return true since you can call .push on an array object

```
[1,2,3].respond_to?(:to_sym)
```
would return false since you can't turn an array into a symbol

##### <a name="bank_account">bank account example</a> :point_up:[top](#top)

```
class Account
  attr_reader :name, :balance

  def initialize(name, balance = 100)
    @name = name
    @balance = balance
  end

  def display_balance(pin_number)
    puts pin_number == pin ? "Balance: $#{@balance}." : pin_error
  end

  def withdraw(pin_number, amount)
    if pin_number == pin
      @balance -= amount
      puts "Withdrew #{amount}. New balance: $#{@balance}."
    else
      puts pin_error
    end
  end

  private

  def pin
    @pin = 1234
  end

  def pin_error
    "Access denied: incorrect PIN."
  end
end

my_account = Account.new("Eric", 1_000_000)
my_account.withdraw(11, 500_000)            # Access denied: incorrect PIN.
my_account.display_balance(1234)            # Balance: $1000000.
my_account.withdraw(1234, 500_000)          # Withdrew 500000. New balance: $500000.
my_account.display_balance(1234)            # Balance: $500000.

```

:point_up:[top](#top)
