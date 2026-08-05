**Experiment 1**



\#include <stdio.h>

\#include<unistd.h>

int main()

{

&#x20;   printf("Process ID: %d\\n", getpid() );

&#x20;   printf("Parent Process ID: %d\\n", getpid() );

&#x20;   return 0;

}



\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



**Experiment 2**



\#include <stdio.h>

\#include <stdlib.h>



int main()

{

&#x20;   FILE \*fptr1, \*fptr2;

&#x20;   char filename\[100], c;



&#x20;   printf("Enter the filename to open for reading:\\n");

&#x20;   scanf("%s", filename);



&#x20;   fptr1 = fopen(filename, "r");



&#x20;   if (fptr1 == NULL)

&#x20;   {

&#x20;       printf("Cannot open file %s\\n", filename);

&#x20;       exit(0);

&#x20;   }



&#x20;   printf("Enter the filename to open for writing:\\n");

&#x20;   scanf("%s", filename);



&#x20;   fptr2 = fopen(filename, "w");



&#x20;   if (fptr2 == NULL)

&#x20;   {

&#x20;       printf("Cannot open file %s\\n", filename);

&#x20;       exit(0);

&#x20;   }



&#x20;   c = fgetc(fptr1);



&#x20;   while (c != EOF)

&#x20;   {

&#x20;       fputc(c, fptr2);

&#x20;       c = fgetc(fptr1);

&#x20;   }



&#x20;   printf("\\nContents copied to %s\\n", filename);



&#x20;   fclose(fptr1);

&#x20;   fclose(fptr2);



&#x20;   return 0;

}



\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



**Experiment 3**



\#include <stdio.h>



int main()

{

&#x20;   int A\[100]\[4];

&#x20;   int i, j, n, total = 0, index, temp;

&#x20;   float avg\_wt, avg\_tat;



&#x20;   printf("Enter number of process: ");

&#x20;   scanf("%d", \&n);



&#x20;   printf("Enter Burst Time:\\n");



&#x20;   for (i = 0; i < n; i++)

&#x20;   {

&#x20;       printf("P%d: ", i + 1);

&#x20;       scanf("%d", \&A\[i]\[1]);

&#x20;       A\[i]\[0] = i + 1;

&#x20;   }



&#x20;   // Sorting processes according to Burst Time (SJF)

&#x20;   for (i = 0; i < n; i++)

&#x20;   {

&#x20;       index = i;



&#x20;       for (j = i + 1; j < n; j++)

&#x20;       {

&#x20;           if (A\[j]\[1] < A\[index]\[1])

&#x20;               index = j;

&#x20;       }



&#x20;       temp = A\[i]\[1];

&#x20;       A\[i]\[1] = A\[index]\[1];

&#x20;       A\[index]\[1] = temp;



&#x20;       temp = A\[i]\[0];

&#x20;       A\[i]\[0] = A\[index]\[0];

&#x20;       A\[index]\[0] = temp;

&#x20;   }



&#x20;   // Calculating Waiting Time

&#x20;   A\[0]\[2] = 0;



&#x20;   for (i = 1; i < n; i++)

&#x20;   {

&#x20;       A\[i]\[2] = 0;



&#x20;       for (j = 0; j < i; j++)

&#x20;       {

&#x20;           A\[i]\[2] += A\[j]\[1];

&#x20;       }



&#x20;       total += A\[i]\[2];

&#x20;   }



&#x20;   avg\_wt = (float)total / n;

&#x20;   total = 0;



&#x20;   printf("\\nP\\tBT\\tWT\\tTAT\\n");



&#x20;   // Calculating Turnaround Time

&#x20;   for (i = 0; i < n; i++)

&#x20;   {

&#x20;       A\[i]\[3] = A\[i]\[1] + A\[i]\[2];

&#x20;       total += A\[i]\[3];



&#x20;       printf("P%d\\t%d\\t%d\\t%d\\n",

&#x20;              A\[i]\[0],

&#x20;              A\[i]\[1],

&#x20;              A\[i]\[2],

&#x20;              A\[i]\[3]);

&#x20;   }



&#x20;   avg\_tat = (float)total / n;



&#x20;   printf("\\nAverage Waiting Time = %.2f", avg\_wt);

&#x20;   printf("\\nAverage Turnaround Time = %.2f\\n", avg\_tat);



&#x20;   return 0;

}

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



