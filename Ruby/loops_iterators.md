# <a name="top">Loops & Iterators</a>

* [.each iterator](#each_iterator)
* [.times iterator](#times_iterator)
* [while loop](#while_loop)
* [until loop](#until_loop)
* [for loop](#for_loop)
* [upto](#upto)
* [collect](#collect)

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

##### <a name="each_iterator">.each iterator</a> :point_up:[top](#top)
```
array = [1,2,3,4,5]

array.each do |x|
  x += 10
  print "#{x}"
end

// 1112131415
```
```
[1,2,3].each { |x| puts x * 10 }

# 10
# 20
# 30
```

##### <a name="times_iterator">.times iterator</a> :point_up:[top](#top)
```
10.times {print "Chunky bacon!"}

OR

10.times do
  print "Chunky bacon!"
end

// Will print Chunky bacon! 10 times with no spaces after exclamation point.
```
```
1.times do
  puts "I'm a code block"
end

1.times { puts "As am I!" }

// I'm a code block
// As am I!
```
```
5.times { puts "Odelay!" }

# Odelay!
# Odelay!
# Odelay!
# Odelay!
# Odelay!
```

##### <a name="while_loop">while loop</a> :point_up:[top](#top)

```
i = 3

while i > 0 do
  print i
  i -= 1
end

// 321
```

##### <a name="until_loop">until loop</a> :point_up:[top](#top)

```
i = 3

until i == 0 do
  print i
  i -= 1
end

// 321
```

##### <a name="for_loop">for loop</a> :point_up:[top](#top)

```
for k in 1..3
  print k
end

// 123
```

##### <a name="upto">upto</a> :point_up:[top](#top)

```
95.upto(100) { |num| print num, " " }

# 95 96 97 98 99 100
```
```
"L".upto("P") { |letter| puts letter, " " }

# L

# M

# N

# O

# P
```

##### <a name="collect">collect</a> :point_up:[top](#top)

```
my_nums = [1,2,3]
puts my_nums
puts "------------"
my_nums.collect { |num| num ** 2 }

puts my_nums
puts "*************"

my_nums = [1,2,3]
puts my_nums
puts "------------"
my_nums.collect! { |num| num ** 2 }

puts my_nums
```
collect doestn't actually change my_nums
collect! changes my_nums

:point_up:[top](#top)
