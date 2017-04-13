Keep in mind there are many different solutions to each of these prompts.

# Maskify

```rb
def maskify(input)
  character_array = input.split('').reverse
  output_array = character_array.each_with_index.map do |character, index|
    if index > 3
      '*'
    else
      character
    end
  end
  output_array.reverse.join
end
```
or...
```rb
def maskify(cc)
  (cc.length-4).times do |i|
    cc[-5-i] = "#"
  end
  cc
end
```

# Caesar Cipher II

```rb
def caesar(input, rotate_index)
  letters = ('a'..'z').to_a
  cipher = letters.rotate(rotate_index)
  character_array = input.split('')
  output_array = character_array.map do |character|
      cipher[letters.index(character)]
  end
  output_array.join
end
```

# Caesar Cipher II (with Bonus)

```rb
def caesar(input, rotate_index)
  letters = ('a'..'z').to_a
  cipher = letters.rotate(rotate_index)
  character_array = input.split('')
  output_array = character_array.map do |character|
    if letters.include?(character)
      cipher[letters.index(character)]
    elsif letters.include?(character.downcase)
      cipher[letters.index(character.downcase)].upcase
    else
      character
    end
  end
  output_array.join
end
```

# Atbash Cipher

```rb
def atbash(input)
  letters = ('a'..'z').to_a
  letters_inverse = ('a'..'z').to_a.reverse
  character_array = input.split('')
  output_array = character_array.map do |character|
    if letters.include?(character)
      letters_inverse[letters.index(character)]
    elsif letters.include?(character.downcase)
      letters_inverse[letters.index(character.downcase)].upcase
    else
      character
    end
  end
  output_array.join
end
```
