# BPMN Process Modeling – Scenarios 1, 2 & 3

## Overview

This repository contains BPMN process models for three real-world business processes:

1. **Employee Leave Approval**
2. **Online Purchase Order Processing**
3. **IT Service Request**

The BPMN models demonstrate the use of **Start Events, Tasks, Exclusive Gateways, Alternative Paths, Sequence Flows, and End Events**.

---

# Scenario 1: Employee Leave Approval

## Process Description

The process begins when an employee submits a leave request through the company's HR system.

### Process Flow

1. The employee **submits a leave request**.
2. The HR system **checks the employee's leave balance**.
3. An **Exclusive Gateway** checks whether sufficient leave balance is available.
4. If the balance is insufficient, the system **sends an insufficient-balance notification** and the process ends.
5. If sufficient balance is available, the request is **sent to the manager for approval**.
6. The manager decides whether to approve or reject the request.
7. If approved, the system **updates the employee's leave balance** and **sends an approval notification**.
8. If rejected, the system **sends a rejection notification**.
9. The process ends after the appropriate notification.

### BPMN Flow

**Start Event → Submit Leave Request → Check Leave Balance → Exclusive Gateway**

* **Insufficient Balance → Send Insufficient-Balance Notification → End Event**
* **Sufficient Balance → Send Request to Manager → Exclusive Gateway**

  * **Approved → Update Leave Balance → Send Approval Notification → End Event**
  * **Rejected → Send Rejection Notification → End Event**

---

# Scenario 2: Online Purchase Order Processing

## Process Description

The process begins when a customer places an online order. The system checks product availability and payment status before completing the order.

### Process Flow

1. The customer **places an order**.
2. The system **checks product availability**.
3. An **Exclusive Gateway** checks whether the product is available.
4. If unavailable, the system **sends an out-of-stock notification** to the customer and the process ends.
5. If available, the system **processes the payment**.
6. An **Exclusive Gateway** checks whether the payment is successful.
7. If payment fails, the system **sends a payment failure notification** and the process ends.
8. If payment is successful, the system **confirms the order**.
9. The product is **prepared for shipment**.
10. The order is **shipped**.
11. The customer **receives a shipping confirmation**.
12. The process ends.

### BPMN Flow

**Start Event → Place Order → Check Product Availability → Exclusive Gateway**

* **Unavailable → Send Out-of-Stock Notification → End Event**
* **Available → Process Payment → Exclusive Gateway**

  * **Payment Failed → Send Payment Failure Notification → End Event**
  * **Payment Successful → Confirm Order → Prepare Product → Ship Order → Send Shipping Confirmation → End Event**

---

# Scenario 3: IT Service Request

## Process Description

The process begins when an employee reports an IT problem. The help desk registers and evaluates the problem before assigning it to the appropriate technician.

### Process Flow

1. The employee **submits an IT support request**.
2. The IT help desk **registers the request**.
3. The help desk **checks the severity of the problem**.
4. An **Exclusive Gateway** determines the severity.
5. If the problem is low severity, it is **assigned to a support technician**.
6. If the problem is high severity, it is **assigned to a senior technician**.
7. The technician **investigates the problem**.
8. An **Exclusive Gateway** checks whether the problem can be resolved internally.
9. If it can be resolved, the technician **fixes the problem**.
10. If it cannot be resolved internally, the technician **escalates it to an external service provider**.
11. After resolution, the help desk **updates the request status**.
12. The employee **receives a resolution notification**.
13. The process ends.

### BPMN Flow

**Start Event → Submit IT Support Request → Register Request → Check Problem Severity → Exclusive Gateway**

* **Low Severity → Assign to Support Technician → Investigate Problem**
* **High Severity → Assign to Senior Technician → Investigate Problem**

Both paths continue to:

**Investigate Problem → Exclusive Gateway**

* **Can Be Resolved → Fix Problem → Update Request Status**
* **Cannot Be Resolved Internally → Escalate to External Service Provider → Update Request Status**

Then:

**Update Request Status → Send Resolution Notification → End Event**

---

# BPMN Elements Used

| BPMN Element          | Purpose                                         |
| --------------------- | ----------------------------------------------- |
| **Start Event**       | Indicates where a process begins                |
| **Task**              | Represents an activity performed in the process |
| **Exclusive Gateway** | Selects one path based on a condition           |
| **Sequence Flow**     | Shows the order and direction of activities     |
| **Alternative Paths** | Allow the process to follow different routes    |
| **End Event**         | Indicates where a process path ends             |

---

# Conclusion

These three BPMN scenarios demonstrate how business processes can be modeled using standard BPMN elements. **Exclusive Gateways** are used to make decisions and create alternative paths based on conditions such as leave balance, manager approval, product availability, payment status, problem severity, and issue resolution.

The models provide a simple representation of real-world processes and show how different outcomes can lead to different process paths and end events.
