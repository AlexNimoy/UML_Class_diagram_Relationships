# UML

### Наследование

![Наследование](./img/Inheritance.svg)

```ruby
class A < B
end
```

## Сила связей

### Зависимость

![Зависимость](./img/Dependency.svg)

```ruby
class A
  def some_method
    B.new
  end
end
```

### Ассоциация

![Ассоциация](./img/Association.svg)

```ruby
class A
  def some_method(b)
    b.call
  end
end

# ИЛИ

class A
  def some_method(b: B.new)
    b.call
  end
end
```

### Агрегация

![Агрегация](./img/Aggregation.svg)

```ruby
class A
  def initialize(b)
    @b = b || B.new
  end
end

# ИЛИ

class A
  def initialize(b: B.new)
    @b = b
  end
end

# ИЛИ

class A
  def initialize(**args)
    @b = args[:b] || B.new
  end
end
```

### Композиция

![Композиция](./img/Composition.svg)

```ruby
class A
  def initialize
    @b = B.new
  end
end
```