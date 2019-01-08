# Sep. 24 - 30

## Algorithm

Using two stacks \(first in last out\) to implement a queue \(first in first out\) with enqueue, dequeue size and get\_min methods.

Keep 2 stacks, let's call them inbox and outbox.

Enqueue:

* Push the new element onto inbox

Dequeue:

* If outbox is empty, refill it by popping each element from inbox and pushing it onto outbox
* Pop and return the top element from outbox

```text
Class MyQueue():
    def __init__():
        self.input = Stack()
        self.output = Stack()
        self.size = 0
        self.min = None
        
    def enqueue(e):
        self.input.push(e)
        self.size += 1
        self.min = min(self.min, e) if self.min else e
    
    def dequeue():
        if self.size == 0:
            # todo: exception handling
            return
        # move elements to output stack
        if not self.output:
            current_min = None
            while(self.input):
                current_element = self.output.pop()
                current_min = min(current_element, current_min) if current_min else current_element
                self.output.push((current_element, curent_min))
        
        # pop the pair
        pair = self.output.pop()
        value = pair[0]
        current_min = pair[1]
        # update min
        if value == self.min:
            if self.output:
                new_min = self.output.top()[1]
                self.min = new_min
            else:
                self.min = None
        else:
            pass
        self.size -= 1
        return value
    
    def size():
        return self.size
    
    def get_min():
        return self.min
```

举例：

push 1, push 4, push 2, pop

input: \[1\] size:1 min: 1 output: \[\]

input: \[1, 4\] size:2 min: 1 output: \[\]

input: \[1, 4, 2\] size:3 min: 1 output: \[\]

output: \[\(2,2\), \(4,2\), \(1,1\)\] -&gt;\[\(2,2\), \(4,2\)\] min: 2 size: 2 input: \[\] return 1

Another simple implementation \(only enqueue and dequeue\) using java:

```text
public class Queue<E>
{

    private Stack<E> inbox = new Stack<E>();
    private Stack<E> outbox = new Stack<E>();

    public void queue(E item) {
        inbox.push(item);
    }

    public E dequeue() {
        if (outbox.isEmpty()) {
            while (!inbox.isEmpty()) {
               outbox.push(inbox.pop());
            }
        }
        return outbox.pop();
    }

}
```



