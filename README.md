# lms-2
# EduLearn LMS

## Project Overview

EduLearn LMS is a comprehensive Learning Management System that combines a Java backend with a modern JavaScript frontend. It's designed to provide a robust platform for online learning, course management, and student engagement.

## Technologies Used

### Backend
- Java 11
- Maven 3.8.1
- MySQL 8.0
- JUnit 4.13.2
- Logback 1.2.6

### Frontend
- JavaScript (ES6+)
- Vite 5.4.2
- better-sqlite3 8.3.0
- crypto-js 4.1.1

## Project Structure
edulearn-lms/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/
│   │   │       └── edulearn/
│   │   │           ├── controllers/
│   │   │           ├── models/
│   │   │           ├── services/
│   │   │           └── utils/
│   │   └── resources/
│   │       └── logback.xml
│   └── test/
│       └── java/
│           └── com/
│               └── edulearn/
│                   └── tests/
├── public/
│   ├── index.html
│   └── assets/
├── src/
│   ├── components/
│   ├── pages/
│   ├── styles/
│   ├── utils/
│   └── main.js
├── vite.config.js
├── package.json
├── package-lock.json
└── pom.xml


## Backend (Java)

### Maven Configuration (pom.xml)

```xml
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <groupId>com.edulearn</groupId>
    <artifactId>edulearn-lms</artifactId>
    <version>1.0-SNAPSHOT</version>

    <properties>
        <maven.compiler.source>11</maven.compiler.source>
        <maven.compiler.target>11</maven.compiler.target>
        <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
    </properties>

    <dependencies>
        <!-- Database -->
        <dependency>
            <groupId>mysql</groupId>
            <artifactId>mysql-connector-java</artifactId>
            <version>8.0.27</version>
        </dependency>

        <!-- Testing -->
        <dependency>
            <groupId>junit</groupId>
            <artifactId>junit</artifactId>
            <version>4.13.2</version>
            <scope>test</scope>
        </dependency>

        <!-- Logging -->
        <dependency>
            <groupId>ch.qos.logback</groupId>
            <artifactId>logback-classic</artifactId>
            <version>1.2.6</version>
        </dependency>
    </dependencies>

    <build>
        <plugins>
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-compiler-plugin</artifactId>
                <version>3.8.1</version>
                <configuration>
                    <source>11</source>
                    <target>11</target>
                </configuration>
            </plugin>
        </plugins>
    </build>
</project>
FRONTEND(JAVASCRIPT)
{
  "name": "edulearn-lms",
  "private": true,
  "version": "1.0.0",
  "type": "module",
  "scripts": {
    "dev": "vite",
    "build": "vite build",
    "preview": "vite preview"
  },
  "dependencies": {
    "better-sqlite3": "^8.3.0",
    "crypto-js": "^4.1.1"
  },
  "devDependencies": {
    "vite": "^5.4.2"
  }
}

Vite Configuration (vite.config.js)
import { defineConfig } from 'vite';

export default defineConfig({
  server: {
    port: 3000,
    open: true
  },
  build: {
    outDir: 'dist',
    assetsDir: 'assets',
    rollupOptions: {
      input: {
        main: 'index.html'
      }
    }
  }
});
