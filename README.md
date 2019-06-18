# MBTA-Reqs-over-50K-Report

## Purpose

This is a small weekly report delivered to the Senior Director featuring all requisitions with Sum Amounts greater than $50,000 assigned to Non-Inventory Buyers. The Senior Director uses this report in a meeting with the NINV Buyers to choose which reqs. to prioritize and receive updates on their progress.

### Data Requirements

#### `SLT_SPILT_REQ_SIDE_GT_50K_####.xlsx`

The file name above (excluding everything after "50K") is a query in FMIS that should be pulled. The file should contain the following columns:

| Columns                      | Definition/Use                                     |
| ---------------------------- | -------------------------------------------------- |
| Buyer                        | Buyer assigned to that requisition                 |
| Req Total                    | Total amount spent on req.; repeated on each line  |
| Business_Unit                | Business unit that requisition is under            |
| Req ID                       | Unique Identifier for each requisition             |
| Req_Line                     | Count of line for that specific requisition        |
| More Info                    | Detailed explanation of specific requisition line  |
| Status                       | Req. Status; always "A" in this dataframe          |
| Req Date                     | Date of requisition's creation                     |
| Origin                       | Not used                                           |
| UOM                          | Not used                                           |
| Req Qty                      | Quantity of item purchased in that req. line       |
| Price                        | Price of items on each req. line                   |
| Requester                    | Not used                                           |
| Approval_Date                | Date of requisition's approval                     |
| Approved_By                  | Not used                                           |
| FUND                         | Funding sourced of each requisition                |
| Req Descr                    | Description of each req.; Differs from "More Info" |
| Buyer2                       | Buyer assigned to that req. at the Header level    |

* The column "Age" is manually added to the dataframe after the pull, and it is the number of days between today and Approval_Date

### Output File(s)

Once the data is pulled and "Age" is added, the dataframe should be divided into two sheets: One filtered by the Buyers "CFRANCIS," "JKIDD," AND "JMIELE," and the other featuring all other Buyers. In addition, each sheet should be sorted from newest to oldest on "Age," and a bolded border should delineate reqs younger than one week from reqs older than one week.

