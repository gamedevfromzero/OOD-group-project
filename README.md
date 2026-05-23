# JSRT 12 - Java Sustainable Recycling Tool 12. Console application for estimating impact of recycling on the environment and recycling guidance

### Abstract:
This is a group project for the **Kristianstad University** course **DA121A VT26** Object-Oriented Design. The main goal is to write a program that utilize "Responsible Consumption and Production" [Sustainable Development Goal 12](https://globalgoals.org/goals/12-responsible-consumption-and-production/). The project itself is a Java application with console interface and various text menus for navigation. The code is written in Java with regard to Object-Oriented Design principles and aims to showcase the course material knowledge of students. The project simulates the real working environment and development process that students will experience in the future. 

### Functionality:
The program introduce terms material, product, category, recycling guidance (reffered as guidance), environmental report and recycling report (reffered as report), and project.  
- Material - abstract material that has defined properties required for environmental impact calculation.

- Product - abstract product that has list of materials and it's ratio in total mass or 1 kg of product. Also has total weight and lifespan property.

- Recycling category - abstract recycling category that has a range of acceptable material and/or product properties. Applied automatically to the suitable products and/or materials.

- Recycling guidance - textual description of recycling guidance for selected recycling category(s).

- Environmental/Recycling report - estimated environental impact of product recyclement and recycling guidance for material(s) and/or product(s).

- Project - collection of added materials, products, categories and reports. Can be saved, loaded or switched to facilitate usage of the program for the end user.

## How to use?
Program starts with an empty project with basic materials. User have to add new product(s) and may add new materia(s). 
> [!NOTE]
> It is possible to load it directly from file or directory from a .json file or load the whole project.

After that user can make a new report that will include the product(s) **recycling impact** on **environment**.
> [!NOTE]
> To make report include recycling guidance, materials and products should have suitable **recycling category** and **recycling guidance** assigned to it.

A recycling guidance will assign itself to the products and materials by it's custom filter. Then a recycling guidance should be written and assigned for recycling category to show up in the report. User can create, load or switch between different projects within one console window. If user wants to save the project, it has to specify a path where project file will be written and materials, productss, categories, guidances and reports will be stored in subfolders. It gives the opportunity to combine previously generated information and use it more flexible. 
> [!NOTE]
> The whole project with all products, materials, categories, guidances and reports can be saved and loaded by *write* and *read* dialog option.

## Menu options
| Menu option  | Name |                                     Description                                       |
|--------------|------|---------------------------------------------------------------------------------------|
| *h* or help  | **help** dialog | Show this menu or extra help on the certain dialog option.                 |
| *n* or new   | **new** dialog | Create a new material/product/category/guidance/report or a new project.    |                                                     
| *r* or read  | **read** from disk dialog | Load a saved material/product/category/guidance/report or a saved project using .json format. |
| *l* or list  | **list** dialog | List all existing material/product/category/guidance/report or open projects. |
| *e* or edit  | **edit** dialog | Edit an existing material/product/category/guidance/report or active project. |
| *s* or show  | **select** dialog | Select certain material/product/category/guidance/report or switch active project. |
| *w* or write | **write** to disk dialog | Use to save material/product/category/guidance/report or active project using .json format. |
| *a* or about | **about** information | Show application information and authors. |
| *q* or quit  | **quit** dialog | Self explanatory. Close the application. | 

## Project architecture
The application follows the DDD principle and internaly consists of 3 layers
- Presentation
- Application
- Domain

The application follows the defined [UML class diagram](docs/UML.puml) that defines the relations between classes.

The code is designed according to main Object-Oriented Design principles: 
The application emphasizes **maintainable, testable, and well-structured code**, demonstrating clear responsibility distribution and professional development practices.

This project is designed and tested with Java 25. There is no 100% guarantee that the project will work on older versions of Java but it most litkely will, since this project uses pretty stable API from Java 17 and above.

---

## Team
Current developers
| Role | Name |
|------|------|
| Lead developer | Vladyslav Yanchuk |
| Design Validator | Bonniface Mwangi Maina |
| Domain Logic Developer | Bonniface Mwangi Maina | 

Former developers
| Role | Name | 
|------|------|
| *Console UI Developer* | *Maksym Ignatiev* | 
| *Concept Researcher & Explainer* | *Ayyub Lindroos* |
| | *Shady Khalil* |

## Run the project

To run the project, either use the pre-configured build tool, Make:
```sh
make
```
with optional targets:
  - `compile`
  - `execute`

and optional patameters:
  - `verbose=<boolean>`: show more information on how the compilation and execution is done

or compile the source code from the `./src/` directory manually, excluding `./src/test/` directory, which contains tests. Entry point to the project is `./src/Main.java`


### Tests 

To run unit tests, either use the pre-configured build tool, Make:
```sh
make test
```
with optional parameters:
  - `silent=<boolean>`: suppresses the logging of each testing step
  - `verbose=<boolean>`: shows extra information what make does under the hood
  - `method=<1|powershell|2|bitsadmin|3|curl>`: method for downloading dependency files on Windows (default: `powershell`). If one method is slow or unavailable, try another one.

or compile the source test code from the `./src/test/` directory manually, including the JUnit framework jar dependency, which can be obtained by running the:
```sh
make get-junit
```
or by downloading the JUnit 5+ jar file from the maven repositories manually.

The 'all-in-one' tests target is `test-full` (which accepts the same parameters as the `test` target), which involves:
  - compilation of the source project code into bytecode (options from `compile` and `execute` targets apply)
  - compilation of the source test code into bytecode
  - execution of the tests

This target ensures that the tests always have the latest bytecode of both, the project and the tests, minimizing the riscs of testing the old code.

---

## License

This project is licensed under the 0BSD License - see the [LICENSE](LICENSE) file for details.  
