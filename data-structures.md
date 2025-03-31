# Data Structure Interview Problems

## Easy Problems

1. **Implement Stack**

   - Problem: Implement a stack with push, pop, and getMin operations in O(1) time

   ```typescript
   // Input:
   MinStack minStack = new MinStack();
   minStack.push(-2);
   minStack.push(0);
   minStack.push(-3);
   minStack.getMin(); // return -3
   minStack.pop();
   minStack.top();    // return 0
   minStack.getMin(); // return -2

   // Implementation
   class MinStack {
       private stack: number[];
       private minStack: number[];

       constructor() {
           this.stack = [];
           this.minStack = [];
       }

       push(val: number): void {
           this.stack.push(val);
           if (this.minStack.length === 0 || val <= this.minStack[this.minStack.length - 1]) {
               this.minStack.push(val);
           }
       }

       pop(): void {
           if (this.stack.pop() === this.minStack[this.minStack.length - 1]) {
               this.minStack.pop();
           }
       }

       top(): number {
           return this.stack[this.stack.length - 1];
       }

       getMin(): number {
           return this.minStack[this.minStack.length - 1];
       }
   }
   ```

2. **Implement Queue using Stacks**

   - Problem: Implement a queue using only two stacks

   ```typescript
   // Input:
   MyQueue queue = new MyQueue();
   queue.push(1);
   queue.push(2);
   queue.peek();  // returns 1
   queue.pop();   // returns 1
   queue.empty(); // returns false

   // Implementation
   class MyQueue {
       private stack1: number[];
       private stack2: number[];

       constructor() {
           this.stack1 = [];
           this.stack2 = [];
       }

       push(x: number): void {
           this.stack1.push(x);
       }

       pop(): number {
           if (this.stack2.length === 0) {
               while (this.stack1.length > 0) {
                   this.stack2.push(this.stack1.pop()!);
               }
           }
           return this.stack2.pop()!;
       }

       peek(): number {
           if (this.stack2.length === 0) {
               while (this.stack1.length > 0) {
                   this.stack2.push(this.stack1.pop()!);
               }
           }
           return this.stack2[this.stack2.length - 1];
       }

       empty(): boolean {
           return this.stack1.length === 0 && this.stack2.length === 0;
       }
   }
   ```

3. **Implement Linked List**

   - Problem: Implement a singly linked list with basic operations

   ```typescript
   // Operations: append, prepend, delete, find
   class ListNode {
     val: number;
     next: ListNode | null;

     constructor(val?: number) {
       this.val = val ?? 0;
       this.next = null;
     }
   }

   class LinkedList {
     head: ListNode | null;

     constructor() {
       this.head = null;
     }

     append(val: number): void {
       const newNode = new ListNode(val);
       if (!this.head) {
         this.head = newNode;
         return;
       }
       let current = this.head;
       while (current.next) {
         current = current.next;
       }
       current.next = newNode;
     }

     prepend(val: number): void {
       const newNode = new ListNode(val);
       newNode.next = this.head;
       this.head = newNode;
     }

     delete(val: number): void {
       if (!this.head) return;
       if (this.head.val === val) {
         this.head = this.head.next;
         return;
       }
       let current = this.head;
       while (current.next) {
         if (current.next.val === val) {
           current.next = current.next.next;
           return;
         }
         current = current.next;
       }
     }

     find(val: number): ListNode | null {
       let current = this.head;
       while (current) {
         if (current.val === val) return current;
         current = current.next;
       }
       return null;
     }
   }
   ```

4. **Binary Search Tree Operations**

   - Problem: Implement basic BST operations

   ```typescript
   class TreeNode {
     val: number;
     left: TreeNode | null;
     right: TreeNode | null;

     constructor(val?: number) {
       this.val = val ?? 0;
       this.left = null;
       this.right = null;
     }
   }

   class BST {
     root: TreeNode | null;

     constructor() {
       this.root = null;
     }

     insert(val: number): void {
       const newNode = new TreeNode(val);
       if (!this.root) {
         this.root = newNode;
         return;
       }
       this.insertNode(this.root, newNode);
     }

     private insertNode(node: TreeNode, newNode: TreeNode): void {
       if (newNode.val < node.val) {
         if (!node.left) {
           node.left = newNode;
         } else {
           this.insertNode(node.left, newNode);
         }
       } else {
         if (!node.right) {
           node.right = newNode;
         } else {
           this.insertNode(node.right, newNode);
         }
       }
     }

     search(val: number): TreeNode | null {
       return this.searchNode(this.root, val);
     }

     private searchNode(node: TreeNode | null, val: number): TreeNode | null {
       if (!node || node.val === val) return node;
       return val < node.val ? this.searchNode(node.left, val) : this.searchNode(node.right, val);
     }
   }
   ```

