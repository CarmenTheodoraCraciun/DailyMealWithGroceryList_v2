# Daily Meal with Grocery List

## Project Description
DailyMealWithGroceryList is an automation project designed to streamline meal planning and grocery list generation. It automates the process of fetching recipe data, checking for updates, and assisting users in planning meals based on available ingredients, ultimately generating a personalized list of recipes and their ingredients.

## Workflows and Features
This project consists of three main automation workflows:

### 1. Main.xaml
**Purpose:** Orchestrates the overall process.

**Functionality:**
- Checks for the existence of `recepies.json`.
- Verifies if `recepies.json` has been updated within the last **14 days**.
- If `recepies.json` is missing or outdated, it prompts the user to update it by invoking the **GroceryList.xaml** workflow.
- In all cases (whether `recepies.json` was updated or not), it proceeds to invoke the **MealPlanner.xaml** workflow.

### 2. GroceryList.xaml
**Purpose:** Extracts recipe information from a specific website.

**Functionality:**
- Navigates to [bucataria.lidl.ro/toate-retetele](https://bucataria.lidl.ro/toate-retetele).
- Extracts the following details for each recipe:
    - **Recipe Name**
    - **Recipe Link (URL)**
    - **Time to Make**
    - **Ingredients**
- Saves the extracted data into `recepies.json`.

### 3. MealPlanner.xaml
**Purpose:** Helps users plan meals based on ingredients they possess or prefer.

**Functionality:**
- Asks the user to provide a list of ingredients they have or like.
- Compares the user's ingredients with the recipes stored in `recepies.json`.
- Generates an **HTML file (`meal_plan.html`)** containing a list of recipes that include one or more of the specified ingredients.

Within the HTML file, users can:
- Select their favorite recipe ideas.
- Export a consolidated list of ingredients for the selected recipes.
- Click on links to go directly to the original recipe pages on [bucataria.lidl.ro](https://bucataria.lidl.ro).

## Technologies Used
This project is built using automation software, likely:
- **UiPath Studio** – For developing and executing the `.xaml` workflows.
- **Web Automation/Scraping Libraries** – Utilized within UiPath to interact with web pages and extract data.
- **JSON** – For storing and managing recipe data (`recepies.json`).
- **HTML** – For generating the user-friendly output of the meal planner.

## Setup and Installation
To get this automation project running, you will need **UiPath Studio** installed.

### Clone the repository:
```sh
git clone https://github.com/CarmenTheodoraCraciun/DailyMealWithGroceryList_v2.git
```

## Navigate to the project directory:
```sh
cd DailyMealWithGroceryList_v2
```

## Open the project in UiPath Studio:
1. Open UiPath Studio.
2. Click on "Open Project" and navigate to the DailyMealWithGroceryList_v2 folder.
3. Select the project.json file to open the project.

## Usage
Run the ```Main.xaml``` workflow:
1. In UiPath Studio, ensure Main.xaml is set as the main workflow.
2. Click the "Run" button (or use the appropriate shortcut) to start the automation.

## Follow the prompts:
* If ```recepies.json``` needs updating, the automation will prompt you to run the ```GroceryList.xaml``` part.
* The ```MealPlanner.xaml``` will then guide you to input your ingredients.

## Review the output:
* An HTML file ```showRecepies.html``` will be generated with your personalized meal plan.
* Open this file in your web browser to view and interact with it.

* ![image](https://github.com/user-attachments/assets/9f929024-99a8-4520-8c75-e8c8885e455b)

