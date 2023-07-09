
## 3.24
Employee -> (0, 3) -> Has_phone -> (0, 1) -> Phone
I assume an employee can at most have one phone. But multiple employees can have phones.

Employee -> (0, 2) -> Works_in -> (1, 10) -> Department
I assume that every department will have at least one employee, and can have up to 10 employees.

Department -> (1, 3) -> Contains -> (1) -> Phone
I assume a phone can only have one phone number.


## 3.25
Instructor -> (2, 4) -> Teaches -> (1, 1) -> Course
I assume that a course can only have one teacher.

Course -> (0, 1) -> Uses -> (0, 5) -> Text
I assume that courses can't use the same texts as other courses.

Instructor -> (0, 20) -> Adopts -> (0, 1) -> Text
Since an instructor can teach up to 4 courses, i assume they can adopt up to 20 texts. And since I assumed that a text can't be by multiple courses, a text can only appear once.


## 3.27
STUDENT (1 -> 1) SOCIAL_SECURITY_CARD

STUDENT (N -> M) TEACHER

CLASSROOM (N -> M) WALL

COUNTRY (1 -> 1) CURRENT_PRESIDENT

COURSE (N -> M) TEXTBOOK

ITEM (that can be found in an order) (N -> M) ORDER

STUDENT (N -> M) CLASS

CLASS (N -> M) INSTRUCTOR

INSTRUCTOR (N -> 1) OFFICE

EBAY_AUCTION_ITEM (1 -> N) EBAY_BID


## 3.28
1. True
2. Maybe
3. Maybe
4. True
5. Maybe
6. Maybe
7. False
8. Maybe
9. Maybe
10. Maybe
11. Maybe
12. Maybe


## 9.5

**Bank**
| <u>Code</u> | Name | Addr |
| ---- | ---- | ---- |

**Bank_Branch**
| <u>Branch_No</u> | Addr | <u>Code</u> |
| --------- | ---- | ---- |

**Account**
| <u>Acct_No</u> | Balance | Type | <u>Branch_No</u> |
| -------------- | ------- | ---- | ---------------- |

**Loan**
| <u>Loan_No</u> | Amount | Type | <u>Branch_No</u> |
| -------------- | ------ | ---- | ---------------- |

**Customer**
| <u>SSN</u> | Phone | Name | Addr |
| ---------- | ----- | ---- | ---- |

**A_C**
| <u>Acct_No</u> | <u>SSN</u> |
| -------------- | ---------- |

**L_C**
| <u>Loan_No</u> | <u>SSN</u> |
| -------------- | ---------- |


