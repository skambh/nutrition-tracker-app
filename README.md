# nutrition-tracker-app

# Base Requirements
1. The app should allow the user to record something they ate/drank, along with the nutritional value of that food item.
  a. For example, if the user eats an apple, they can add a log entry for an apple.
3. The nutritional value of each food item consists of a set of nutrients and the amount of each nutrient.
  a. For example, an apple consists of the following three nutritional fields and their associated values: {carbohydrates: 25g, fiber: 4g, calories: 95}
4. The app should allow the user to select target nutrients for which the the app will display the total value consumed that day.
5. The app should allow users to store recipes. A recipe consists of a set of ingredients (food items). The nutritional value of the recipe is the sum of the nutritional value of its ingredients.
6. All data should be stored locally on the user device. The data consists of 3 files: a dictionary mapping each recipe to its component food/drink items and food items to to their nutritional value, and a log record of each item consumed along with the date and time of consumption.
  a. For example, a dictionary consisting of one item, a apple, and one recipe, a pasta, might have the following structure
  {
    apple: {
      type: item,
      serving_size: 1 
      nutritional_value: {
         carbohydrates: 25g,
         fiber: 4g,
         calories: 95
       }
     },
     penne: {
       type: item,
       serving_size: 1 cup
       nutritional_value: {
         carbohydrates: 42g,
         protein: 7g
       },
     }, 
     marinara_sauce: {
       type: pasta,
       serving_size: 1/2 cup
       nutritional_value: {
         calories: 100,
         fat: 7g
       }
     },
     pasta: {
       type: recipe,
       items: {
         { item: penne,
           serving_size: 1 cup },
         { item: marinara_sauce,
           serving_size: 1/2 cup }
       }
     }
   }
8. Not every item has to have all the nutritional values filled in. They can have null values which will not count towards the summation if they're part of a recipe.
9. The user should be prompted to fill out the nutritional information for a new item/recipe at the time of recording, and should have an option to update the database.
10. The app should prompt the user for the serving size whenever they record an entry, and the app should automatically scale the nutrtitional value to be recorded based on the recorded servings consumed and the stored serving size for which nutritional information is available.

# Stretch Requirements
1. The user should be able to set targets for certain nutritional values, and the app should display the progress towards those targets each time an item or recipe is logged.
2. The app should have a search engine integration that automatically suggests nutritional values for a new recipe/item and suggest the ingredients that make up a recipe.
