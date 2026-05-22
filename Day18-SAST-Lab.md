# Day 18 - DevSecOps SAST Lab

## Objective
Build a CI/CD pipeline that performs static application security testing using GitHub CodeQL.

## Tool Used
- GitHub Actions
- CodeQL

## Vulnerability Tested
SQL Injection risk due to unsafe string concatenation in SQL query.

## Vulnerable Code
The original code directly concatenated user input into SQL query.

## Fix Applied
Replaced string concatenation with parameterized query.

## Security Lesson
Never trust user input. Use parameterized queries to prevent SQL Injection.

## Pipeline Result
CodeQL scan completed successfully.
