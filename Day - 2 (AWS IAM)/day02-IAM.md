# AWS IAM (Identity and Access Management)


## What is Authentication and Authorization?

Before accessing any AWS resource, AWS needs to answer two questions:

### Authentication

Authentication verifies **who you are**.

Examples:

* Username and Password
* Access Keys
* Multi-Factor Authentication (MFA)

### Authorization

Authorization determines **what actions you are allowed to perform** after authentication.

Examples:

* Can create an EC2 instance
* Can read files from an S3 bucket
* Can delete resources

**Authentication = Who are you?**
**Authorization = What can you do?**

---

## 1. What is AWS IAM?

AWS IAM (Identity and Access Management) is a global AWS service that helps manage access to AWS resources securely.

Using IAM, administrators can:

* Create users and groups
* Assign permissions
* Control access to AWS services
* Enforce security policies

IAM ensures that only authorized users and services can access AWS resources.

---

## 2. Why Do We Need AWS IAM?

Imagine a company with multiple employees such as Developers, Testers, DevOps Engineers, and Managers.

Without IAM:

* Everyone would share the same AWS account.
* There would be no control over permissions.
* Security risks would increase.

IAM solves this by allowing administrators to provide specific permissions based on job responsibilities.

### Benefits of IAM

* Improved Security
* Fine-grained Access Control
* Centralized User Management
* Supports MFA
* Follows Principle of Least Privilege
* Audit and Compliance Support

---

## 3. Components of IAM

### IAM Users

An IAM User represents a person or application that needs access to AWS.

Examples:

* Developer
* Tester
* DevOps Engineer

Each user can have:

* Username
* Password
* Access Keys
* Permissions

---

### IAM Groups

A Group is a collection of IAM Users.

Instead of assigning permissions individually, permissions can be assigned to the group.

Example:

Developers Group:

* User1
* User2
* User3

When permissions are attached to the group, all users automatically inherit them.

---

### IAM Policies

Policies define permissions in AWS.

They are written in JSON format and specify:

* What actions are allowed
* What resources can be accessed
* Whether access is allowed or denied

Example:

* Allow EC2 Full Access
* Allow S3 Read Only Access

---

### IAM Roles

Roles provide temporary permissions to users, applications, or AWS services.

Unlike users, roles do not have permanent credentials.

Common use cases:

* EC2 accessing S3
* Lambda accessing DynamoDB
* Cross-account access

Roles are considered more secure because AWS manages temporary credentials automatically.

---

## 4. Practical Workflow

A typical IAM workflow:

1. Create an IAM User
2. Add the User to a Group
3. Attach Policies to the Group
4. Enable MFA for additional security
5. Test the User's permissions

Example:

Developer → Developers Group → EC2 Full Access Policy

Result:
The developer can manage EC2 instances but cannot access services that were not explicitly permitted.

---

## Best Practices

* Never use the Root Account for daily tasks.
* Enable MFA for all users.
* Follow the Principle of Least Privilege.
* Use Roles whenever possible.
* Rotate Access Keys regularly.
* Assign permissions through Groups instead of individual Users.

---

## Summary

AWS IAM is the foundation of AWS security. It manages authentication and authorization through Users, Groups, Policies, and Roles, ensuring that the right people and services have the right level of access to AWS resources.
