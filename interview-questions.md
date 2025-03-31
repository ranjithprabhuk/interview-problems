# Software Engineering Interview Questions
*(All problems designed to be solved within 30-45 minutes)*

## Junior Level Candidates

### Easy
1. **Palindrome Checker**
   - **Problem**: Write a function to check if a string is a palindrome (reads the same forward and backward).
   - **Example**: Input: "racecar" → Output: true | Input: "hello" → Output: false
   - **Time frame**: 5-10 minutes

2. **Maximum Value**
   - **Problem**: Implement a function to find the maximum value in an array.
   - **Example**: Input: [3, 7, 2, 9, 1] → Output: 9
   - **Time frame**: 5-10 minutes

3. **String Reversal**
   - **Problem**: Write code to reverse a string without using built-in reverse functions.
   - **Example**: Input: "hello" → Output: "olleh"
   - **Time frame**: 5-10 minutes

4. **Character Counter**
   - **Problem**: Create a function that counts the occurrence of each character in a string.
   - **Example**: Input: "programming" → Output: {'p':1, 'r':2, 'o':1, 'g':2, 'a':1, 'm':2, 'i':1, 'n':1}
   - **Time frame**: 10-15 minutes

5. **Anagram Checker**
   - **Problem**: Implement a function that checks if two strings are anagrams.
   - **Example**: Input: "listen", "silent" → Output: true | Input: "hello", "world" → Output: false
   - **Time frame**: 10-15 minutes

6. **Array Sum**
   - **Problem**: Write code to find the sum of all elements in an array.
   - **Example**: Input: [1, 2, 3, 4, 5] → Output: 15
   - **Time frame**: 5-10 minutes

7. **Prime Number Check**
   - **Problem**: Create a function to determine if a number is prime.
   - **Example**: Input: 7 → Output: true | Input: 4 → Output: false
   - **Time frame**: 10-15 minutes

8. **FizzBuzz**
   - **Problem**: Print numbers from 1 to n, but print "Fizz" for multiples of 3, "Buzz" for multiples of 5, and "FizzBuzz" for multiples of both.
   - **Example**: Input: 15 → Output: [1, 2, "Fizz", 4, "Buzz", "Fizz", 7, 8, "Fizz", "Buzz", 11, "Fizz", 13, 14, "FizzBuzz"]
   - **Time frame**: 10-15 minutes

9. **Factorial Calculator**
   - **Problem**: Write a function to find the factorial of a number.
   - **Example**: Input: 5 → Output: 120 (5! = 5 × 4 × 3 × 2 × 1 = 120)
   - **Time frame**: 5-10 minutes

10. **Remove Duplicates**
    - **Problem**: Create a function that removes duplicates from an array.
    - **Example**: Input: [1, 2, 2, 3, 4, 4, 5] → Output: [1, 2, 3, 4, 5]
    - **Time frame**: 10-15 minutes

