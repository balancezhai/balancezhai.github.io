---
title: "AppControl: Enforcing Application Behaviour through Type-Based Constraints (EP/V000462/1)"
excerpt: "<br/><img src='/images/prop_appctrl_iv.png'>"
collection: portfolio
---

## About this project
This project was supported the Digital Security by Design (DSbD) Programme delivered by UKRI to support the DSbD ecosystem (EPSRC [EP/V000462/1](https://gow.epsrc.ukri.org/NGBOViewGrant.aspx?GrantRef=EP/V000462/1), through , in partner with the University of Glasgow and Imperial College London.

## Key Ideas
To secure program interaction we need to go beyond access privileges and ensure that a program follows the intended behavioural specification. Because Capabilities say nothing about program behaviour, we will also use Behavioural Types to capture the physical and behavioural structure of application interfaces.
- Behavioural typing supports compile-time checking of program behaviour when its implementation is known, and runtime checking of program behaviour when it is not known. 
- We will leverage CHERI's Capabilities to ensure that behavioural types are not modified by parties unknown.

## Debugging Infrastructure
- Design-by-specification will ensure correctness of behaviour, provided that the specification is correct. Debugging a specification-based system, demands the ability to debug the specification at run-time.
- Debugging system will include continuous diagnostics tools that allow to evaluate the system operation continuously and can identify hardware failure or unusual system behaviour.

![Debugging system](/images/prop_appctrl_b.png)