5. **Hash Set Implementation**

   - Problem: Implement a HashSet without using built-in hash set libraries

   ```typescript
   class MyHashSet {
     private set: boolean[];

     constructor() {
       this.set = [];
     }

     add(key: number): void {
       this.set[key] = true;
     }

     remove(key: number): void {
       this.set[key] = false;
     }

     contains(key: number): boolean {
       return !!this.set[key];
     }
   }
   ```

6. **Implement Circular Queue**

   - Problem: Design your implementation of the circular queue

   ```typescript
   class MyCircularQueue {
     private queue: number[];
     private head: number;
     private tail: number;
     private size: number;

     constructor(k: number) {
       this.queue = new Array(k);
       this.head = -1;
       this.tail = -1;
       this.size = k;
     }

     enQueue(value: number): boolean {
       if (this.isFull()) return false;
       if (this.isEmpty()) this.head = 0;
       this.tail = (this.tail + 1) % this.size;
       this.queue[this.tail] = value;
       return true;
     }

     deQueue(): boolean {
       if (this.isEmpty()) return false;
       if (this.head === this.tail) {
         this.head = -1;
         this.tail = -1;
         return true;
       }
       this.head = (this.head + 1) % this.size;
       return true;
     }

     Front(): number {
       return this.isEmpty() ? -1 : this.queue[this.head];
     }

     Rear(): number {
       return this.isEmpty() ? -1 : this.queue[this.tail];
     }

     isEmpty(): boolean {
       return this.head === -1;
     }

     isFull(): boolean {
       return (this.tail + 1) % this.size === this.head;
     }
   }
   ```

7. **Priority Queue Implementation**

   - Problem: Implement a basic priority queue

   ```typescript
   class PriorityQueue {
     private heap: number[];

     constructor() {
       this.heap = [];
     }

     enqueue(val: number): void {
       this.heap.push(val);
       this.bubbleUp();
     }

     dequeue(): number | undefined {
       if (this.heap.length === 0) return undefined;
       if (this.heap.length === 1) return this.heap.pop();

       const result = this.heap[0];
       this.heap[0] = this.heap.pop()!;
       this.bubbleDown();
       return result;
     }

     private bubbleUp(): void {
       let index = this.heap.length - 1;
       while (index > 0) {
         const parentIndex = Math.floor((index - 1) / 2);
         if (this.heap[parentIndex] <= this.heap[index]) break;
         [this.heap[parentIndex], this.heap[index]] = [this.heap[index], this.heap[parentIndex]];
         index = parentIndex;
       }
     }

     private bubbleDown(): void {
       let index = 0;
       while (true) {
         let smallest = index;
         const leftChild = 2 * index + 1;
         const rightChild = 2 * index + 2;

         if (leftChild < this.heap.length && this.heap[leftChild] < this.heap[smallest]) {
           smallest = leftChild;
         }
         if (rightChild < this.heap.length && this.heap[rightChild] < this.heap[smallest]) {
           smallest = rightChild;
         }

         if (smallest === index) break;

         [this.heap[index], this.heap[smallest]] = [this.heap[smallest], this.heap[index]];
         index = smallest;
       }
     }
   }
   ```

8. **Trie Implementation**

   - Problem: Implement a trie with insert, search, and startsWith methods

   ```typescript
   class TrieNode {
     children: Map<string, TrieNode>;
     isEndOfWord: boolean;

     constructor() {
       this.children = new Map();
       this.isEndOfWord = false;
     }
   }

   class Trie {
     root: TrieNode;

     constructor() {
       this.root = new TrieNode();
     }

     insert(word: string): void {
       let current = this.root;
       for (const char of word) {
         if (!current.children.has(char)) {
           current.children.set(char, new TrieNode());
         }
         current = current.children.get(char)!;
       }
       current.isEndOfWord = true;
     }

     search(word: string): boolean {
       const node = this.searchNode(word);
       return node !== null && node.isEndOfWord;
     }

     startsWith(prefix: string): boolean {
       return this.searchNode(prefix) !== null;
     }

     private searchNode(str: string): TrieNode | null {
       let current = this.root;
       for (const char of str) {
         if (!current.children.has(char)) {
           return null;
         }
         current = current.children.get(char)!;
       }
       return current;
     }
   }
   ```

