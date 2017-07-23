---
layout: post
title: "Immutable DTOs"
date: "2017-07-02 19:54:36 +0300"
tags: programming design maintainability
external_url: http://idiorm.readthedocs.io
---

Data from the DB is often retrieved as plain key value arrays. Even projects that use ORMs like [this]({{ page.external_url }}) or other active record implementations do not improve the situation.

We either pass around full-blown active record objects or arrays like this:
```
Array
(
    [id] => 1
    [name] => User name
    [type] => User type
    [created_at] => 2017-01-01 00:00:00
)
```

Often its usage would be multiple nestings down, where its origin is hard to trace. Often it would even be modified somewhere inbetween.

There are multiple problems resulting from this, to name a few:
* Accessing array element by key
* Looking up the original retrieval function to know what data the array contains
* Time consuming backtrace analyzing

We need a data structure for conveniently using the data afterwards. When trying to find a better solution, I was contemplating different ideas:
* POPOs - classes with public fields only and no methods
* DTOs with setters and getters

### The compromise

Immutable DTOs (no setters).

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

$user = new UserDTO($dbUser['name'], $dbUser['type']);
```

Then if you need to modify the data, initialize a new object:
```
$changedUser = new UserDTO($user->name(), 'new type');
```

Most GUIs are able to use the autocomplete functionality on those objects, considering they are properly type-hinted. Also, this allows me to create the DTO once and stop worrying that it could be changed in the process - increased readability and maintainability. Possibility to look up object initialization occurrences - increased traceability.

*I am not an advocate of DTOs as they hurt the OOP design. However, in some real world/legacy systems this is the only solution.*
