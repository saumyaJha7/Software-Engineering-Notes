---
tags:
  - BFFP
---
### *6. Security and Best Practices (The Golden Rules)* 

#### 1. *Never Hardcode Secrets:* Never place database URLs or API keys directly into your application's source code. 
#### 2. *Use Cloud Managers for Encryption:* Rely on tools like AWS Parameter Store or Vault. They ensure that your configs are mathematically encrypted while sitting in storage, and encrypted while traveling over the network to your server.

#### 3. *Access Control (Least Privilege):* Not every developer needs every key. Frontend devs only need backend API URLs; backend devs need database access; only DevOps teams should have access to cloud infra/EC2 configs.
#### 4. *Rotation:* Periodically rotate (change) your API keys and JWT secrets to limit the damage of potential leaks. 
#### 5. *Always Validate Configurations:* This is the most critical safeguard. When your application boots up, before it runs any business logic, use a library (like Zod in TypeScript or Go Validator) to rigorously check that every expected environment variable is present and correctly formatted. Missing a mandatory variable can cause bizarre production bugs that are incredibly difficult to trace.