9. **Graph Implementation**

   - Problem: Implement a basic graph using adjacency list

   ```typescript
   class Graph {
     private vertices: Map<number, number[]>;

     constructor() {
       this.vertices = new Map();
     }

     addVertex(vertex: number): void {
       if (!this.vertices.has(vertex)) {
         this.vertices.set(vertex, []);
       }
     }

     addEdge(vertex1: number, vertex2: number): void {
       if (!this.vertices.has(vertex1)) this.addVertex(vertex1);
       if (!this.vertices.has(vertex2)) this.addVertex(vertex2);

       this.vertices.get(vertex1)!.push(vertex2);
       this.vertices.get(vertex2)!.push(vertex1);
     }

     getNeighbors(vertex: number): number[] {
       return this.vertices.get(vertex) || [];
     }

     bfs(startVertex: number): number[] {
       const visited = new Set<number>();
       const result: number[] = [];
       const queue: number[] = [startVertex];

       visited.add(startVertex);

       while (queue.length > 0) {
         const vertex = queue.shift()!;
         result.push(vertex);

         for (const neighbor of this.getNeighbors(vertex)) {
           if (!visited.has(neighbor)) {
             visited.add(neighbor);
             queue.push(neighbor);
           }
         }
       }

       return result;
     }
   }
   ```

10. **Heap Implementation**

    - Problem: Implement a min heap

    ```typescript
    class MinHeap {
      private heap: number[];

      constructor() {
        this.heap = [];
      }

      insert(val: number): void {
        this.heap.push(val);
        this.bubbleUp();
      }

      extractMin(): number | undefined {
        if (this.heap.length === 0) return undefined;
        if (this.heap.length === 1) return this.heap.pop();

        const min = this.heap[0];
        this.heap[0] = this.heap.pop()!;
        this.bubbleDown();
        return min;
      }

      private bubbleUp(): void {
        let index = this.heap.length - 1;
        while (index > 0) {
          const parentIndex = Math.floor((index - 1) / 2);
          if (this.heap[parentIndex] <= this.heap[index]) break;
          [this.heap[parentIndex], this.heap[index]] = [this.heap[index], this.heap[parentIndex]];
          index = parentIndex;
        }
      }

      private bubbleDown(): void {
        let index = 0;
        while (true) {
          let smallest = index;
          const leftChild = 2 * index + 1;
          const rightChild = 2 * index + 2;

          if (leftChild < this.heap.length && this.heap[leftChild] < this.heap[smallest]) {
            smallest = leftChild;
          }
          if (rightChild < this.heap.length && this.heap[rightChild] < this.heap[smallest]) {
            smallest = rightChild;
          }

          if (smallest === index) break;

          [this.heap[index], this.heap[smallest]] = [this.heap[smallest], this.heap[index]];
          index = smallest;
        }
      }
    }
    ```

## Medium Problems

11. **LRU Cache Implementation**

    - Problem: Implement a Least Recently Used (LRU) cache

    ```typescript
    class LRUCache {
      private cache: Map<number, number>;
      private capacity: number;

      constructor(capacity: number) {
        this.cache = new Map();
        this.capacity = capacity;
      }

      get(key: number): number {
        if (!this.cache.has(key)) return -1;

        const value = this.cache.get(key)!;
        this.cache.delete(key);
        this.cache.set(key, value);
        return value;
      }

      put(key: number, value: number): void {
        if (this.cache.has(key)) {
          this.cache.delete(key);
        } else if (this.cache.size >= this.capacity) {
          const firstKey = this.cache.keys().next().value;
          this.cache.delete(firstKey);
        }
        this.cache.set(key, value);
      }
    }
    ```

