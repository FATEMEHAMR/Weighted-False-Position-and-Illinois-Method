# Weighted False Position and Illinois Method

This project implements and compares two improved numerical root-finding methods:

- **Modified False Position Method / Illinois Method**
- **Improved / Weighted False Position Method**

The program is written in **Python** and allows the user to enter a nonlinear function, an initial interval, a tolerance value, and a maximum number of iterations. It then applies both methods and prints detailed iteration tables for comparison.

The main goal of this project is to study how improved versions of the classical False Position method can solve nonlinear equations more efficiently and more reliably without requiring derivatives.

---

## Table of Contents

- [Project Overview](#project-overview)
- [Numerical Background](#numerical-background)
- [Implemented Methods](#implemented-methods)
  - [Modified False Position Method / Illinois Method](#modified-false-position-method--illinois-method)
  - [Improved / Weighted False Position Method](#improved--weighted-false-position-method)
- [Features](#features)
- [Project Structure](#project-structure)
- [Requirements](#requirements)
- [How to Run](#how-to-run)
- [Input Format](#input-format)
- [Example Usage](#example-usage)
- [Sample Test Cases](#sample-test-cases)
- [Code Explanation](#code-explanation)
- [Method Comparison](#method-comparison)
- [Error Handling](#error-handling)
- [Limitations](#limitations)
- [Future Improvements](#future-improvements)
- [Authors](#authors)
- [License](#license)

---

## Project Overview

Finding roots of nonlinear equations is one of the fundamental problems in numerical analysis. Many engineering, physics, and mathematical problems lead to equations that cannot be solved analytically. In such cases, numerical methods are used to approximate the roots.

The classical **False Position Method**, also known as **Regula Falsi**, is a bracketing method. It starts with an interval `[a, b]` where the function changes sign:

```text
f(a) × f(b) < 0
