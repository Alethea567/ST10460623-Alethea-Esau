# ST10460623-Alethea-Esau
Step Tracker App – Purpose and Explanation
Purpose of the App
The Step Tracker App is designed to help students monitor their daily physical activity by tracking the number of steps taken each day over a week. Given the busy student life filled with lectures, study sessions, and social activities, maintaining an active lifestyle is crucial for health and well-being. This app serves as a reliable companion, allowing students to keep track of their steps in an engaging and structured way.

The app provides:
A weekly summary of steps taken each day
A detailed breakdown of morning and afternoon steps
A way to identify trends and determine which day had the highest activity
An average step count calculation to track fitness progress

Explanation of the App Functionality
The app consists of three key screens that provide an intuitive and user-friendly experience:

1️Splash Screen (Introduction Screen)
Purpose: Serves as the entry point of the app.
Features:
Displays the app’s name, the developer's (student’s) name, and student number.
Shows a simple app logo for branding.
Automatically navigates to the Main Screen after a few seconds.
Think of this as the welcome page of the app!

2️ Main Screen (Weekly Step Summary)
Purpose: Displays the steps taken over the week and provides an option to view detailed information.
Features:
A list view showing steps recorded for each day from Monday to Sunday.
Uses parallel arrays to store and manage step data efficiently.
A button that navigates to the Detailed View Screen for more in-depth analysis.
This acts as the dashboard where students can quickly check their weekly step count!

3️ Detailed View Screen (Daily Breakdown)
Purpose: Provides a detailed breakdown of steps taken in the morning and afternoon for each day.
Features:
Displays the morning and afternoon steps separately for better analysis.
A button to determine and display the day with the highest number of steps.
Calculates and displays the average step count for the week.
Allows users to navigate back to the main screen for a summary view.
This is useful for students who want to analyze their daily habits and improve their fitness!
Why This App is Useful for Students
Encourages daily movement and a healthier lifestyle
Helps students identify patterns in their physical activity
Provides motivation to increase step count over time
Easy to use, with simple navigation between screens

This app makes fitness tracking fun and effortless for students, integrating it into their daily routines without extra effort.

Pseudocode
First Screen
BEGIN SplashScreen
    DISPLAY App Logo
    DISPLAY "Step Tracker"
    DISPLAY "Student Name: [Your Name]"
    DISPLAY "Student Number: [Your Student Number]"

    WAIT 3 seconds
    NAVIGATE to MainScreen
END SplashScreen

Second Screen
BEGIN MainScreen
    DECLARE daysOfWeek = ["Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday", "Sunday"]
    DECLARE stepsData = [5000, 7000, 6000, 8000, 7500, 9000, 10000]  // Example data

    DISPLAY "Weekly Steps Summary"

    FOR i = 0 to 6 DO
        DISPLAY daysOfWeek[i] + " : " + stepsData[i] + " steps"
    END FOR

    BUTTON "View Details" CLICKED
        NAVIGATE to DetailScreen with stepsData
END MainScreen

Third Screen
BEGIN DetailScreen (stepsData)
    DECLARE morningSteps = [2000, 3000, 2500, 3500, 3200, 4000, 4500]
    DECLARE afternoonSteps = [3000, 4000, 3500, 4500, 4300, 5000, 5500]
    DECLARE totalSteps = []

    FOR i = 0 to 6 DO
        totalSteps[i] = morningSteps[i] + afternoonSteps[i]
    END FOR

    DISPLAY "Daily Breakdown"

    FOR i = 0 to 6 DO
        DISPLAY daysOfWeek[i] + " - Morning: " + morningSteps[i] + ", Afternoon: " + afternoonSteps[i]
    END FOR

    DECLARE highestSteps = 0
    DECLARE highestDay = ""

    FOR i = 0 to 6 DO
        IF totalSteps[i] > highestSteps THEN
            highestSteps = totalSteps[i]
            highestDay = daysOfWeek[i]
        END IF
    END FOR

    BUTTON "Show Highest Day" CLICKED
        DISPLAY "Highest Steps Recorded on: " + highestDay + " with " + highestSteps + " steps"

    CALCULATE averageSteps = SUM(totalSteps) / 7
    DISPLAY "Average Steps per Day: " + averageSteps

    BUTTON "Back to Main" CLICKED
        NAVIGATE to MainScreen
END DetailScreen


