### General  
The engine defines an interface for handling datetime objects and time intervals in tasks, commonly required in calendar development. The goal is to encapsulate all mathematical calculations within the engine while providing intuitive methods for working with time intervals.  

### Interface  

#### **Datetime Objects**  
The engine supports datetime objects as either Python datetime instances or ISO-formatted strings (with or without an assigned timezone). It can convert these datetime values to a specified timezone and provides a mapping system to align its internal timezones with a predefined timezone handbook used in development.  

#### **Time Intervals**  
The engine defines a dedicated DTO for handling time intervals. It accepts two time intervals with associated timezones and checks for overlapping occurrences. It supports various types of overlaps (e.g., head-tail overlap, full containment) and processes them accordingly.  

There are three ways to handle overlapping intervals:  
1. **Exclude both** – Removes both intervals from consideration.  
2. **Extend into one** – Merges the two intervals into a single extended interval.  
3. **Choose by parameter** – Uses additional attributes assigned to the intervals to define a custom selection logic.  

#### **Rules and Collections**  
Rules are used to define collections of time intervals. A collection is formed based on a set of rules, each describing the recurrence pattern of an interval. A collection can be built in three ways:  
- By specifying a set of rules.  
- By manually defining a set of time intervals.  
- By combining both predefined intervals and rule-based intervals into a single collection.  

Within a collection, a specific strategy for handling overlapping intervals is applied, as mentioned earlier. The engine can also merge two collections, using a customizable merging strategy to resolve overlaps.  

Additionally, the engine can generate time intervals from a collection within a given datetime range. Collections may be infinite, producing intervals dynamically as needed.  
