
### 🏆 Title

# 🚀 LeetCode 1075 | SQL Solution 💯

### GitHub README.md

Paste this **directly into the GitHub README edit box**:

```markdown
# 🚀 LeetCode 1075 | Project Employees I 💯

## 🔗 Problem

**LeetCode:** [1075. Project Employees I](https://leetcode.com/problems/project-employees-i/)

**Difficulty:** Easy  
**Language:** MySQL

---

## 🧠 Intuition

We need to find the average experience of employees working on each project.

The `Project` table contains the relationship between projects and employees, while the `Employee` table contains the experience of each employee.

We can join both tables using `employee_id` and calculate the average experience for each project.

---

## 🚀 Approach

1. Join the `Employee` and `Project` tables using `employee_id`.
2. Group the records by `project_id`.
3. Calculate the average experience using `AVG()`.
4. Round the average to 2 decimal places using `ROUND()`.

---

## 💻 SQL Solution

```mysql
SELECT 
    p.project_id,
    ROUND(AVG(e.experience_years), 2) AS average_years
FROM Employee e
INNER JOIN Project p 
    ON e.employee_id = p.employee_id
GROUP BY p.project_id;