### Medium
1. **First Non-Repeating Character**
   - **Problem**: Write a function to find the first non-repeating character in a string.
   - **Example**: Input: "programming" → Output: 'p' (because it's the first character that appears only once)
   - **Time frame**: 15-20 minutes

2. **Linked List Cycle Detection**
   - **Problem**: Create a function to detect if a linked list has a cycle.
   - **Example**: Input: A→B→C→D→B (B is repeated, creating a cycle) → Output: true
   - **Time frame**: 20-25 minutes

3. **Binary Search**
   - **Problem**: Implement binary search on a sorted array.
   - **Example**: Input: [1, 3, 5, 7, 9, 11], target = 7 → Output: 3 (index of 7)
   - **Time frame**: 15-20 minutes

4. **Array Intersection**
   - **Problem**: Write code to find the intersection of two arrays.
   - **Example**: Input: [1, 2, 3, 4, 5], [3, 4, 5, 6, 7] → Output: [3, 4, 5]
   - **Time frame**: 15-20 minutes

5. **Balanced Parentheses**
   - **Problem**: Create a function that validates if a given string of parentheses is balanced.
   - **Example**: Input: "{[()]}" → Output: true | Input: "{[(])}" → Output: false
   - **Time frame**: 15-20 minutes

6. **Decimal to Binary**
   - **Problem**: Implement a function to convert a decimal number to a binary string.
   - **Example**: Input: 10 → Output: "1010"
   - **Time frame**: 15-20 minutes

7. **Kth Largest Element**
   - **Problem**: Write code to find the kth largest element in an unsorted array.
   - **Example**: Input: [3, 1, 5, 7, 2, 4, 6], k = 3 → Output: 5 (the 3rd largest element)
   - **Time frame**: 20-25 minutes

8. **Valid Binary Search Tree**
   - **Problem**: Create an algorithm to check if a binary tree is a valid binary search tree.
   - **Example**: Input: [4, 2, 6, 1, 3, 5, 7] (represented as a binary tree) → Output: true
   - **Time frame**: 20-25 minutes

9. **Two Sum**
   - **Problem**: Given an array of integers and a target sum, return indices of the two numbers that add up to the target.
   - **Example**: Input: [2, 7, 11, 15], target = 9 → Output: [0, 1] (because 2 + 7 = 9)
   - **Time frame**: 15-20 minutes

10. **String Compression**
    - **Problem**: Implement basic string compression using the counts of repeated characters.
    - **Example**: Input: "aabcccccaaa" → Output: "a2b1c5a3"
    - **Time frame**: 15-20 minutes

### Hard
1. **Longest Common Subsequence**
   - **Problem**: Write an algorithm to find the longest common subsequence between two strings.
   - **Example**: Input: "ABCDGH", "AEDFHR" → Output: "ADH" (length 3)
   - **Time frame**: 25-30 minutes

2. **Deep Clone**
   - **Problem**: Implement a deep clone function for arbitrary JavaScript objects.
   - **Example**: Input: {a: 1, b: {c: 2, d: [3, 4]}} → Output: A new object with the same structure but not referentially equal
   - **Time frame**: 25-30 minutes

3. **Word Search**
   - **Problem**: Given a 2D board and a word, find if the word exists in the grid.
   - **Example**: Input: board = [['A','B','C','E'],['S','F','C','S'],['A','D','E','E']], word = "ABCCED" → Output: true
   - **Time frame**: 25-30 minutes

4. **Merge Intervals**
   - **Problem**: Given a collection of intervals, merge all overlapping intervals.
   - **Example**: Input: [[1,3],[2,6],[8,10],[15,18]] → Output: [[1,6],[8,10],[15,18]]
   - **Time frame**: 20-25 minutes

5. **LRU Cache**
   - **Problem**: Implement an LRU (Least Recently Used) cache with O(1) time complexity for both get and put operations.
   - **Example**: LRUCache cache = new LRUCache(2 /* capacity */); cache.put(1, 1); cache.put(2, 2); cache.get(1); // returns 1; cache.put(3, 3); // evicts key 2; cache.get(2); // returns -1 (not found)
   - **Time frame**: 30-35 minutes

6. **String Permutations**
   - **Problem**: Create an algorithm to find all permutations of a string.
   - **Example**: Input: "abc" → Output: ["abc", "acb", "bac", "bca", "cab", "cba"]
   - **Time frame**: 25-30 minutes

7. **Coin Change**
   - **Problem**: Find the minimum number of coins needed to make change for a given amount.
   - **Example**: Input: coins = [1, 2, 5], amount = 11 → Output: 3 (5 + 5 + 1)
   - **Time frame**: 25-30 minutes

8. **Rotate Matrix**
   - **Problem**: Rotate an n x n 2D matrix by 90 degrees clockwise.
   - **Example**: Input: [[1,2,3],[4,5,6],[7,8,9]] → Output: [[7,4,1],[8,5,2],[9,6,3]]
   - **Time frame**: 25-30 minutes

9. **Jump Game**
   - **Problem**: Given an array of non-negative integers, you are initially positioned at the first index. Each element represents your maximum jump length at that position. Determine if you can reach the last index.
   - **Example**: Input: [2,3,1,1,4] → Output: true (Jump 1 step from index 0 to 1, then 3 steps to the last index)
   - **Time frame**: 20-25 minutes

10. **Container With Most Water**
    - **Problem**: Given n non-negative integers representing an elevation map where the width of each bar is 1, compute how much water it can trap after raining.
    - **Example**: Input: [1,8,6,2,5,4,8,3,7] → Output: 49
    - **Time frame**: 25-30 minutes

## Senior Level Candidates

### Easy
1. **Rate Limiter**
   - **Problem**: Design a rate limiter that restricts the number of API calls within a time frame.
   - **Example**: For a limit of 100 requests per minute: 1st-100th request → allowed, 101st request within the same minute → rejected
   - **Time frame**: 20-25 minutes

2. **Throttle Function**
   - **Problem**: Write a function to implement throttling for an event handler.
   - **Example**: When throttling on scroll event with 300ms: multiple scroll events within 300ms will only trigger the handler once
   - **Time frame**: 15-20 minutes

3. **Pub-Sub Implementation**
   - **Problem**: Create a simple pub-sub (publisher-subscriber) implementation.
   - **Example**: pubSub.subscribe('event', callback); pubSub.publish('event', data); // callback gets executed with data
   - **Time frame**: 20-25 minutes

4. **Promise.all Implementation**
   - **Problem**: Implement a basic version of Promise.all().
   - **Example**: MyPromise.all([promise1, promise2, promise3]).then(results => console.log(results)); // Results is an array of resolved values
   - **Time frame**: 20-25 minutes

5. **Memoization Function**
   - **Problem**: Create a memoization function for optimizing recursive calculations.
   - **Example**: const memoizedFib = memoize(fib); memoizedFib(40); // Much faster than regular fibonacci function
   - **Time frame**: 15-20 minutes

6. **Deep Equality Comparison**
   - **Problem**: Write a function that performs deep equality comparison between two objects.
   - **Example**: Input: {a: 1, b: {c: 2}}, {a: 1, b: {c: 2}} → Output: true
   - **Time frame**: 15-20 minutes

7. **Array Flatten**
   - **Problem**: Implement a function that flattens a nested array to any depth.
   - **Example**: Input: [1, [2, [3, [4]], 5]] → Output: [1, 2, 3, 4, 5]
   - **Time frame**: 15-20 minutes

8. **Debounce Function**
   - **Problem**: Implement a debounce function that delays invoking a function until after a certain time has elapsed.
   - **Example**: When debouncing a search input with 300ms: typing "hello" quickly will only trigger the search once, 300ms after the last keystroke
   - **Time frame**: 15-20 minutes

9. **Event Emitter**
   - **Problem**: Create a basic implementation of an event emitter with on, off, and emit methods.
   - **Example**: emitter.on('event', callback); emitter.emit('event', data); // callback gets executed with data
   - **Time frame**: 20-25 minutes

10. **Currying Function**
    - **Problem**: Implement a curry function that converts a function with multiple arguments into a sequence of functions with a single argument.
    - **Example**: const add = (a, b, c) => a + b + c; const curriedAdd = curry(add); curriedAdd(1)(2)(3) // Returns 6
    - **Time frame**: 15-20 minutes

### Medium
1. **Thread-Safe Singleton**
   - **Problem**: Design and implement a thread-safe singleton pattern.
   - **Example**: Regardless of concurrent instantiation attempts, only one instance is ever created
   - **Time frame**: 20-25 minutes

2. **Producer-Consumer**
   - **Problem**: Create a solution for the producer-consumer problem using a bounded buffer.
   - **Example**: Multiple producer threads adding items to a fixed-size queue, multiple consumer threads removing items
   - **Time frame**: 25-30 minutes

3. **Async Task Queue**
   - **Problem**: Implement a task queue that processes async tasks with a configurable concurrency limit.
   - **Example**: const queue = new TaskQueue(3); queue.push(async1, async2, async3, async4); // Only 3 run at once
   - **Time frame**: 25-30 minutes

4. **State Machine**
   - **Problem**: Design a simple state machine that can transition between states and trigger events.
   - **Example**: A document workflow that transitions from Draft → Review → Published, with appropriate validation
   - **Time frame**: 25-30 minutes

5. **Observable Pattern**
   - **Problem**: Implement the Observable pattern with subscribe, unsubscribe, and notify methods.
   - **Example**: const observable = new Observable(); observable.subscribe(observer); observable.notify(data); // All observers receive data
   - **Time frame**: 20-25 minutes

6. **Dependency Injection**
   - **Problem**: Create a simple dependency injection container.
   - **Example**: container.register('database', DbService); container.register('userService', UserService, ['database']); const userService = container.resolve('userService'); // Automatically injects DbService
   - **Time frame**: 25-30 minutes

7. **Command Pattern**
   - **Problem**: Implement the Command pattern for an undo/redo functionality.
   - **Example**: An editor with operations like commandManager.execute(new InsertTextCommand('hello')); commandManager.undo();
   - **Time frame**: 25-30 minutes

8. **Middleware System**
   - **Problem**: Design a middleware system similar to Express.js middleware.
   - **Example**: app.use(authMiddleware); app.use(loggerMiddleware); app.get('/path', routeHandler);
   - **Time frame**: 20-25 minutes

9. **Cache with TTL**
   - **Problem**: Implement a caching system with time-to-live (TTL) functionality.
   - **Example**: cache.set('key', 'value', 300); // Expires after 300 seconds; cache.get('key'); // Returns 'value' if not expired
   - **Time frame**: 25-30 minutes

10. **Retry Mechanism**
    - **Problem**: Create a function that retries failed async operations with exponential backoff.
    - **Example**: retry(fetchData, { retries: 3, backoff: 300 }); // Retries 3 times with increasing delays
    - **Time frame**: 20-25 minutes

### Hard
1. **Distributed Systems Lock**
   - **Problem**: Design a distributed lock mechanism that prevents race conditions across multiple servers.
   - **Example**: Multiple server instances attempting to update the same resource; only one should succeed
   - **Time frame**: 30-35 minutes

2. **Real-time Collaboration**
   - **Problem**: Design the core logic for a real-time collaborative text editor.
   - **Example**: Multiple users editing the same document simultaneously without conflicts
   - **Time frame**: 30-35 minutes

3. **Message Broker**
   - **Problem**: Implement a simple message broker with publish/subscribe functionality and persistence.
   - **Example**: Services publishing events; other services consuming these events reliably
   - **Time frame**: 30-35 minutes

4. **Consistent Hashing**
   - **Problem**: Implement a consistent hashing algorithm for distributing data across servers.
   - **Example**: Adding or removing a server redistributes only K/N of keys, where K is the number of keys and N is the number of servers
   - **Time frame**: 30-40 minutes

5. **Rate Limiter with Token Bucket**
   - **Problem**: Implement a token bucket algorithm for rate limiting with burst capabilities.
   - **Example**: 100 tokens per minute with ability to burst up to 50 tokens
   - **Time frame**: 25-30 minutes

6. **Circuit Breaker**
   - **Problem**: Design a circuit breaker pattern for handling failures in distributed systems.
   - **Example**: After 5 failures, the circuit opens for 30 seconds, then goes to half-open state
   - **Time frame**: 25-30 minutes

7. **Saga Pattern**
   - **Problem**: Implement the Saga pattern for distributed transactions.
   - **Example**: A multi-step process like order → payment → inventory → shipping, with compensating transactions for failures
   - **Time frame**: 35-40 minutes

8. **Bloom Filter**
   - **Problem**: Implement a Bloom filter data structure for efficient set membership testing.
   - **Example**: Testing if an item might be in a very large set without storing the entire set
   - **Time frame**: 30-35 minutes

9. **Conflict-Free Replicated Data Type**
   - **Problem**: Implement a simple CRDT for text that can merge concurrent edits.
   - **Example**: Two users inserting text at different positions; merging their changes without conflicts
   - **Time frame**: 35-40 minutes

10. **Event Sourcing**
    - **Problem**: Design a simple event sourcing system for an e-commerce application.
    - **Example**: All state changes are stored as events; current state is reconstructed by replaying events
    - **Time frame**: 30-35 minutes
