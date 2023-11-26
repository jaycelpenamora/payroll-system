# payroll-system

## Business Rules Draft (Someone must make a proper document)

##  Entities
  #### **Employee:** 
  *Represents individual employees within the organization.*
  #### **Payroll:** 
  *Represents payroll information for each pay period.*
  #### **Tax:** 
  *Represents tax information for calculations, recording and reporting.*
  #### **PaymentMethod:**
  *Represents the method through which an employee receives their payment in a payroll system*
  #### **HRAdmin:**
  *Represents administrative users responsible for managing the payroll system.*
    For the implementation of functionalities within the system to manage HR-related tasks such as:
    Creating, updating, or deleting employee records.
    Setting access permissions or roles for different users within the HR system.
    Generating reports related to employee data or payroll.
  #### **Department:**
  *Represents different departments within the organization.*
  #### **Benefit:**
  *Represents additional benefits provided to employees.* Compensation beyond the base salary such as health insurance, retirement plans, bonuses, etc.
  #### **Timekeeping:**
  *Represents the time worked by employees, which may be used for payroll calculations.* Used to calculate wages based on hourly rates or to monitor attendance.
  #### **Deduction Types:**
  *Tables storing information about different types of deductions.*
  
    -- Example records
    INSERT INTO DeductionType (deduction_type_id, name, description, amount)
    VALUES
    (1, 'Income Tax', 'Federal income tax deduction', NULL),
    (2, 'Health Insurance', 'Employee health insurance contribution', 50.00);
 
  #### **Earning Types:**
  *Tables storing information about different types of earning types.*
  
      -- Example records
      INSERT INTO EarningsType (earnings_type_id, name, description, amount)
      VALUES
      (1, 'Base Salary', 'Regular monthly salary', 3000.00),
      (2, 'Overtime', 'Additional pay for overtime hours', 200);
  #### **Salary Adjustments: **
  *Table that contains information about different salary adjustments. This enables historical tracking of changes to an employee's compensation.*
  
    -- Example records
    INSERT INTO SalaryAdjustment (adjustment_id, employee_id, adjustment_type, amount, adjustment_date)
    VALUES
    (1, 101, 'Promotion', 500.00, '2023-03-01'),
    (2, 102, 'Annual Raise', 100.00, '2023-04-01');
  
##  Relationships
#### Employee - Payroll Relationship
  One-to-Many an employee can have none (meaning its the employee's first month) or multiple payroll records over time. Each payroll record is associated with one specific employee. 
#### Employee - Benefit Relationship:
  One-to-Many an employee can have none or multiple benefits recorded. Each benefit record is associated with one specific employee. 
#### Employee - Timekeeping Relationship: 
  One-to-Many an employee can have multiple timekeeping records. Each timekeeping record is associated with one specific employee.
#### HRAdmin - Employee Relationship:
  One-to-Many Atleast one HR admin will be responsible for multiple employees. Each employee is associated with (or managed by) a specific HR administrator.
#### Employee - Department Relationship:
  Many-to-One multiple employees can belong to the same department. A department must contain atleast one employee.
#### Employee - Tax Relationship:
  One-to-Many an employee can have multiple tax records over time.
#### Employee - PaymentMethod Relationship:
  One-to-Many an employee must have atleast one to multiple payment methods over time.
#### HRAdmin - Department Relationship:
  One-to-Many an HR admin can be responsible for multiple departments. Each department is managed by one HR administrator. Administrative oversight or responsibility.
#### Deduction Types - Payroll
  One-to-Many Many payroll records must be associated with at least one deduction type (tax). This means that a deduction type (e.g., Income Tax) can be applied to multiple employees in their payroll records.
#### Earnings Types - Payroll
  One-to-Many Many payroll records must be associated with at least one earnings type. This means that an earnings type (e.g., Base Salary) can be applied to multiple employees in their payroll records.
#### Employee - SalaryAdjustment 
 One-to-many relationship, this is because one employee can have multiple salary adjustments over time, but each salary adjustment is associated with one specific employee. 
> [!NOTE]
> 1. Pictures of the diagram in relational model (engineering notation) and logical model are uploaded in issues section.
> 2. If you want the  actual diagram send me an email at 202210041@fit.edu.ph
> 3. Its up to you to if you want to remodel or make alterations.
> 4. If the diagram is giving you a headache consult me so we can adjust it.
> 5. If the majority considers the system done we may proceed to creating sample records for the tables created.
