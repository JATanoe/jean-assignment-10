# Meal Planner API Client

A Spring Boot application that serves as a client for the Spoonacular API's meal planning service. This application provides RESTful endpoints to fetch meal plans for a day or a week, with options to specify calorie targets, diet preferences, and food exclusions.

## Technologies Used

- Java 11+
- Spring Boot
- Spring Web
- RestTemplate for API communication
- Jackson for JSON processing

## API Endpoints

### Get Weekly Meal Plan

```
GET /mealplanner/week
```

**Query Parameters:**
- `numCalories` (optional): Target number of calories per day
- `diet` (optional): Diet preference (e.g., vegetarian, vegan, paleo)
- `exclusions` (optional): Comma-separated list of ingredients to exclude

**Response:**
A weekly meal plan with meals for each day of the week, including nutritional information.

### Get Daily Meal Plan

```
GET /mealplanner/day
```

**Query Parameters:**
- `numCalories` (optional): Target number of calories per day
- `diet` (optional): Diet preference (e.g., vegetarian, vegan, paleo)
- `exclusions` (optional): Comma-separated list of ingredients to exclude

**Response:**
A daily meal plan with a list of meals and nutritional information.

## Setup and Installation

1. Clone the repository
2. Configure your Spoonacular API key in `application.properties`:
   ```
   spoonacular.apiKey=your-api-key
   ```
3. Build the project using Maven:
   ```
   ./mvnw clean install
   ```
4. Run the application:
   ```
   ./mvnw spring-boot:run
   ```

## Usage Examples

### Request a Weekly Meal Plan

```
GET /mealplanner/week?numCalories=2000&diet=vegetarian&exclusions=shellfish,olives
```

### Request a Daily Meal Plan

```
GET /mealplanner/day?numCalories=1500&diet=paleo
```

## Response Structure

### Weekly Meal Plan

The weekly meal plan response includes:
- A map of days (Monday, Tuesday, etc.) to daily meal plans
- Each daily meal plan includes:
  - A list of meals (breakfast, lunch, dinner)
  - Nutritional information (calories, carbohydrates, fat, protein)

### Daily Meal Plan

The daily meal plan response includes:
- A list of meals (breakfast, lunch, dinner)
- Nutritional information (calories, carbohydrates, fat, protein)

### Meal Information

Each meal includes:
- ID
- Title
- Preparation time
- Number of servings
- Source URL for the recipe
- Image type

## Note

This application requires a valid Spoonacular API key to function. You can obtain one by signing up at [Spoonacular API](https://spoonacular.com/food-api).