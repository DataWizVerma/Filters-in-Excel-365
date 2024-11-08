

# Excel Practice Solutions

This repository provides solutions for various Excel-based questions using functions like `FILTER`, `SUM`, `COUNTIFS`, and `SUMIFS`. Below are the questions along with the corresponding Excel formulas for each.

---

## Questions and Solutions

### 1. Print names of all people in either Sales or Website department

**Question:**  
Print names of all people in either Sales or Website department.

**Solution:**  
```excel
=FILTER(staff[Name], (staff[Department] = "Sales") + (staff[Department] = "Website"), "No data found")
```

---

### 2. Count of people who joined in the first 3 months of 2018 & 2019

**Question:**  
How many people have joined in the first 3 months of 2018 & 2019?

**Solution:**  
```excel
=SUM(COUNTIFS(staff[Date Joined], ">=1/1/2018", staff[Date Joined], "<=3/31/2018"),
     COUNTIFS(staff[Date Joined], ">=1/1/2019", staff[Date Joined], "<=3/31/2019"))
```

---

### 3. Print data for all "50% data bites" sold in New Zealand

**Question:**  
Print data for all "50% data bites" sold in New Zealand.

**Solution:**  
```excel
=FILTER(sales, (sales[Product] = "50% data bites") * (sales[Geography] = "New Zealand"), "No data found")
```

---

### 4. Total amount where country is neither India nor Australia

**Question:**  
What is the total amount where the country is neither India nor Australia?

**Solution:**  
```excel
=SUMIFS(sales[Amount], sales[Geography], "<>India", sales[Geography], "<>Australia")
```

---

### 5. Print data for all sales from other people where the amount is > average sales of Gunar Cockshoot

**Question:**  
Print data for all sales from other people where the amount is greater than the average sales of "Gunar Cockshoot."

**Solution:**  
1. First, calculate the average sales for "Gunar Cockshoot" and store it in cell `G2`:
   ```excel
   =AVERAGEIF(sales[Sales Person], "Gunar Cockshoot", sales[Amount])
   ```

2. Use this value in the `FILTER` formula to display relevant data:
   ```excel
   =FILTER(sales, (sales[Amount] > G2) * (sales[Sales Person] <> "Gunar Cockshoot"), "No data found")
   ```

---