**Experiment 4**



\#include <stdio.h>



int main()

{

&#x20;   int bt\[20], p\[20], wt\[20], tat\[20];

&#x20;   int i, j, n, total = 0, pos, temp;

&#x20;   float avg\_wt, avg\_tat;



&#x20;   printf("Enter number of process: ");

&#x20;   scanf("%d", \&n);



&#x20;   printf("\\nEnter Burst Time:\\n");



&#x20;   for (i = 0; i < n; i++)

&#x20;   {

&#x20;       printf("P%d: ", i + 1);

&#x20;       scanf("%d", \&bt\[i]);

&#x20;       p\[i] = i + 1;

&#x20;   }



&#x20;   // Sort processes according to Burst Time (SJF)

&#x20;   for (i = 0; i < n; i++)

&#x20;   {

&#x20;       pos = i;



&#x20;       for (j = i + 1; j < n; j++)

&#x20;       {

&#x20;           if (bt\[j] < bt\[pos])

&#x20;               pos = j;

&#x20;       }



&#x20;       temp = bt\[i];

&#x20;       bt\[i] = bt\[pos];

&#x20;       bt\[pos] = temp;



&#x20;       temp = p\[i];

&#x20;       p\[i] = p\[pos];

&#x20;       p\[pos] = temp;

&#x20;   }



&#x20;   // Calculate Waiting Time

&#x20;   wt\[0] = 0;



&#x20;   for (i = 1; i < n; i++)

&#x20;   {

&#x20;       wt\[i] = 0;



&#x20;       for (j = 0; j < i; j++)

&#x20;       {

&#x20;           wt\[i] += bt\[j];

&#x20;       }



&#x20;       total += wt\[i];

&#x20;   }



&#x20;   avg\_wt = (float)total / n;

&#x20;   total = 0;



&#x20;   printf("\\nProcess\\tBurst Time\\tWaiting Time\\tTurnaround Time\\n");



&#x20;   // Calculate Turnaround Time

&#x20;   for (i = 0; i < n; i++)

&#x20;   {

&#x20;       tat\[i] = bt\[i] + wt\[i];

&#x20;       total += tat\[i];



&#x20;       printf("P%d\\t%d\\t\\t%d\\t\\t%d\\n",

&#x20;              p\[i], bt\[i], wt\[i], tat\[i]);

&#x20;   }



&#x20;   avg\_tat = (float)total / n;



&#x20;   printf("\\nAverage Waiting Time = %.2f", avg\_wt);

&#x20;   printf("\\nAverage Turnaround Time = %.2f\\n", avg\_tat);



&#x20;   return 0;

}



\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



**Experiment 5**



\#include <stdio.h>



struct priority\_scheduling

{

&#x20;   char process\_name;

&#x20;   int burst\_time;

&#x20;   int waiting\_time;

&#x20;   int turn\_around\_time;

&#x20;   int priority;

};



int main()

