# Personal-Finance-Management

->User login(optional)
->#define ec Expense_Category


#class dig

Transaction->Expense
amount     ->Income
+------------------------+     +-------------------+     +----------------------+
|      Transaction      |     |     Expense       |     |    Investment        |
+------------------------+     +-------------------+     +----------------------+
| - amount: float       |     | - category_name: |     | - principal_amount:  |
|                      |     |   std::string     |     |   float              |
| + get_amount(): float |     | + get_amount():   |     | - interest_rate:     |
|                      |     |   float           |     |   float              |
+------------------------+     +-------------------+     | - tenure: int         |
                                                       |                      |
                                                       +----------------------+
       ^                         /|\                   /|\
       |                          |                     |
       |                          |                     |
       |                          |                     |
       |                          |                     |
       |                          |                     |
       |                          |                     |
       |                          |                     |
       |        +-----------------|---------------------+
       |        |                 |                     |
       |        |                 |                     |
       |        |                 |                     |
       |        |                 |                     |
       |        |                 |                     |
+------|------------------------+---------------------|----------------------+
| + get_source(): std::string |                       |                      |
|                           |                       |                      |
+---------------------------+                       |                      |
                                                   |                      |
            +-------------------+                   |                      |
            |     ExpenseCategory |                   |                      |
            +-------------------+                   |                      |
            | - name: std::string |                   |                      |
            | - expenses[100]:   |                   |                      |
            |     Expense*:      |                   |                      |
            | - num_expenses: int|                   |                      |
            +-------------------+                   |                      |
            | + record_expense():|                   |                      |
            | + total_expenses():|                   |                      |
            | + get_name():      |                   |                      |
            +-------------------+                   |                      |
                                                   |                      |
                        +-----------------+        |                      |
                        | FinanceManager  |        |                      |
                        +-----------------+        |                      |
                        | - expense_categories:|   |                      |
                        |     ExpenseCategory*  |   |                      |
                        | - investments[10]:   |   |                      |
                        |     Investment*:      |   |                      |
                        | - num_categories: int|   |                      |
                        | - num_investments: int|  |                      |
                        +-----------------+        |                      |
                        | + add_expense_category()| |                      |
                        | + add_investment():     | |                      |
                        | + record_expense():     | |                      |
                        | + calculate_total_expenses()| |                      |
                        | + calculate_total_investments()| |                      |
                        +-----------------+        |                      |
