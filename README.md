# PROG6112_Test

# PROG6112 Exam Cheatsheet & Reference Repository

* **Author:** Sachin Mahabeer
* **GitHub Username:** `SMahabeer07`
* **Repository:** [PROG6112_Test](https://github.com/SMahabeer07/PROG6112_Test.git)

---

## 📋 Assessment Rules & Instructions

1. **Permitted Resources:** This is an open-book assessment. You may refer to your own repositories, previous projects, notes, textbooks, and the internet.


2. **Use of AI:** **Strictly prohibited.** All work must be completed independently without AI assistance.
3. **Environment:** Use of the provided Virtual Machine (VM) is strongly recommended as all software is pre-installed. Using a local device means you are entirely responsible for troubleshooting your own environment.
4. **Referencing & Attribution:** Acknowledge external sources, documentation, or code snippets using **Harvard Anglia** referencing style and include code attribution comments where applicable.
5. **Submission Requirements:** You must submit your final work to **both ARC and GitHub**.



---

## 🧩 Java Logic & File Handling Cheatsheet

### 1. Two-Dimensional Arrays (Processing Rows & Columns)

```java
// Traversing a 2D array to calculate totals/averages
int total = 0;
int count = 0;
int highest = sales[0][0];
int lowest = sales[0][0];

for (int i = 0; i < sales.length; i++) {
    for (int j = 0; j < sales[i].length; j++) {
        total += sales[i][j];
        count++;
        if (sales[i][j] > highest) highest = sales[i][j];
        if (sales[i][j] < lowest) lowest = sales[i][j];
    }
}
double average = (double) total / count;

```

---

### 2. Implementing Interfaces

```java
public interface ITicketSales {
    int TotalTicketSales(int[] ticketSales);
    double AverageTicketSales(int[] ticketSales);
    int HighestSale(int[] ticketSales);
    int LowestSale(int[] ticketSales);
}

public class TicketSales implements ITicketSales {
    @Override
    public int TotalTicketSales(int[] ticketSales) {
        int sum = 0;
        for (int val : ticketSales) sum += val;
        return sum;
    }
    // Implement remaining interface methods here...
}

```

---

### 3. File Handling (Writing to a Text File)

```java
import java.io.BufferedWriter;
import java.io.FileWriter;
import java.io.IOException;

public void saveReportToFile(String reportContent, String fileName) {
    try (BufferedWriter writer = new BufferedWriter(new FileWriter(fileName))) {
        writer.write("SALES LOG\n");
        writer.write("********************\n");
        writer.write(reportContent);
        writer.write("\n********************");
    } catch (IOException e) {
        System.out.println("Error saving file: " + e.getMessage());
    }
}

```

---

### 4. JUnit 5 Unit Testing Basics

```java
import static org.junit.jupiter.api.Assertions.assertEquals;
import org.junit.jupiter.api.Test;

public class TicketSalesTest {

    @Test
    public void CalculateTotalTicketSales_ReturnsTotalTicketSales() {
        TicketSales salesObj = new TicketSales();
        int[] sampleData = {420, 310, 180, 390};
        int expectedTotal = 1300;
        
        int actualTotal = salesObj.TotalTicketSales(sampleData);
        
        assertEquals(expectedTotal, actualTotal, "Total ticket sales calculation is incorrect.");
    }
}

```