{

&#x20;   int number\_of\_process;

&#x20;   int total = 0;

&#x20;   int ASCII\_number = 65;

&#x20;   int position;



&#x20;   float average\_waiting\_time;

&#x20;   float average\_turnaround\_time;



&#x20;   struct priority\_scheduling temp\_process;



&#x20;   printf("Enter the total number of Processes: ");

&#x20;   scanf("%d", \&number\_of\_process);



&#x20;   struct priority\_scheduling process\[number\_of\_process];



&#x20;   printf("\\nPlease Enter the Burst Time and Priority of each process:\\n");



&#x20;   for (int i = 0; i < number\_of\_process; i++)

&#x20;   {

&#x20;       process\[i].process\_name = (char)ASCII\_number;



&#x20;       printf("\\nEnter the details of the process %c\\n",

&#x20;              process\[i].process\_name);



&#x20;       printf("Enter the burst time: ");

&#x20;       scanf("%d", \&process\[i].burst\_time);



&#x20;       printf("Enter the priority: ");

&#x20;       scanf("%d", \&process\[i].priority);



&#x20;       ASCII\_number++;

&#x20;   }



&#x20;   // Sort processes according to priority (Higher priority first)

&#x20;   for (int i = 0; i < number\_of\_process; i++)

&#x20;   {

&#x20;       position = i;



&#x20;       for (int j = i + 1; j < number\_of\_process; j++)

&#x20;       {

&#x20;           if (process\[j].priority > process\[position].priority)

&#x20;           {

&#x20;               position = j;

&#x20;           }

&#x20;       }



&#x20;       temp\_process = process\[i];

&#x20;       process\[i] = process\[position];

&#x20;       process\[position] = temp\_process;

&#x20;   }



&#x20;   process\[0].waiting\_time = 0;



&#x20;   for (int i = 1; i < number\_of\_process; i++)

&#x20;   {

&#x20;       process\[i].waiting\_time = 0;



&#x20;       for (int j = 0; j < i; j++)

&#x20;       {

&#x20;           process\[i].waiting\_time += process\[j].burst\_time;

&#x20;       }



&#x20;       total += process\[i].waiting\_time;

&#x20;   }



&#x20;   average\_waiting\_time = (float)total / (float)number\_of\_process;



&#x20;   total = 0;



&#x20;   printf("\\n\\nProcess\_name\\tBurst Time\\tWaiting Time\\tTurnaround Time\\n");

&#x20;   printf("---------------------------------------------------------------\\n");



&#x20;   for (int i = 0; i < number\_of\_process; i++)

&#x20;   {

&#x20;       process\[i].turn\_around\_time =

&#x20;           process\[i].burst\_time + process\[i].waiting\_time;



&#x20;       printf("%c\\t\\t%d\\t\\t%d\\t\\t%d\\n",

&#x20;              process\[i].process\_name,

&#x20;              process\[i].burst\_time,

&#x20;              process\[i].waiting\_time,

&#x20;              process\[i].turn\_around\_time);



&#x20;       total += process\[i].turn\_around\_time;

&#x20;   }



&#x20;   average\_turnaround\_time = (float)total / (float)number\_of\_process;



&#x20;   printf("\\nAverage Waiting Time    : %.2f", average\_waiting\_time);

&#x20;   printf("\\nAverage Turnaround Time : %.2f\\n",

&#x20;          average\_turnaround\_time);



&#x20;   return 0;

}



\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



Experiment 6



\#include <stdio.h>

\#include <conio.h>



int main()

