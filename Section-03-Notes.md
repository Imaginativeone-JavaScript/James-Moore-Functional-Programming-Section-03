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
  
    **How can I modify Arrays in a mutable way?**
    
    ```javascript
    // An array of meal objects
    const meals = [
      { id: 1, description: 'Breakfast', calories: 420 },
      { id: 2, description: 'Lunch', calories: 520 }
    ];
    
    // Another meal object, all by itself
    const meal = { 
      id: 3, 
      description: 'Snack', 
      calories: 100
    };
    ```
    
    **Add the meal object to a new array that contains the objects from the meal array.**
    
    ```javascript
    const updatedMeals = [...meals, meal];
    ```
    
    **What if I wanted to updated the description of the object in the meals array with the id of 2?**
    
    The **map function** array.map(transformation-function)
    
    **An Example**
    
    Say that I need to double every number in the array:
    ```javascript
    const numbers = [1, 2, 3];
    
    // How do I apply this "double" function to every item in the array?
    function double(number) {
      return number * 2;
    }
    ```
    
    The map function - to the rescue
    
    ```javascript
    const numbers = [1, 2, 3];
    
    function double(number) {
      return number * 2;
    }
    
    const doubledNumbers = numbers.map(double);
    ```
    
    Step through what happens when this code executes:
    
    The call to map will start by grabbing the first element in the numbers array, the "1", and passes it into our double function.
    
    ```javascript
    const numbers = [1, 2, 3];
    
    function double(1) { // First pass works on the first element
      return number * 2;
    } // This function functions takes the parameter, 1, multiplies it by 2, and then returns 1 * 2;
      // The map function creates a new array, and stores a 2 inside of it.
    
    const doubledNumbers = numbers.map(double);
    ```
    
  - [ ] 15. Summarize information in an array 9min
