# 3 Dec - 9 Dec

## Review

Interesting python tips

{% embed url="https://github.com/satwikkansal/wtfpython" %}

{% embed url="https://github.com/leisurelicht/wtfpython-cn" %}

str -&gt; dict

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