{

&#x20;   int i, NOP, sum = 0, count = 0, y, quant;

&#x20;   int wt = 0, tat = 0;

&#x20;   int at\[10], bt\[10], temp\[10];



&#x20;   float avg\_wt, avg\_tat;



&#x20;   printf("Total number of processes in the system: ");

&#x20;   scanf("%d", \&NOP);



&#x20;   y = NOP;



&#x20;   for (i = 0; i < NOP; i++)

&#x20;   {

&#x20;       printf("\\nEnter the Arrival and Burst Time of Process\[%d]\\n", i + 1);



&#x20;       printf("Arrival Time: ");

&#x20;       scanf("%d", \&at\[i]);



&#x20;       printf("Burst Time: ");

&#x20;       scanf("%d", \&bt\[i]);



&#x20;       temp\[i] = bt\[i];

&#x20;   }



&#x20;   printf("\\nEnter the Time Quantum: ");

&#x20;   scanf("%d", \&quant);



&#x20;   printf("\\nProcess No\\tBurst Time\\tTurnaround Time\\tWaiting Time\\n");



&#x20;   for (sum = 0, i = 0; y != 0;)

&#x20;   {

&#x20;       if (temp\[i] <= quant \&\& temp\[i] > 0)

&#x20;       {

&#x20;           sum += temp\[i];

&#x20;           temp\[i] = 0;

&#x20;           count = 1;

&#x20;       }

&#x20;       else if (temp\[i] > 0)

&#x20;       {

&#x20;           temp\[i] -= quant;

&#x20;           sum += quant;

&#x20;       }



&#x20;       if (temp\[i] == 0 \&\& count == 1)

&#x20;       {

&#x20;           y--;



&#x20;           printf("\\nProcess\[%d]\\t%d\\t\\t%d\\t\\t%d",

&#x20;                  i + 1,

&#x20;                  bt\[i],

&#x20;                  sum - at\[i],

&#x20;                  sum - at\[i] - bt\[i]);



&#x20;           wt += sum - at\[i] - bt\[i];

&#x20;           tat += sum - at\[i];



&#x20;           count = 0;

&#x20;       }



&#x20;       if (i == NOP - 1)

&#x20;       {

&#x20;           i = 0;

&#x20;       }

&#x20;       else if (at\[i + 1] <= sum)

&#x20;       {

&#x20;           i++;

&#x20;       }

&#x20;       else

&#x20;       {

&#x20;           i = 0;

&#x20;       }

&#x20;   }



&#x20;   avg\_wt = (float)wt / NOP;

&#x20;   avg\_tat = (float)tat / NOP;



&#x20;   printf("\\n\\nAverage Turnaround Time : %.2f", avg\_tat);

&#x20;   printf("\\nAverage Waiting Time    : %.2f\\n", avg\_wt);



&#x20;   getch();

&#x20;   return 0;

}



\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



Experiment 7



\#include <stdio.h>



int main()

{

&#x20;   int at\[10], bt\[10], pr\[10];

&#x20;   int n, i, j, temp;

&#x20;   int time = 0, count, over = 0;

&#x20;   int sum\_wait = 0, sum\_turnaround = 0, start;

&#x20;   float avgwait, avgturn;



&#x20;   printf("Enter the number of processes\\n");

&#x20;   scanf("%d", \&n);



&#x20;   for (i = 0; i < n; i++)

&#x20;   {

&#x20;       printf("Enter the arrival time and execution time for process %d\\n", i + 1);

&#x20;       scanf("%d%d", \&at\[i], \&bt\[i]);

&#x20;       pr\[i] = i + 1;

&#x20;   }



&#x20;   /\* Sort according to arrival time \*/

&#x20;   for (i = 0; i < n - 1; i++)

&#x20;   {

&#x20;       for (j = i + 1; j < n; j++)

&#x20;       {

&#x20;           if (at\[i] > at\[j])

&#x20;           {

&#x20;               temp = at\[i];

&#x20;               at\[i] = at\[j];

&#x20;               at\[j] = temp;



&#x20;               temp = bt\[i];

&#x20;               bt\[i] = bt\[j];

&#x20;               bt\[j] = temp;



&#x20;               temp = pr\[i];

&#x20;               pr\[i] = pr\[j];

&#x20;               pr\[j] = temp;

&#x20;           }

&#x20;       }

&#x20;   }



&#x20;   printf("\\n\\nProcess\\t|Arrival Time\\t|Execution Time\\t|Start Time\\t|End Time\\t|Waiting Time\\t|Turnaround Time\\n\\n");



&#x20;   while (over < n)

&#x20;   {

&#x20;       count = 0;



&#x20;       for (i = over; i < n; i++)

&#x20;       {

&#x20;           if (at\[i] <= time)

&#x20;               count++;

&#x20;           else

&#x20;               break;

&#x20;       }



&#x20;       /\* Sort available processes according to burst time \*/

&#x20;       if (count > 1)

&#x20;       {

&#x20;           for (i = over; i < over + count - 1; i++)

&#x20;           {

&#x20;               for (j = i + 1; j < over + count; j++)

&#x20;               {

&#x20;                   if (bt\[i] > bt\[j])

&#x20;                   {

&#x20;                       temp = at\[i];

&#x20;                       at\[i] = at\[j];

&#x20;                       at\[j] = temp;



&#x20;                       temp = bt\[i];

&#x20;                       bt\[i] = bt\[j];

&#x20;                       bt\[j] = temp;



&#x20;                       temp = pr\[i];

&#x20;                       pr\[i] = pr\[j];

&#x20;                       pr\[j] = temp;

&#x20;                   }

&#x20;               }

&#x20;           }

&#x20;       }



&#x20;       start = time;

&#x20;       time += bt\[over];



&#x20;       printf("P\[%d]\\t|\\t%d\\t|\\t%d\\t|\\t%d\\t|\\t%d\\t|\\t%d\\t|\\t%d\\n",

&#x20;              pr\[over],

&#x20;              at\[over],

&#x20;              bt\[over],

&#x20;              start,

&#x20;              time,

&#x20;              time - at\[over] - bt\[over],

&#x20;              time - at\[over]);



&#x20;       sum\_wait += time - at\[over] - bt\[over];

&#x20;       sum\_turnaround += time - at\[over];



&#x20;       over++;

&#x20;   }



&#x20;   avgwait = (float)sum\_wait / (float)n;

&#x20;   avgturn = (float)sum\_turnaround / (float)n;



&#x20;   printf("Average waiting time is %f\\n", avgwait);

&#x20;   printf("Average turnaround time is %f\\n", avgturn);



&#x20;   return 0;

}



