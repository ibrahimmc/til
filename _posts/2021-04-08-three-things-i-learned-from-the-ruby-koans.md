---
layout: post
title: Three things I learned from The Ruby Koans
---

Here are (at least) three things I learned from [The Ruby Koans](http://rubykoans.com/):

## 1- Overarching lesson: how to name variables, classes, tests and methods in a useful, user-friendly way

One important skill that I've tried to integrate from the Koans is how to **intelligently** name variables. It seems so easy to read compared to the code that I usually produce, so I tried to pick up on the syntax to uncover what the Koan author is doing, and _why it works_.

## 2- Better understanding and appreciation about how objects work in Ruby

In the `about_objects` Koan, I learnt that every initialized object has a different `id` through the following codeblock:

```ruby
  def test_every_object_has_different_id
    obj = Object.new
    another_obj = Object.new
    assert_equal true, obj.object_id != another_obj.object_id
  end
```
This is even true when we use the clone method to create a different object:

```ruby
  def test_clone_creates_a_different_object
    obj = Object.new
    copy = obj.clone

    assert_equal true, obj           != copy
    assert_equal true, obj.object_id != copy.object_id
  end
```

In the `about_symbols` Koan however, I saw how identical `symbols` are the same internal object through the test:

```ruby
  def test_identical_symbols_are_a_single_internal_object
    symbol1 = :a_symbol
    symbol2 = :a_symbol

    assert_equal true, symbol1           == symbol2
    assert_equal true, symbol1.object_id == symbol2.object_id
  end
```

## 3- Learning how to use block code

In the `about_iteration` Koan, I learnt how to implement block code for simple iterations. A simple implementation of a `sum` method would look like this:
> array.each { |item| sum += item }


