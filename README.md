# 🛡️ SecureAPI-Showcase: SQL Injection Lab

Este proyecto es un laboratorio controlado desarrollado en **Java 21** y **Spring Boot 4** para demostrar la identificación, explotación y mitigación de vulnerabilidades de **Inyección SQL (SQLi)**.

---

### 🎯 Objetivo
El objetivo es proporcionar un entorno práctico para entender cómo las consultas concatenadas permiten la manipulación de la base de datos y cómo las **Consultas Parametrizadas** (Prepared Statements) eliminan este riesgo.

---

### 🚀 Tecnologías Utilizadas

![Java](https://img.shields.io/badge/Java_21-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot_4-6DB33F?style=for-the-badge&logo=spring-boot&logoColor=white)
![H2](https://img.shields.io/badge/Base_de_Datos-H2-007396?style=for-the-badge&logo=databricks&logoColor=white)
![Maven](https://img.shields.io/badge/Build-Maven-C71A36?style=for-the-badge&logo=apache-maven&logoColor=white)

---

### 🏗️ Estructura del Proyecto

El laboratorio se divide en dos enfoques principales para comparar el comportamiento de la aplicación:

* **` /api/v1/search `**: **Endpoint Vulnerable.** Permite inyección de código mediante concatenación de Strings.
* **` /api/v2/search `**: **Endpoint Seguro.** Utiliza parámetros vinculados para sanitizar el input.

---

### 🧪 Pruebas de Concepto (PoC)

#### 1. Explotación (V1)
Intento de recuperación de toda la base de datos de usuarios sin conocer sus nombres:

```bash
curl "http://localhost:8080/api/v1/search?name=' OR '1'='1"