12. **AVL Tree Implementation**

    - Problem: Implement a self-balancing AVL tree

    ```typescript
    class AVLNode {
      value: number;
      left: AVLNode | null;
      right: AVLNode | null;
      height: number;

      constructor(value: number) {
        this.value = value;
        this.left = null;
        this.right = null;
        this.height = 1;
      }
    }

    class AVLTree {
      root: AVLNode | null;

      constructor() {
        this.root = null;
      }

      private getHeight(node: AVLNode | null): number {
        return node ? node.height : 0;
      }

      private getBalance(node: AVLNode | null): number {
        return node ? this.getHeight(node.left) - this.getHeight(node.right) : 0;
      }

      private rightRotate(y: AVLNode): AVLNode {
        const x = y.left!;
        const T2 = x.right;

        x.right = y;
        y.left = T2;

        y.height = Math.max(this.getHeight(y.left), this.getHeight(y.right)) + 1;
        x.height = Math.max(this.getHeight(x.left), this.getHeight(x.right)) + 1;

        return x;
      }

      private leftRotate(x: AVLNode): AVLNode {
        const y = x.right!;
        const T2 = y.left;

        y.left = x;
        x.right = T2;

        x.height = Math.max(this.getHeight(x.left), this.getHeight(x.right)) + 1;
        y.height = Math.max(this.getHeight(y.left), this.getHeight(y.right)) + 1;

        return y;
      }

      insert(value: number): void {
        this.root = this.insertNode(this.root, value);
      }

      private insertNode(node: AVLNode | null, value: number): AVLNode {
        if (!node) return new AVLNode(value);

        if (value < node.value) node.left = this.insertNode(node.left, value);
        else if (value > node.value) node.right = this.insertNode(node.right, value);
        else return node;

        node.height = Math.max(this.getHeight(node.left), this.getHeight(node.right)) + 1;

        const balance = this.getBalance(node);

        // Left Left Case
        if (balance > 1 && value < node.left!.value) return this.rightRotate(node);

        // Right Right Case
        if (balance < -1 && value > node.right!.value) return this.leftRotate(node);

        // Left Right Case
        if (balance > 1 && value > node.left!.value) {
          node.left = this.leftRotate(node.left!);
          return this.rightRotate(node);
        }

        // Right Left Case
        if (balance < -1 && value < node.right!.value) {
          node.right = this.rightRotate(node.right!);
          return this.leftRotate(node);
        }

        return node;
      }
    }
    ```

13. **Disjoint Set (Union Find)**

    - Problem: Implement a disjoint set data structure

    ```typescript
    class DisjointSet {
      private parent: number[];
      private rank: number[];

      constructor(size: number) {
        this.parent = Array.from({ length: size }, (_, i) => i);
        this.rank = new Array(size).fill(0);
      }

      find(x: number): number {
        if (this.parent[x] !== x) {
          this.parent[x] = this.find(this.parent[x]); // Path compression
        }
        return this.parent[x];
      }

      union(x: number, y: number): void {
        const rootX = this.find(x);
        const rootY = this.find(y);

        if (rootX !== rootY) {
          if (this.rank[rootX] < this.rank[rootY]) {
            this.parent[rootX] = rootY;
          } else if (this.rank[rootX] > this.rank[rootY]) {
            this.parent[rootY] = rootX;
          } else {
            this.parent[rootY] = rootX;
            this.rank[rootX]++;
          }
        }
      }

      connected(x: number, y: number): boolean {
        return this.find(x) === this.find(y);
      }
    }
    ```

14. **Segment Tree**

    - Problem: Implement a segment tree for range queries

    ```typescript
    class SegmentTree {
      private tree: number[];
      private n: number;

      constructor(arr: number[]) {
        this.n = arr.length;
        this.tree = new Array(4 * this.n).fill(0);
        this.buildTree(arr, 0, 0, this.n - 1);
      }

      private buildTree(arr: number[], node: number, start: number, end: number): void {
        if (start === end) {
          this.tree[node] = arr[start];
          return;
        }

        const mid = Math.floor((start + end) / 2);
        this.buildTree(arr, 2 * node + 1, start, mid);
        this.buildTree(arr, 2 * node + 2, mid + 1, end);
        this.tree[node] = this.tree[2 * node + 1] + this.tree[2 * node + 2];
      }

      rangeSum(left: number, right: number): number {
        return this.rangeSumUtil(0, 0, this.n - 1, left, right);
      }

      private rangeSumUtil(node: number, start: number, end: number, left: number, right: number): number {
        if (left > end || right < start) return 0;
        if (left <= start && right >= end) return this.tree[node];

        const mid = Math.floor((start + end) / 2);
        return (
          this.rangeSumUtil(2 * node + 1, start, mid, left, right) +
          this.rangeSumUtil(2 * node + 2, mid + 1, end, left, right)
        );
      }

      update(index: number, value: number): void {
        this.updateUtil(0, 0, this.n - 1, index, value);
      }

      private updateUtil(node: number, start: number, end: number, index: number, value: number): void {
        if (start === end) {
          this.tree[node] = value;
          return;
        }

        const mid = Math.floor((start + end) / 2);
        if (index <= mid) {
          this.updateUtil(2 * node + 1, start, mid, index, value);
        } else {
          this.updateUtil(2 * node + 2, mid + 1, end, index, value);
        }
        this.tree[node] = this.tree[2 * node + 1] + this.tree[2 * node + 2];
      }
    }
    ```

