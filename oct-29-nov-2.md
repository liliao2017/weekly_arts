# Oct 29 - Nov 2

## Tips

1. setUpClass\(\) and setUp\(\)

Both methods are used in python unittest framework, the difference is that setUpClass\(\) is called for each test class, and setUp\(\) is called for each method. And it's the same for tearDown\(\) and tearDownClass\(\).

2. namedtuple

namedtuple can be used as a simplified class, here is a demo of how to use it:

```text
from collections import namedtuple

# 定义一个namedtuple类型User，并包含name，sex和age属性。
User = namedtuple('User', ['name', 'sex', 'age'])

# 创建一个User对象
user = User(name='kongxx', sex='male', age=21)

# 也可以通过一个list来创建一个User对象，这里注意需要使用"_make"方法
user = User._make(['kongxx', 'male', 21])

print user
# User(name='user1', sex='male', age=21)

# 获取用户的属性
print user.name
print user.sex
print user.age

# 修改对象属性，注意要使用"_replace"方法
user = user._replace(age=22)
print user
# User(name='user1', sex='male', age=21)

# 将User对象转换成字典，注意要使用"_asdict"
print user._asdict()
# OrderedDict([('name', 'kongxx'), ('sex', 'male'), ('age', 22)])
--------------------- 
作者：kongxx 
来源：CSDN 
原文：https://blog.csdn.net/kongxx/article/details/51553362 
版权声明：本文为博主原创文章，转载请附上博文链接！
```





