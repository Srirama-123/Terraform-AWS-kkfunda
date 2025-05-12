
# 🛠️ Terraform Workflow – In-Depth Explanation

![Terraform Workflow](../Diagrams/tf-workflow.png)

---

## 🧩 1. `Init` – Initialize Terraform Project

### 📌 Description:
- Sets up the working directory for Terraform.
- Downloads required **providers** and sets up **backend** if defined.

### ✅ What You Do:
```bash
terraform init
````

* Creates `.terraform/` directory.
* Prepares the system for further operations.

---

## ✅ 2. `Validate` – Check Configuration Syntax

### 📌 Description:

* Validates `.tf` files to ensure they are **syntactically correct** and **internally consistent**.
* Does not check external resources or real-time AWS status.

### ✅ Command:

```bash
terraform validate
```

---

## 📐 3. `Plan` – Preview Execution Changes

### 📌 Description:

* Generates an **execution plan** showing what Terraform will do:

  * Add
  * Change
  * Destroy

### ✅ Command:

```bash
terraform plan
```

### 🧠 Real-Time Insight:

* Useful for code review and approval processes.
* Prevents accidental infrastructure changes.

---

## 🚀 4. `Apply` – Provision Infrastructure

### 📌 Description:

* Applies changes and provisions AWS infrastructure as per the plan.
* By default, it asks for confirmation before proceeding.

### ✅ Command:

```bash
terraform apply
```

### 🧠 Real-Time Tip:

* Use `-auto-approve` in CI/CD tools (with caution).
* Creates resources and updates `.tfstate`.

---

## 🧹 5. `Destroy` – Tear Down Infrastructure

### 📌 Description:

* Deletes all resources managed by Terraform.
* Asks for confirmation to prevent accidental deletions.

### ✅ Command:

```bash
terraform destroy
```

### ⚠️ Real-Time Advice:

* Useful in dev/test environments.
* Always double-check what will be destroyed.

---

## 🔄 Summary of Lifecycle Phases

| Phase      | Command              | Purpose                                     |
| ---------- | -------------------- | ------------------------------------------- |
| `init`     | `terraform init`     | Initialize directory and download providers |
| `validate` | `terraform validate` | Syntax check for Terraform configs          |
| `plan`     | `terraform plan`     | Preview execution plan before apply         |
| `apply`    | `terraform apply`    | Create/update infrastructure on AWS         |
| `destroy`  | `terraform destroy`  | Remove all managed resources                |

---




