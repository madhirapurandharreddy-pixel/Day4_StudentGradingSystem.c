#include <stdio.h>

int main()
{
    float s1, s2, s3, s4, s5;      // Marks in 5 subjects
    float total, percentage, attendance;

    printf("Enter marks in 5 subjects: ");
    scanf("%f %f %f %f %f", &s1, &s2, &s3, &s4, &s5);

    printf("Enter attendance percentage: ");
    scanf("%f", &attendance);


    if ((s1 < 0 || s1 > 100) || (s2 < 0 || s2 > 100) ||
        (s3 < 0 || s3 > 100) || (s4 < 0 || s4 > 100) || (s5 < 0 || s5 > 100))
        {
        printf("Error: Marks must be between 0 and 100.\n");
    }
    else
    {

        total = s1 + s2 + s3 + s4 + s5;
        percentage = total / 5;

        printf("Total Percentage: %.2f%%\n", percentage);
        printf("Attendance: %.2f%%\n", attendance);


        if (attendance < 75)
        {
            printf("Final Grade: F\n");
            printf("Remarks: Fail (Low Attendance)\n");
        }
        else
        {

            if (percentage >= 45 && percentage <= 49 && attendance >= 90)
            {
                percentage = percentage + 5;
                if (percentage > 100)
                    percentage = 100; // cap to 100%
            }

            if (percentage >= 90)
            {
                printf("Final Grade: A+\n");
                printf("Remarks: Excellent\n");
            }
            else
            {
                if (percentage >= 80)
                {
                    printf("Final Grade: A\n");
                    printf("Remarks: Very Good\n");
                }
                else
                {
                    if (percentage >= 70)
                    {
                        printf("Final Grade: B\n");
                        printf("Remarks: Good\n");
                    }
                    else
                    {
                        if (percentage >= 60)
                        {
                            printf("Final Grade: C\n");
                            printf("Remarks: Average\n");
                        }
                        else
                        {
                            if (percentage >= 50)
                            {
                                printf("Final Grade: D\n");
                                printf("Remarks: Pass\n");
                            }
                            else
                            {
                                printf("Final Grade: F\n");
                                printf("Remarks: Fail\n");
                            }
                        }
                    }
                }
            }
        }
    }

    return 0;
}
