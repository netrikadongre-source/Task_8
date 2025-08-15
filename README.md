# Task_8: Maven Build Automation with Jenkins

This project demonstrates how to build and package a simple Java application using **Apache Maven** integrated with **Jenkins Freestyle Job** running inside a Docker container.

---

## 📌 Project Overview
- **Goal**: Automate a Java Maven build process using Jenkins.
- **Java Version**: 21 (Temurin) installed in Jenkins container.
- **Maven Version**: Auto-installed via Jenkins (3.9.11 in this build).
- **Build Tool**: Maven `clean package` goal.
- **Result**: Successfully compiled and packaged into a `.jar` file.

---

## 🛠 Prerequisites
- Docker installed and running.
- Jenkins LTS Docker image set up.
- JDK 21 available inside Jenkins container.
- Maven configured in Jenkins tool configuration.

---

## 🚀 Setup & Execution Steps

1. **Clone or prepare project locally**
   ```bash
   git clone <your-repo-url>
   cd Task_8
   ```

2. **Copy project into Jenkins workspace**
   ```bash
   docker cp . <jenkins_container_id>:/var/jenkins_home/workspace/Task_8
   ```
   
3. **Jenkins Configuration**
   - JDK Installations:
       - Name: `JDK-21`
       - JAVA_HOME: `/opt/java/openjdk`
       - Uncheck *Install automatically*
         
   - Maven Installations:
       - Name: `My-Maven`
       - Enable *Install automatically* (e.g., Maven 3.9.11).

4. **Create Freestyle Job**
   - Name: `Task_8`
   - No SCM (if manually copied).
   - Build Step: *Invoke top-level Maven targets* → Goals: `clean package`.
  
5. **Run the Job**
   - Click Build Now in Jenkins.
   - Click Build Now in Jenkins.
     ```csharp
     [INFO] BUILD SUCCESS
     ```

## 📂 Repository Contents
   - `pom.xml` – Maven configuration (Java 21 compatibility)
   - `src/` – Java source code
   - `output.txt` – Full Jenkins console log
   - `screenshots/` – Proof of Jenkins build configuration and results

## 🖼 Results
   - Maven build completed successfully inside Jenkins.
   - Packaged `.jar` file generated in `target/` folder
   - Logs and screenshots included for reference.

## ✍ Author
***Netrika Dongre~***
