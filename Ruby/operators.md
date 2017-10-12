# Operators


`<=>` compairs two objects numerically or alphabetically

shows `0` if they are equal
shows `-1` if first is less than second
shows `1` if first is greater than second

##### <a name="conditional_assignment">Conditional Assignment</a>

```
favorite_book = nil
puts favorite_book    #

favorite_book ||= "Cat's Cradle"
puts favorite_book    # Cat's Cradle

favorite_book ||= "Why's (Poignant) Guide to Ruby"
puts favorite_book    # Cat's Cradle

favorite_book = "Why's (Poignant) Guide to Ruby"
puts favorite_book    # Why's (Poignant) Guide to Ruby
```

`.push` same as `<<` same as `+`

```
[1,2,3] << 4    # gives [1,2,3,4]
```
```
"Yukishiro" << "Matsumoto"    # gives "Yukishiro Matsumoto"
```
