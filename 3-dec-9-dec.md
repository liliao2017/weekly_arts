# 3 Dec - 9 Dec

## Review

Interesting python tips

{% embed url="https://github.com/satwikkansal/wtfpython" %}

{% embed url="https://github.com/leisurelicht/wtfpython-cn" %}

**str -&gt; dict**

```text
some_string = "wtf"
some_dict = {}
for i, some_dict[i] in enumerate(some_string):
    pass
```

**Output:**

```text
>>> some_dict # 创建了索引字典.
{0: 'w', 1: 't', 2: 'f'}
```

**class attributes and instance attributes**

```text
class SomeClass:
    some_var = 15
    some_list = [5]
    another_list = [5]
    def __init__(self, x):
        self.some_var = x + 1
        self.some_list = self.some_list + [x]
        self.another_list += [x]
```

**Output**

```text
>>> some_obj = SomeClass(420)
>>> some_obj.some_list
[5, 420]
>>> some_obj.another_list
[5, 420]
>>> another_obj = SomeClass(111)
>>> another_obj.some_list
[5, 111]
>>> another_obj.another_list
[5, 420, 111]
>>> another_obj.another_list is SomeClass.another_list
True
>>> another_obj.another_list is some_obj.another_list
True
>>> another_obj.some_list is some_obj.some_list
False
>>> another_obj.some_list is SomeClass.some_list
False
```

The `+=` operator modifies the mutable object in-place without creating a new object. So changing the attribute of one instance affects the other instances and the class attribute as well.

注意最后四行的差别。对list来讲，＋＝会直接修改原变量，因此，类实例中的another\_list和类变量another\_list指向同一个对象。

