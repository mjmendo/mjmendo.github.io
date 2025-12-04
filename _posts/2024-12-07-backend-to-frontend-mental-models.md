---
layout: post
title: "From Backend to Frontend: A Developer's Mental Model"
date: 2024-12-07
categories: react
---

As a seasoned backend developer transitioning to full-stack development, one of the biggest challenges is developing a mental model for frontend concepts. This post explores the parallels between backend and frontend development, focusing on React and TypeScript, through the lens of a ticket management system implementation.

## Core Concepts: Backend to Frontend Translation

### State Management
- **Backend**: Database state management
- **Frontend**: React's useState and component state
  ```typescript
  // Backend: Database record
  const ticket = await repository.findById(id);
  
  // Frontend: Component state
  const [ticket, setTicket] = useState<Ticket | null>(null);
  ```

### Event Handling
- **Backend**: Event listeners and triggers
- **Frontend**: useEffect and event handlers

Note: useEffect is a "listener" to handle **behaviour when the state of an object changes**. Remember functions are also objects in JS, so the can also change and therefore be in the dep array of the useEffect hook.


  ```typescript
  // Backend: Database trigger
  ON UPDATE tickets SET updated_at = NOW();
  
  // Frontend: Effect hook
  useEffect(() => {
    onFilterChange(activeFilters);
  }, [activeFilters, onFilterChange]);
  ```

### Data Flow
- **Backend**: Service layer communication
- **Frontend**: Component props and callbacks
  ```typescript
  // Backend: Service injection
  @Inject private ticketService: TicketService;
  
  // Frontend: Props passing
  <TicketFilter onFilterChange={(filters) => handleFilters(filters)} />
  ```

## Key Learnings from Implementation

### Component State Management
React's state management follows these principles:
1. **Single Source of Truth**: Like database normalization
   ```typescript
   const [activeFilters, setActiveFilters] = useState(new Map());
   ```

2. **Immutable Updates**: Similar to transaction isolation
   ```typescript
   // Don't modify directly
   activeFilters.set(key, value);  // Wrong
   
   // Create new instance
   setActiveFilters(new Map(prev).set(key, value));  // Correct
   ```

3. **State Propagation**: Like event propagation in message queues
   ```typescript
   useEffect(() => {
     onFilterChange(filterMap);  // Notify parent of changes
   }, [filterMap]);
   ```

### Validation and Error Handling
Frontend validation follows similar patterns to backend validation:
```typescript
// Backend validation
if (!isValid(request)) throw new ValidationError();

// Frontend validation
if (!isValidFilter(filterValue)) {
  setError('Invalid filter value');
  return;
}
```

## Practical Example: Filter Implementation

The filter implementation demonstrates several key concepts:

1. **State Management**:
   ```typescript
   const [filterMap, setFilterMap] = useState<Map<string,string[]>>(new Map());
   ```

2. **Effect Handling**:
   ```typescript
   useEffect(() => {
     onFilterChange(filterMap);
   }, [filterMap]);
   ```

3. **Component Communication**:
   ```typescript
   interface TicketFilterProps { 
     onFilterChange: (filters: Map<string,string[]>) => void;
   }
   ```

## Best Practices and Patterns

1. **Separation of Concerns**
   - Backend: Services, Repositories, Controllers
   - Frontend: Components, Hooks, Services

2. **Type Safety**
   - Backend: Database schemas, DTOs
   - Frontend: TypeScript interfaces, Props types

3. **Error Handling**
   - Backend: Try-catch blocks, Error responses
   - Frontend: State management, UI feedback

## Conclusion

The comparison between backend and frontend development becomes more intuitive when you map familiar concepts to their frontend counterparts. Understanding these parallels helps in:
- Structuring frontend applications
- Managing component state effectively
- Implementing proper data flow
- Handling side effects appropriately
