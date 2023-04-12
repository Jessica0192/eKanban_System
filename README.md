<h1 align="center">eKanban System</h1>
A customized system was created for a fog light manufacturing company, utilizing the Kanban approach, to provide real-time updates and information to every level of the organizational structure. The system is also equipped with features for database configuration and employee management, and provides comprehensive data visualization tools for monitoring updates on parts and the overall manufacturing process.


## Important Note
The content of this repository is an academic project and should not be made public as it is related to academic coursework. Any misuse of the project may result in serious consequences, including academic penalties and disciplinary action. A video recording of the project is available for viewing, and access to the code base and additional materials related to this project may be granted only for legitimate educational or research purposes. Please contact me directly to make a request.


## Technology Stack
Microsoft SQL Server
C#
.NET Framework
Microsoft Visual Studio


## Database Design
The database structure comprises several tables that store different types of data. These tables include:
* AssemblyStations table: includes information about each assembly station, such as its ID and name
* CompletedLamps table: includes information about each completed fog lamp, such as its ID, assembly station, and defect status
* Configurations table: includes simulation configuration parameters, such as the time scale and defect rates
* Employee table: includes information about employee, such as its ID, name and skill level
* TestTrays table: includes information about each test tray, such as its ID and completion status


## Stored Procedures, Functions, and Triggers
### Stored Procedures
* HandleTray: it handles Test Tray's product number when a new product is created. It creates a new tray if the previous one has reached the maximum number of products, and it calculates the number of failed and passed products in the current tray
* CreateNewProduct: it creates a new product (Fog Lamp) by calling the HandleTray and DecreasePartAmount procedures to handle the amount of parts and tray number
* ReplenishParts: it replenishes the parts of a workstation that has its flag turned on

### Functions
* CalculateYieldForEachWorkstation: it calculates the yield for a specific workstation
* CalculateYieldForAllRunningWorkstation: it calculates the average yield for all the running workstations
* GetNumberOfProductProducedForWorkstation: it returns the number of products produced by a specific workstation

### Triggers
* CreateCompletedLamp: a trigger that generates a fresh lamp entry in the records once a lamp has been assembled at a specific assembly station


## Programs
* Configuration Tool: the table allows for full configuration of parameters for the simulation, such as the time scale and starting quantities of each part bin. Other parameters that can be configured include the defect rates for each skill level and the capacity of test trays.
* Workstation Simulation: represents a single assembly station and provides the simulated timing surrounding the creation of a fog lamp
* Workstation Andon: displays a graphic representation of the part counts and status of a single assembly station in real-time
* AssemblyLine Visualization: displays the status of the entire assembly line in real-time, in the form of a conventional Kanban display


## Demonstration


https://user-images.githubusercontent.com/70799519/231313830-930e191b-e374-4621-8ff3-d1f663080c47.mp4





