# CoronaSystem_Exe
# Project README

## Overview

This project is designed to handle employee data and Covid details. It consists of multiple layers, including the DAL (Data Access Layer), BL (Business Logic Layer), and MyService layer.


## MyService Layer
The MyService layer serves as the API layer for interacting with the application. It contains controllers that handle incoming HTTP requests and delegate processing to the BL layer. Controllers return appropriate HTTP responses with data or error messages.

### Files:
- **CovidDtailesController.cs**: Controller for handling Covid detail-related endpoints.
- **EmployeeController.cs**: Controller for handling employee-related endpoints.


## BL (Business Logic Layer)
The BL layer contains the business logic of the application. It orchestrates data manipulation and validation, calling appropriate methods from the DAL layer. It also contains mapping logic using AutoMapper for mapping between DTOs (Data Transfer Objects) and entities.

### Files:
- **CovidDetailesBl.cs**: Implements the `ICovidDatailesBl` interface for Covid detail-related business logic.
- **EmployeeBl.cs**: Implements the `IEmployeeBl` interface for employee-related business logic.


## DAL (Data Access Layer)
The DAL is responsible for interacting with the database and performing CRUD operations. It contains implementations for various data access interfaces, such as `IEmployeeDal`, `ICovidDetailDal`, etc. Each DAL implementation interacts with the database context (`DB_Context`) using Entity Framework Core.

### Files:
- **CityServiceDal.cs**: Implements the `ICityDal` interface for city-related operations.
- **CovidDetailServiceDal.cs**: Implements the `ICovidDetailDal` interface for Covid detail-related operations.
- **EmployeeServiceDal.cs**: Implements the `IEmployeeDal` interface for employee-related operations.
- **VaccineManufacturerServiceDal.cs**: Implements the `IVaccineManufacturerDal` interface for vaccine manufacturer-related operations.
- **StreetServiceDal.cs**: Implements the `IStreetDal` interface for street-related operations.
- **AddressServiceDal.cs**: Implements the `IAddressDal` interface for address-related operations.


## How to Run the Project
first- open the 'corona_Hub_exe.sln' file at the 'corona_Hub_Exe' dir:
![image-10](https://github.com/TovaGolimstok/CoronaSystem_Exe/assets/164151470/63f7177e-0ddb-4e82-9c79-9a2839c8e7a3)
![image-11](https://github.com/TovaGolimstok/CoronaSystem_Exe/assets/164151470/55545652-a5bc-4054-a8ec-44fbdb486307)
in the browse choose the db file from your local computer.
1.connect to the db file in the data connection in the server explorer tool.

2. Set up the database connection string:
      -go to file:'ServiceCollectionExtensions.cs'
      -at line :            string connString = "...here" replace the connString to your connection string of your db connection.
      - go to file:'DB_Context.cs' in models dir in dal layer 
      -at func: 'public OnConfiguring' 
      -change th connstring:at optionsBuilder.UseSqlServer(...here)

3. Run the database migrations to create the database schema.

4. Start the application and make HTTP requests to the defined endpoints.
when you run up the project there will be a swgger up with a locallhost 5073(http://localhost:5073/swagger/index.html):
![image](https://github.com/TovaGolimstok/CoronaSystem_Exe/assets/164151470/d18b4136-b8d9-4c16-a8a0-137f20398b34)
and then you can choose to create an employee or just to create employee_covid_detailes to a specific Numberid_employee.
1. create amployee:
![image-1](https://github.com/TovaGolimstok/CoronaSystem_Exe/assets/164151470/19fa4788-04e8-4c10-abe6-91522576a90a)
![image-2](https://github.com/TovaGolimstok/CoronaSystem_Exe/assets/164151470/05f5c221-6350-44ed-ad09-a391f53b8ddb)
and then enter the 'try it out' button:![Alt text](image-3.png)
and then enter all the parameters:
![image-4](https://github.com/TovaGolimstok/CoronaSystem_Exe/assets/164151470/8a8a5b83-4c20-4fd8-ac1d-349785a72ccb)
and then run the execute button:![image-5](https://github.com/TovaGolimstok/CoronaSystem_Exe/assets/164151470/4359ed90-f1f4-4977-8091-37d5f3588769)

and there will be a 200 status code of succes:![image-6](https://github.com/TovaGolimstok/CoronaSystem_Exe/assets/164151470/9111a005-64e8-451e-a432-e6f7ea24332e)


2. gat by id_employee or by number_id_employee:![image-7](https://github.com/TovaGolimstok/CoronaSystem_Exe/assets/164151470/7ba0b9d1-3f8b-4338-a2f6-e9b6fe70b7dc)

i choose by number_id_employee:![image-8](https://github.com/TovaGolimstok/CoronaSystem_Exe/assets/164151470/1a17c6c3-b0f9-4979-962a-5e80bab3e76a)

and then i got the information:![image-9](https://github.com/TovaGolimstok/CoronaSystem_Exe/assets/164151470/9d0d7dba-b201-4323-95ae-16115bdcf5ea)


