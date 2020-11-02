## <center><font color=#5C4033>Min Stack</font></center>

### <font color=#FF7F00>题目</font>
Design a stack that supports push, pop, top, and retrieving the minimum element in constant time.

1. push(x) -- Push element x onto stack.
2. pop() -- Removes the element on top of the stack.
3. top() -- Get the top element.
4. getMin() -- Retrieve the minimum element in the stack.

[原始链接](https://leetcode-cn.com/problems/min-stack/)

### <font color=#FF7F00>Java代码</font>
```java
class MinStack{
    Deque<Integer> xStack;
    Deque<Integer> minStack;

    public MinStack(){
        xStack = new LinkedList<Integer>();
        minStack = new LinkedList<Integer>();
        minStack.push(Integer.MAX_VALUE);
    }

    public void push(int x){
        xStack.push(x);
        minStack.push(Math.min(minStack.peek(),x));
    }

    public void pop(){
        xStack.pop();
        minStack.pop();
    }

    public int top(){
        return xStack.peek();
    }

    public int getMin(){
        return minStack.peek();
    }
}
```