\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



Experiment 8



\#include <stdio.h>

\#include <conio.h>



int main()

{

&#x20;   int i, NOP;

&#x20;   int sum = 0, count = 0, y, quant;

&#x20;   int wt = 0, tat = 0;

&#x20;   int at\[10], bt\[10], temp\[10];

&#x20;   float avg\_wt, avg\_tat;



&#x20;   printf("Total number of processes in the system: ");

&#x20;   scanf("%d", \&NOP);



&#x20;   y = NOP;



&#x20;   for (i = 0; i < NOP; i++)

&#x20;   {

&#x20;       printf("\\nEnter the Arrival and Burst Time of Process\[%d]\\n", i + 1);



&#x20;       printf("Arrival Time: ");

&#x20;       scanf("%d", \&at\[i]);



&#x20;       printf("Burst Time: ");

&#x20;       scanf("%d", \&bt\[i]);



&#x20;       temp\[i] = bt\[i];

&#x20;   }



&#x20;   printf("\\nEnter the Time Quantum: ");

&#x20;   scanf("%d", \&quant);



&#x20;   printf("\\nProcess No\\tBurst Time\\tTurnaround Time\\tWaiting Time\\n");



&#x20;   for (sum = 0, i = 0; y != 0;)

&#x20;   {

&#x20;       if (temp\[i] <= quant \&\& temp\[i] > 0)

&#x20;       {

&#x20;           sum += temp\[i];

&#x20;           temp\[i] = 0;

&#x20;           count = 1;

&#x20;       }

&#x20;       else if (temp\[i] > 0)

&#x20;       {

&#x20;           temp\[i] -= quant;

&#x20;           sum += quant;

&#x20;       }



&#x20;       if (temp\[i] == 0 \&\& count == 1)

&#x20;       {

&#x20;           y--;



&#x20;           printf("Process\[%d]\\t%d\\t\\t%d\\t\\t%d\\n",

&#x20;                  i + 1,

&#x20;                  bt\[i],

&#x20;                  sum - at\[i],

&#x20;                  sum - at\[i] - bt\[i]);



&#x20;           wt += sum - at\[i] - bt\[i];

&#x20;           tat += sum - at\[i];



&#x20;           count = 0;

&#x20;       }



&#x20;       if (i == NOP - 1)

&#x20;       {

&#x20;           i = 0;

&#x20;       }

&#x20;       else if (at\[i + 1] <= sum)

&#x20;       {

&#x20;           i++;

&#x20;       }

&#x20;       else

&#x20;       {

&#x20;           i = 0;

&#x20;       }

&#x20;   }



&#x20;   avg\_wt = (float)wt / NOP;

&#x20;   avg\_tat = (float)tat / NOP;



&#x20;   printf("\\nAverage Turnaround Time: %f", avg\_tat);

&#x20;   printf("\\nAverage Waiting Time: %f", avg\_wt);



&#x20;   getch();

&#x20;   return 0;

}

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



