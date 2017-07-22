---
layout: post
title: "Immutable DTOs"
date: "2017-07-02 19:54:36 +0300"
tags: programming design maintainability
external_url: idiorm.readthedocs.io
---

I came up with this *compromise* at my current work place where we use [ORM]({{ page.external_url }}) for interactions with database. We have a quite a large number of repository type of classes. In a lot of cases they returned a plain PHP key value array.

Similar to this:
```
Array
(
    [id] => 1
    [name] => Entity name
    [type] => Entity type
    [created_at] => 2017-01-01 00:00:00
)
```

Then this PHP array was passed around to wherever it was used afterwards. Often its usage would be multiple nestings down where its origin is hard to trace. Often it would even be modified somewhere in between.

There are multiple problems resulting out of this, to name a few:
* Accessing array element by key
* Needing to look up the retrieval function to know what data the array contains
* Time consuming backtrace analyzing

When trying to find a better solution I was contemplating different ideas:
* POPOs
* DTOs with setters and getters

### The compromise

Immutable DTOs.

```
class UserDTO
{
  private $name;
  private $type;

  public function __construct($name, $type)
  {
    $this->name = $name;
    $this->type = $type;
  }

  public function name()
  {
    return $this->name;
  }

  public function type()
  {
    return $this->type;
  }
}
```

Within this current system it is the best solution. They allow me to create the object once without worrying that it could be changed in the process. Most GUIs are able to use autocomplete functionality on those objects considering they are properly type-hinted.

*Disclaimer: I am not an advocate of DTOs as they hurt the OOP design. However in many real world/legacy systems this is a good solution.*
