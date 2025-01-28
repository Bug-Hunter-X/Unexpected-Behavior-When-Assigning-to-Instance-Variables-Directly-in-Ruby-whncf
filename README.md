# Unexpected Behavior When Assigning to Instance Variables Directly in Ruby

This example demonstrates a potential issue in Ruby where directly assigning values to instance variables without explicitly defining setter methods can lead to unexpected behavior.  The issue is related to how Ruby handles attribute access and the implicit creation of getter methods.

## The Problem

In Ruby, if you define an instance variable (`@value` in this case), Ruby automatically creates a getter method (`value`) that allows you to read the instance variable's value. However, there's no implicit setter method created unless you explicitly define it.

Attempting to assign a new value using `my_object.value = 30` will cause a `NoMethodError` because Ruby is looking for a setter method (`value=`) which doesn't exist. This could be confusing for programmers coming from other languages where direct assignment to instance variables is more common.

## The Solution

The solution is to either use `instance_variable_set` to modify instance variables directly or define a proper setter method in your class to achieve the desired modification.