15. **Binary Indexed Tree (Fenwick Tree)**
    - Problem: Implement a Binary Indexed Tree for range sum queries
    ```typescript
    class FenwickTree {
      private tree: number[];

      constructor(n: number) {
        this.tree = new Array(n + 1).fill(0);
      }

      update(index: number, delta: number): void {
        index++;
        while (index < this.tree.length) {
          this.tree[index] += delta;
          index += index & -index;
        }
      }

      prefixSum(index: number): number {
        index++;
        let sum = 0;
        while (index > 0) {
          sum += this.tree[index];
          index -= index & -index;
        }
        return sum;
      }

      rangeSum(left: number, right: number): number {
        return this.prefixSum(right) - this.prefixSum(left - 1);
      }
    }
    ```

## Hard Problems

16. **Red-Black Tree**

    - Problem: Implement a Red-Black tree with insertion and deletion

    ```typescript
    enum Color {
      RED,
      BLACK,
    }

    class RBNode {
      value: number;
      color: Color;
      left: RBNode | null;
      right: RBNode | null;
      parent: RBNode | null;

      constructor(value: number) {
        this.value = value;
        this.color = Color.RED;
        this.left = null;
        this.right = null;
        this.parent = null;
      }
    }

    class RedBlackTree {
      private root: RBNode | null;
      private NIL: RBNode;

      constructor() {
        this.NIL = new RBNode(0);
        this.NIL.color = Color.BLACK;
        this.root = this.NIL;
      }

      private leftRotate(x: RBNode): void {
        const y = x.right!;
        x.right = y.left;

        if (y.left !== this.NIL) {
          y.left.parent = x;
        }

        y.parent = x.parent;

        if (x.parent === null) {
          this.root = y;
        } else if (x === x.parent.left) {
          x.parent.left = y;
        } else {
          x.parent.right = y;
        }

        y.left = x;
        x.parent = y;
      }

      // Additional methods for right rotation, insertion, deletion, and fixing violations
      // would be implemented here
    }
    ```

17. **B-Tree**

    - Problem: Implement a B-tree with insertion and search

    ```typescript
    class BTreeNode {
      keys: number[];
      children: BTreeNode[];
      leaf: boolean;
      n: number;
      t: number;

      constructor(t: number, leaf: boolean) {
        this.t = t;
        this.leaf = leaf;
        this.keys = [];
        this.children = [];
        this.n = 0;
      }
    }

    class BTree {
      private root: BTreeNode | null;
      private t: number;

      constructor(t: number) {
        this.root = null;
        this.t = t;
      }

      // Implementation details for insertion, deletion, and search would go here
    }
    ```

18. **Skip List**

    - Problem: Implement a Skip List with insertion and search

    ```typescript
    class SkipListNode {
      value: number;
      next: SkipListNode[];

      constructor(value: number, level: number) {
        this.value = value;
        this.next = new Array(level).fill(null);
      }
    }

    class SkipList {
      private head: SkipListNode;
      private maxLevel: number;
      private level: number;

      constructor(maxLevel: number) {
        this.maxLevel = maxLevel;
        this.level = 0;
        this.head = new SkipListNode(-Infinity, maxLevel);
      }

      // Implementation details for insert, search, and delete would go here
    }
    ```

19. **Fibonacci Heap**

    - Problem: Implement a Fibonacci Heap

    ```typescript
    class FibNode {
      key: number;
      degree: number;
      parent: FibNode | null;
      child: FibNode | null;
      left: FibNode;
      right: FibNode;
      mark: boolean;

      constructor(key: number) {
        this.key = key;
        this.degree = 0;
        this.parent = null;
        this.child = null;
        this.left = this;
        this.right = this;
        this.mark = false;
      }
    }

    class FibonacciHeap {
      private min: FibNode | null;
      private size: number;

      constructor() {
        this.min = null;
        this.size = 0;
      }

      // Implementation details for insert, extractMin, decreaseKey, and delete would go here
    }
    ```

20. **Persistent Data Structures**

    - Problem: Implement a Persistent Binary Search Tree

    ```typescript
    class PersistentNode {
      value: number;
      left: PersistentNode | null;
      right: PersistentNode | null;
      version: number;

      constructor(value: number, version: number) {
        this.value = value;
        this.left = null;
        this.right = null;
        this.version = version;
      }
    }

    class PersistentBST {
      private roots: PersistentNode[];
      private currentVersion: number;

      constructor() {
        this.roots = [];
        this.currentVersion = -1;
      }

      // Implementation details for version control and tree operations would go here
    }
    ```

Each implementation includes:

- Clear class structure
- Essential methods and properties
- Type definitions
- Basic operations
- Comments for complex operations

The problems are organized by difficulty:

- Easy: Basic data structure implementations
- Medium: More complex data structures with advanced operations
- Hard: Advanced data structures with complex operations and optimizations

Time and space complexity analysis should be considered for each operation in these implementations.
