# Exercise 1(a): Program to Implement FCFS Scheduling

```
Name : Namachivayam T
Reg No : 212223060179
```

## Aim

To write and execute a C program to implement the First Come First Serve (FCFS) CPU scheduling algorithm and calculate the Waiting Time and Turnaround Time for each process along with their average values.

## Algorithm: FCFS (First Come First Serve) Scheduling

1. Start.

2. Read the number of processes `n`.

3. Input the Burst Time (BT) for each process.

4. Initialize the Waiting Time of the first process as 0.

5. Calculate the Waiting Time for the remaining processes using:

   `WT[i] = WT[i-1] + BT[i-1]`

6. Calculate the Turnaround Time for each process using:

   `TAT[i] = WT[i] + BT[i]`

7. Calculate the Average Waiting Time using:

   `Average WT = (Sum of all WT) / n`

8. Calculate the Average Turnaround Time using:

   `Average TAT = (Sum of all TAT) / n`

9. Display the Process ID, Burst Time, Waiting Time, and Turnaround Time for each process.

10. Display the Average Waiting Time and Average Turnaround Time.

11. Stop.

## Procedure for Executing the C Program

* Open a C programming environment such as GCC, Turbo C, Code::Blocks, or Dev-C++.
* Create a new C source file.
* Type or paste the FCFS scheduling program into the editor.
* Save the file with the extension `.c` (e.g., `fcfs.c`).
* Compile the program and ensure there are no syntax errors.
* Run the compiled program.
* Enter the number of processes and their burst times when prompted.
* Observe the Waiting Time, Turnaround Time, Average Waiting Time, and Average Turnaround Time displayed on the screen.
* Verify that the processes are executed in the order in which they arrive, following the FCFS principle.

## Program

```c
#include <stdio.h>

int main() {
    int n, i;
    int bt[20], wt[20], tat[20];
    float avg_wt = 0, avg_tat = 0;

    printf("Enter number of processes: ");
    scanf("%d", &n);

    for(i = 0; i < n; i++) {
        printf("Enter Burst Time for P%d: ", i + 1);
        scanf("%d", &bt[i]);
    }

    wt[0] = 0;

    for(i = 1; i < n; i++) {
        wt[i] = wt[i - 1] + bt[i - 1];
    }

    for(i = 0; i < n; i++) {
        tat[i] = wt[i] + bt[i];
    }

    printf("\nProcess\tBT\tWT\tTAT\n");

    for(i = 0; i < n; i++) {
        printf("P%d\t%d\t%d\t%d\n",
               i + 1, bt[i], wt[i], tat[i]);

        avg_wt += wt[i];
        avg_tat += tat[i];
    }

    printf("\nAverage Waiting Time = %.2f", avg_wt / n);
    printf("\nAverage Turnaround Time = %.2f\n", avg_tat / n);

    return 0;
}
```

## Output

<img width="1291" height="477" alt="image" src="https://github.com/user-attachments/assets/ede79263-2bf3-40bd-b940-135201c19bb2" />

## Result

Thus, the C program to implement the First Come First Serve (FCFS) CPU Scheduling Algorithm was executed successfully, and the Waiting Time, Turnaround Time, Average Waiting Time, and Average Turnaround Time were calculated and displayed successfully.
