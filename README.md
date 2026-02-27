<h1>FIND YOUR RECIPE 🍽️🍽️</h1>

### OVERVIEW 🔎:

This program will suggest you the recipe that you have the ingredients for.
<br>You can give up to 5 ingredients to the program, and it'll deliver the recipies for you
## 🔧 My Contribution

**⚠️ IMPORTANT:** **I (Aleynaonrr)** and my teammate **Enes** (https://github.com/enessaduman) developed the **Web Scrapping** for this project.

**Other project components were developed by my team members.**

## 🤝 Team Members

This is a **collaborative project** developed by:
- **Aleynaonrr** -  Project Contributor
- **zeyneptuana22** - Project Contributor (https://github.com/zeyneptuana22)
- **zehraa2005** - Project Contributor (https://github.com/zehraa2005)
- **enessaduman** - Project Contributor (https://github.com/enessaduman)
- **busracode** - Project Contributor (https://github.com/busracode)

---

<h2>Requirements 🔧⚙️</h2>

### 1️⃣ Docker Engine 🐜: 

You have to download the docker engine to let the database work since it is based on falkorDB and using a docker container<br>

Here is the [download link](https://docs.docker.com/get-started/get-docker/ "Docker Engine Download Page"). You can scroll down and download the one that works on your OS.
<br> After downloading the engine, complete the installation and restart your PC.<br>
Finally just run the Docker Desktop, skip the registration part and let the engine start.
### 2️⃣ Libraries 📚: 

We need a bunch of libraries to run the program. You can use your IDE's terminal:
Library installation command line packet:
```commandline
python -m pip install falkordb
python -m pip install scrapy
python -m pip install docker
python -m pip install nltk 
```
This will install all the libraries that we need

### 3️⃣ Creating The Container 🗃️📦:
Since our database run on a docker container, we need to create one. To create and run the container on the same line,
<br>Please use this command line to start your container:
```commandline
docker run -d --name falkor_local_db -p 6379:6379 falkordb/falkordb
```
If there is no image called "falkordb", docker run would download it by on its own. (IT MIGHT TAKE QUITE LONG TIME!)<br>
Also, you after starting the container, you can check it by using this command line if it is started or not.
````commandline
docker ps
````
## Running the Program! 🖥️➡️🍕
Now we have 2 other scripts to create the proper environment for the find_recipe.py script.
### 1️⃣ WEB SCRAPING:
Here we collect the data by scraping the website called THEMEALDB. You can check this website [here](https://www.themealdb.com/ "TheMealDb site").<br>
Run the script with this command line:
````commandline
python scrap_web.py
````
### 2️⃣ FILL THE DATABASE:
Here script receives the data from web and creates a graph database out of it.<br>
⚠️🚨 Make sure that your docker engine and container are started! 🚨⚠️<br>
Run the script with this command line:
````commandline
python database_filler.py
````
## LET'S FIND YOUR RECIPE 🥗🍔🍱
After all of these preparations, now our program is ready to run. This main script will suggest you recipes.<br>
You'll give it the ingredients you want or you have, and it'll list every recipe for your desire.<br>
If you love the recipe, it is going to deliver you a text file that has the recipe details.
It supports up to 5 ingredients to search through recipies.<br>
Here is the command line:
````commandline
python find_recipe.py ingerdient_1 ... ingredient_5
````
If you enter too general ingredients such as "milk" or "flour" it will list you alternatives.
<br> Here is an example:
````commandline
python find_recipe.py milk
````
The Output (Symbolic, it does not guarantee the exact output as context):<br>
````
🔍 Checking ingredients in the database...
     Scanning for matches or suggestions for 'milk'...

   🛑 Ambiguity detected for 'milk'. Did you mean one of these?
      ----------------------------------------
      👉  Whole Milk
      👉  Skim Milk
      👉  Powdered Milk
      ----------------------------------------

🚨 Since too many similar ingredients were found.
Try again with the specific ones listed above.
````
Other than that it basically list the recipies and ask for you to choose one.
## File Structure 📁:
````commandline
.
├── scrap_web.py           # Web Scpraing Module
├── database_filler.py     # Raw Data -> Falkor DB
├── db_util.py             # Database operation functions
├── find_recipe.py         # 🚀 Main Script that user integrated
├── foods1.json            # Temporary data bridge between web and DB
├── Saved_Recipes.txt      # 📄 OUTPUT TEXT FILE
````
### Thank you for using our servise, HAPPY COOKING 🧑‍🍳
# Find Your Recipe

Welcome to the Find Your Recipe repository! This project aims to provide a comprehensive and accessible collection of recipes that encourages users to explore diverse culinary traditions.

## Features
- A wide variety of recipes from different cuisines.
- User-friendly interface for navigating recipes.
- Ability to submit and share your own recipes.

## Installation
To get started with this project, clone the repository and install the required dependencies:
```bash
git clone https://github.com/Aleynaonrr/find-your-recipe.git
cd Recipe-Data
# Install dependencies
```

## Usage
Simply navigate through the recipes and find your favorites! You can submit your recipes through our submission form.


## Acknowledgments
Special thanks to everyone who contributed to this project and made it a success! 