**EXPERIMENT 9**



\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



**EXPERIMENT 10**



\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



**EXPERIMENT 11**



\#include <stdio.h>

\#include <pthread.h>



void\* threadFunction(void\* arg)

{

&#x20;   char\* message = (char\*)arg;

&#x20;   printf("%s\\n", message);



&#x20;   return NULL;

}



int main()

{

&#x20;   pthread\_t thread1, thread2;



&#x20;   char\* message1 = "Hello from Thread 1!";

&#x20;   char\* message2 = "Hello from Thread 2!";



&#x20;   // Create threads

&#x20;   pthread\_create(\&thread1, NULL, threadFunction, (void\*)message1);

&#x20;   pthread\_create(\&thread2, NULL, threadFunction, (void\*)message2);



&#x20;   // Wait for threads to complete

&#x20;   pthread\_join(thread1, NULL);

&#x20;   pthread\_join(thread2, NULL);



&#x20;   return 0;

}

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



**EXPERIMENT 12**



\#include <stdio.h>

\#include <stdlib.h>

\#include <pthread.h>

\#include <unistd.h>



\#define NUM\_PHILOSOPHERS 5



pthread\_mutex\_t chopsticks\[NUM\_PHILOSOPHERS];



void\* philosopherLifeCycle(void\* arg)

{

&#x20;   int id = \*((int\*)arg);

&#x20;   int left\_chopstick = id;

&#x20;   int right\_chopstick = (id + 1) % NUM\_PHILOSOPHERS;



&#x20;   while (1)

&#x20;   {

&#x20;       // Think

&#x20;       printf("Philosopher %d is thinking...\\n", id);



&#x20;       // Pick up chopsticks

&#x20;       pthread\_mutex\_lock(\&chopsticks\[left\_chopstick]);

&#x20;       pthread\_mutex\_lock(\&chopsticks\[right\_chopstick]);



&#x20;       // Eat

&#x20;       printf("Philosopher %d is eating...\\n", id);

&#x20;       sleep(rand() % 3 + 1);



&#x20;       // Put down chopsticks

&#x20;       pthread\_mutex\_unlock(\&chopsticks\[left\_chopstick]);

&#x20;       pthread\_mutex\_unlock(\&chopsticks\[right\_chopstick]);

&#x20;   }



&#x20;   return NULL;

}



int main()

{

&#x20;   pthread\_t philosophers\[NUM\_PHILOSOPHERS];

&#x20;   int philosopher\_ids\[NUM\_PHILOSOPHERS];



&#x20;   // Initialize mutex locks

&#x20;   for (int i = 0; i < NUM\_PHILOSOPHERS; i++)

&#x20;   {

&#x20;       pthread\_mutex\_init(\&chopsticks\[i], NULL);

&#x20;   }



&#x20;   // Create philosopher threads

&#x20;   for (int i = 0; i < NUM\_PHILOSOPHERS; i++)

&#x20;   {

&#x20;       philosopher\_ids\[i] = i;



&#x20;       pthread\_create(

&#x20;           \&philosophers\[i],

&#x20;           NULL,

&#x20;           philosopherLifeCycle,

&#x20;           (void\*)\&philosopher\_ids\[i]

&#x20;       );

&#x20;   }



&#x20;   // Wait for threads to finish

&#x20;   for (int i = 0; i < NUM\_PHILOSOPHERS; i++)

&#x20;   {

&#x20;       pthread\_join(philosophers\[i], NULL);

&#x20;   }



&#x20;   // Destroy mutex locks

&#x20;   for (int i = 0; i < NUM\_PHILOSOPHERS; i++)

&#x20;   {

&#x20;       pthread\_mutex\_destroy(\&chopsticks\[i]);

&#x20;   }



&#x20;   return 0;

}



