---
layout: post
title: "Reducing Function Argument Count"
date: "2017-07-01 18:13:30 +0300"
categories: programming, quality
external_url: https://www.amazon.co.uk/Clean-Code-Handbook-Software-Craftsmanship/dp/0132350882
---
If you read books like [Clean Code]({{ page.external_url }}) you would have come across recommendations for function parameter count. Basically it says that the more arguments the more questioning you should be about your code design.

A function should preferably have no arguments (niladic). Then the recommendations go on and list a **few** cases where **one** function argument (monadic) is ok to use. Even fewer justifications for two arguments (diadic) and so on.

When I first came across this I really liked the idea. However, I didn't understand how to practically apply it to my daily coding routine. As if I knew the cause that my code was suffering from, but din't know how to improve it. Because when I looked at my code it had patterns like this:

```PHP
class UserRepository
{
  public function getAllByCompany($companyId, $type, $isActive)
  {
    // SQL query
  }
}
```

We can improve the function by extracting the `$type` and `$isActive` arguments into different functions. But what if I wanted to even get rid of `$companyId`?

This is a very basic example and you could argue that having the company identifier is justifiable. However, for the sake of this discussion, lets say that we want to make the function niladic.

## The Answer

Constructors.

```
class UserRepository
{
  private $companyId;

  public function __construct($companyId)
  {
    $this->companyId = $companyId;
  }

  public function getAllActiveAdmins()
  {
    // SQL query
  }
}
```

I can design the code so that the user repository takes company identifier as a constructor argument. Languages like Java allow constructor overloading which make the solution even cleaner.

For me it is clear how the recommendation to reduce function arguments has made me think about my design and potential improvements. Even my programmer's thinking has changed in the way of more object oriented style because now my class is instantiated with a state. Not just dumb retrieval. My user repository usage in code is cleaner and more readable. I can instantiate the class once and retrieve the users afterwards without dragging the company identifier along.
