### Question
https://leetcode.com/problems/implement-queue-using-stacks/

### Solution
```JAVA
class MyQueue {

    Stack<Integer> stackA;
    Stack<Integer> stackB;
    
    public MyQueue() {
        stackA = new Stack<>();
        stackB = new Stack<>();
    }
    
    public void push(int x) {
        if(stackA.isEmpty()) {
            stackA.push(x);
        } else {
            while(!stackA.isEmpty()) {
                stackB.push(stackA.pop());
            }
            
            stackA.push(x);
            
            while(!stackB.isEmpty()) {
                stackA.push(stackB.pop());
            }
        }
    }
    
    public int pop() {
        return stackA.pop();
    }
    
    public int peek() {
        return stackA.peek();
    }
    
    public boolean empty() {
        return stackA.isEmpty();
    }
}
```