Pseudocode



BEGIN



Initialize 5 chopsticks.



FOR each philosopher (0 to 4)

&#x20;   Create a philosopher thread.

END FOR



REPEAT FOREVER

&#x20;   Think.

&#x20;   Pick up left and right chopsticks.

&#x20;   Eat.

&#x20;   Put down both chopsticks.

END REPEAT



Wait for all philosopher threads.



END

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



**EXPERIMENT 13**



\#include <stdio.h>



void bestfit(int mp\[], int p\[], int m, int n)

{

&#x20;   int j = 0;



&#x20;   for (int i = 0; i < n; i++)

&#x20;   {

&#x20;       if (mp\[i] > p\[j])

&#x20;       {

&#x20;           printf("\\n%d fits in %d", p\[j], mp\[i]);

&#x20;           mp\[i] = mp\[i] - p\[j++];

&#x20;           i = i - 1;

&#x20;       }

&#x20;   }



&#x20;   for (int i = j; i < m; i++)

&#x20;   {

&#x20;       printf("\\n%d must wait for its process", p\[i]);

&#x20;   }

}



void rsort(int a\[], int n)

{

&#x20;   for (int i = 0; i < n; i++)

&#x20;   {

&#x20;       for (int j = 0; j < n; j++)

&#x20;       {

&#x20;           if (a\[i] > a\[j])

&#x20;           {

&#x20;               int t = a\[i];

&#x20;               a\[i] = a\[j];

&#x20;               a\[j] = t;

&#x20;           }

&#x20;       }

&#x20;   }

}



void sort(int a\[], int n)

{

&#x20;   for (int i = 0; i < n; i++)

&#x20;   {

&#x20;       for (int j = 0; j < n; j++)

&#x20;       {

&#x20;           if (a\[i] < a\[j])

&#x20;           {

&#x20;               int t = a\[i];

&#x20;               a\[i] = a\[j];

&#x20;               a\[j] = t;

&#x20;           }

&#x20;       }

&#x20;   }

}



void firstfit(int mp\[], int p\[], int m, int n)

{

&#x20;   sort(mp, n);

&#x20;   sort(p, m);

&#x20;   bestfit(mp, p, m, n);

}



void worstfit(int mp\[], int p\[], int m, int n)

{

&#x20;   rsort(mp, n);

&#x20;   sort(p, m);

&#x20;   bestfit(mp, p, m, n);

}



int main()

{

&#x20;   int m, n, mp\[20], p\[20], ch;



&#x20;   printf("Number of memory partitions : ");

&#x20;   scanf("%d", \&n);



&#x20;   printf("Number of process : ");

&#x20;   scanf("%d", \&m);



&#x20;   printf("Enter the memory partitions:\\n");

&#x20;   for (int i = 0; i < n; i++)

&#x20;   {

&#x20;       scanf("%d", \&mp\[i]);

&#x20;   }



&#x20;   printf("Enter process size:\\n");

&#x20;   for (int i = 0; i < m; i++)

&#x20;   {

&#x20;       scanf("%d", \&p\[i]);

&#x20;   }



&#x20;   printf("1. First Fit\\t2. Best Fit\\t3. Worst Fit");

&#x20;   printf("\\nEnter your choice : ");

&#x20;   scanf("%d", \&ch);



&#x20;   switch (ch)

&#x20;   {

&#x20;       case 1:

&#x20;           bestfit(mp, p, m, n);

&#x20;           break;



&#x20;       case 2:

&#x20;           firstfit(mp, p, m, n);

&#x20;           break;



&#x20;       case 3:

&#x20;           worstfit(mp, p, m, n);

&#x20;           break;



&#x20;       default:

&#x20;           printf("Invalid choice");

&#x20;           break;

&#x20;   }



&#x20;   return 0;

}

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



