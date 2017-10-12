#Loops & Iterators

* [.each iterator](#each_iterator)
* [.times iterator](#times_iterator)
* [while loop](#while_loop)
* [until loop](#until_loop)
* [for loop](#for_loop)

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

##### <a name="each_iterator">.each iterator</a>
```
array = [1,2,3,4,5]

array.each do |x|
  x += 10
  print "#{x}"
end

// 1112131415
```

##### <a name="times_iterator">.times iterator</a>
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

##### <a name="while_loop">while loop</a>

```
i = 3

while i > 0 do
  print i
  i -= 1
end

// 321
```

##### <a name="until_loop">until loop</a>

```
i = 3

until i == 0 do
  print i
  i -= 1
end

// 321
```

##### <a name="for_loop">for loop</a>

```
for k in 1..3
  print k
end

// 123
```