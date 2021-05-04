## About this repository

### 1. Configurations :
   - This folder contains some basic and repetitive configurations across all projects and branches 
    
   **[create_maven_project.py](configurations/create_maven_project.py)** 
   - This a script creates a maven project.
   - This saves the user from having to remember the commands to create a project.
   - Script is called with destination folder, groupId and artifactId arguments as needed by maven.
   - Example call(as executable) from the terminal would be:
      ``` bash
      create_maven_project -d destination_folder -GID groupId -AID artifactId
      ``` 

   **[edit_project_pom_file.py](configurations/edit_project_pom_file.py)**
   - This script appends some useful pom.xml dependencies, particulaly for Junit5.
   - For maven projects, edit the pom.xml file to add the junit api engine and params shown below.
   - This will fix issues such as the @BeforeEach and @Parameterized tests not being recognised
   - If more information is needed visit the [mvn repository](https://mvnrepository.com/artifact/org.junit.jupiter).
        ``` xml
        <dependency>
            <groupId>org.junit.jupiter</groupId>
            <artifactId>junit-jupiter-engine</artifactId>
            <version>5.8.0-M1</version>
            <scope>test</scope>
        </dependency>
        <!-- https://mvnrepository.com/artifact/org.junit.jupiter/junit-jupiter-params -->
        <dependency>
            <groupId>org.junit.jupiter</groupId>
            <artifactId>junit-jupiter-params</artifactId>
            <version>5.8.0-M1</version>
            <scope>test</scope>
        </dependency>
        ```
    