# Object Interview Problems

## Easy Problems

1. **Object Property Access**
   - Write a function to safely access nested object properties.
   - Example: Input: { a: { b: { c: 1 } } }, "a.b.c"
   - Output: 1

2. **Merge Objects**
   - Merge two objects without modifying the originals.
   - Example: Input: { a: 1 }, { b: 2 }
   - Output: { a: 1, b: 2 }

3. **Count Properties**
   - Count the number of properties in an object.
   - Example: Input: { name: "John", age: 30, city: "New York" }
   - Output: 3

4. **Check Property Existence**
   - Check if a property exists in an object without accessing it.
   - Example: Input: { name: "John" }, "age"
   - Output: false

5. **Object to Array**
   - Convert an object to an array of key-value pairs.
   - Example: Input: { a: 1, b: 2 }
   - Output: [["a", 1], ["b", 2]]

6. **Filter Object Properties**
   - Create a new object with selected properties.
   - Example: Input: { a: 1, b: 2, c: 3 }, ["a", "c"]
   - Output: { a: 1, c: 3 }

7. **Compare Objects**
   - Check if two objects have the same properties and values.
   - Example: Input: { a: 1 }, { a: 1 }
   - Output: true

8. **Remove Property**
   - Remove a specific property from an object.
   - Example: Input: { name: "John", age: 30 }, "age"
   - Output: { name: "John" }

9. **Default Values**
   - Create an object with default values for missing properties.
   - Example: Input: { name: "John" }, { age: 25 }
   - Output: { name: "John", age: 25 }

10. **Property Value Types**
    - Check types of all properties in an object.
    - Example: Input: { name: "John", age: 30, active: true }
    - Output: { name: "string", age: "number", active: "boolean" }

## Medium Problems

1. **Deep Clone**
   - Create a deep clone of an object with nested properties.
   - Example: Input: { a: { b: { c: 1 } } }
   - Output: New object with same structure

2. **Object Transformation**
   - Transform object values based on a mapping function.
   - Example: Input: { a: 1, b: 2 }, (x) => x * 2
   - Output: { a: 2, b: 4 }

3. **Object Flattening**
   - Flatten a nested object structure.
   - Example: Input: { a: { b: { c: 1 } } }
   - Output: { "a.b.c": 1 }

4. **Object Diff**
   - Find differences between two objects.
   - Example: Input: { a: 1, b: 2 }, { a: 1, b: 3 }
   - Output: { b: [2, 3] }

5. **Object Serialization**
   - Implement custom object serialization/deserialization.
   - Example: Handle circular references and special types

6. **Object Validation**
   - Validate object against a schema.
   - Example: Check types, required fields, and value constraints

7. **Object Proxy**
   - Implement a proxy to intercept object operations.
   - Example: Track property access and modifications

8. **Object Inheritance**
   - Implement prototype-based inheritance.
   - Example: Create child objects with inherited properties

9. **Observable Object**
   - Create an object that notifies on property changes.
   - Example: Implement publisher-subscriber pattern

10. **Method Chaining**
    - Implement method chaining for object operations.
    - Example: obj.set("name", "John").increment("age").toggle("active")

## Hard Problems

1. **Object Time Travel**
   - Implement undo/redo functionality for object mutations.
   - Example: Track and reverse object changes

2. **Object Query Language**
   - Implement a query language for filtering objects.
   - Example: Query nested objects with complex conditions

3. **Object Schema Evolution**
   - Handle schema changes while maintaining data consistency.
   - Example: Migrate object structure without data loss

4. **Bi-directional Object Binding**
   - Implement two-way data binding between objects.
   - Example: Sync changes between multiple object instances

5. **Object State Machine**
   - Implement state management with transitions and validation.
   - Example: Define valid state transitions and handlers

6. **Object Persistence**
   - Implement efficient object storage and retrieval.
   - Example: Handle large object graphs with lazy loading

7. **Object Composition**
   - Implement complex object composition with dependency resolution.
   - Example: Manage object lifecycle and dependencies

8. **Object Versioning**
   - Implement versioning system for object changes.
   - Example: Track and manage multiple versions of objects

9. **Object Conflict Resolution**
   - Resolve conflicts in concurrent object modifications.
   - Example: Implement merge strategies for conflicting changes

10. **Object Performance Optimization**
    - Optimize object operations for large-scale applications.
    - Example: Implement efficient memory management and caching