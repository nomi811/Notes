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

#### Loops & Iterators

Repeat an action using an **iterator**. Iterator invokes a block of code.  The code block is just the bit that contains the instructions to be repeated. When you loop over an array or a hash, you say that you *iterate* over it.

```
i = 0
loop do
  i += 1
  print "#{i}"
  break if i > 5
end
```

Prints just odd numbers
```
for i in 1..5
  next if i % 2 == 0
  print i
end
```
Prints just even numbers
```
for i in 1..5
  next if i % 2 != 0
  print i
end
```

##### .each iterator
```
array = [1,2,3,4,5]

array.each do |x|
  x += 10
  print "#{x}"
end

=> 1112131415
```

##### .times iterator
```
10.times {print "Chunky bacon!"}

OR

10.times do
  print "Chunky bacon!"
end

=> Will print Chunky bacon! 10 times with no spaces after exclamation point.
```

##### while loop

```
i = 3

while i > 0 do
  print i
  i -= 1
end

=> 321
```

##### until loop

```
i = 3

until i == 0 do
  print i
  i -= 1
end

=> 321
```

##### for loop

```
for k in 1..3
  print k
end

=> 123
```

##### array

```
[1,2,3,4,5]
 0 1 2 3 4 index numbers

```
```
array = [1,2,3,4,5]

print array[2]

=> 3
```

 string array `["hello", "car", "dog"]`
 2 dimensional array - array of arrays - multidimensional `[[0,0,0,0], [0,0,0,0,], [0,0,0,0], [0,0,0,0]]`
```
multi_d_array = [[1,2,3,4], [5,6,7,8], [9,10,11,12]]

multi_d_array.each { |x| puts "#{x}\n"}

=>  [1, 2, 3, 4]
    [5, 6, 7, 8]
    [9, 10, 11, 12]

print multi_d_array[1][3]

=> 8
```

##### Hiding information

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

##### hashes

a hash is a collection of key-value pairs

```
hash = {
  key1 = value1,
  key2 = value2,
  key3 = value3
}
```
**literal notation**
```
my_hash = { "name"    => "Eric",
            "age"     => 26,
            "hungry?" => true
}

puts my_hash["name"]    // Eric
puts my_hash["age"]     // 26
puts my_hash["hungry?"] // true
```