**EXPERIMENT 14**



\#include <stdio.h>

\#include <stdlib.h>

\#include <fcntl.h>

\#include <unistd.h>



\#define BUFFER\_SIZE 4096



void copy()

{

&#x20;   const char \*sourcefile =

&#x20;       "C:/Users/itssk/OneDrive/Desktop/sasi.txt";

&#x20;   const char \*destination\_file =

&#x20;       "C:/Users/itssk/OneDrive/Desktop/sk.txt";



&#x20;   int source\_fd = open(sourcefile, O\_RDONLY);

&#x20;   int dest\_fd = open(destination\_file,

&#x20;                      O\_WRONLY | O\_CREAT | O\_TRUNC,

&#x20;                      0666);



&#x20;   char buffer\[BUFFER\_SIZE];

&#x20;   ssize\_t bytesRead, bytesWritten;



&#x20;   while ((bytesRead = read(source\_fd, buffer, BUFFER\_SIZE)) > 0)

&#x20;   {

&#x20;       bytesWritten = write(dest\_fd, buffer, bytesRead);

&#x20;   }



&#x20;   close(source\_fd);

&#x20;   close(dest\_fd);



&#x20;   printf("File copied successfully.\\n");

}



void create()

{

&#x20;   FILE \*fp;



&#x20;   fp = fopen("C:/Users/itssk/OneDrive/Desktop/sasi.txt", "w");

&#x20;   printf("File created successfully.\\n");



&#x20;   fclose(fp);

}



int main()

{

&#x20;   int n;



&#x20;   printf("1. Create \\t2. Copy \\t3. Delete");

&#x20;   printf("\\nEnter your choice: ");

&#x20;   scanf("%d", \&n);



&#x20;   switch (n)

&#x20;   {

&#x20;       case 1:

&#x20;           create();

&#x20;           break;



&#x20;       case 2:

&#x20;           copy();

&#x20;           break;



&#x20;       case 3:

&#x20;           remove("C:/Users/itssk/OneDrive/Desktop/sasi.txt");

&#x20;           printf("Deleted successfully.\\n");

&#x20;           break;



&#x20;       default:

&#x20;           printf("Invalid choice.\\n");

&#x20;   }



&#x20;   return 0;

}

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



**EXPERIMENTS 15**



\#include <stdio.h>

\#include <stdlib.h>

\#include <string.h>



int main()

{

&#x20;   char mainDirectory\[] = "C:/Users/itssk/OneDrive/Desktop";

&#x20;   char subDirectory\[] = "os";

&#x20;   char fileName\[] = "example.txt";



&#x20;   char filePath\[200];

&#x20;   char mainDirPath\[200];



&#x20;   snprintf(mainDirPath,

&#x20;            sizeof(mainDirPath),

&#x20;            "%s/%s/",

&#x20;            mainDirectory,

&#x20;            subDirectory);



&#x20;   snprintf(filePath,

&#x20;            sizeof(filePath),

&#x20;            "%s%s",

&#x20;            mainDirPath,

&#x20;            fileName);



&#x20;   FILE \*file = fopen(filePath, "w");



&#x20;   if (file == NULL)

&#x20;   {

&#x20;       printf("Error creating file.\\n");

&#x20;       return 1;

&#x20;   }



&#x20;   fprintf(file, "This is an example file content.");

&#x20;   printf("File created successfully: %s\\n", filePath);



&#x20;   fclose(file);



&#x20;   return 0;

}

\_\_\_\_\_\_\_\_\_\_\_\_\_



**EXPERIMENT 16**

