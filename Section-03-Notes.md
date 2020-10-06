# Section 3: Immutable Data Structures 0/4 | 30min

  - [ ] 12. Immutable Data 4min
    - Simple(r)
    - Less Complicated Code
    - Don't confuse simple with easy
    - const keyword
      - PI
  - [ ] 13. Updating objects, in an immutable way 8min
    - State changes
      - Things your program remembers/tracks
    - Maintaining state
    - Data gets changed; State; immutable data?
    - How do I make changes to records in an immutable way?
    
    ```javascript
    const meal = {
      id: 1,
      description: 'Breakfast'
      // There's no corresponding Calorie Count
    }
    ```
    
    How can I add a Calorie Count to this meal record without mutating it?
    
    One of the simplest approaches is to make a new meal, copy the properties from the original meal, and then adding/updating the properties that need changes.
    
    For example,
    
    ```javascript
    const updatedMeal = {
      id: meal.id,
      description: meal.description,
      calories: 600
    }
    
    console.log(meal, udpatedMeal);
    ```
    
    ## The Spread Operator

    ### Adding a Property

    ```javascript
    const updatedMeal = {
      ...meal,
      calories: 600
    }
    
    console.log(meal, udpatedMeal);
    ```

    ### Updating a property
    
    #### takes precedence over the original description

    ```javascript
    const updatedMeal = {
      id: meal.id,
      description: "Brunch",
      calories: 600
    }
    
    console.log(meal, udpatedMeal);
    ```

    ### Deleting a Property
    
    #### Destructuring + The Rest Syntax
    
    ##### Destructuring
    
    **Instead of this:**
    ```javascript
    const description = updatedMeal.description;
    const calories = updatedMeal.calories;
    
    console.log(description, calories);
    ```
    
    **I can do this:**
    ```javascript
    const (description, calories) = updatedMeal;
    
    console.log(description, calories);
    ```
    
    **Removing the Property**
    ```javascript
    const (id, ...mealWithoutId) = updatedMeal;
    
    // This pulls "id" out into its own constant
    // The rest of the updatedMeal properties are collected into the mealWithoutId constant
    
    console.log(mealWithoutId);
    ```
    
  - [ ] 14. Updating arrays, in an immutable way 10min
  - [ ] 15. Summarize information in an array 9min
