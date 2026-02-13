# Leadership Analytics Release Notes

##  2026.2.6
This month's release will include backend and user experience improvements across Podium dashboards. Some of the updates improve data accuracy and consistency (including incident identification, student counts, and suppression logic), expand cross-district visibility through enhanced filtering, and refine dashboard usability with clearer filters and corrected table layouts. Documentation has also been updated to reflect the support portal and updated training documentation.

Improvements
- Users can now see a currently enrolled student's cross-school within-district assessment history in the Student Profile dashboard, which will allow them to get a deeper understanding of prior assessment performance.
- The Course Grades Snapshot now has separate filters for Grading Period and Grade Type.
- Users with access to multiple districts can now view district information in the School table across all dashboards
- Counts of students by subgroup in the Profile dashboard has been updated to count unique student - district associations.
- An update has been made to ensure Incident IDs are uniquely counted by school rather than district. This may cause small changes in incident ID numbers that better reflect the number of incidents.
- Suppression of district metrics was altered to suppress results if the total number of students included across selections <20 rather than suppressing if one district in the selection had <20 students.
- The instruction page on Accessing and Navigating Podium has been updated to include the new Portal login for Podium.

Bugs and other fixes
- A bug that showed the order of columns as incorrect on the Enrollment Dashboard has been fixed to show the corrected order.
- Updated charts to reference grade level indicator in Profile and Section Profile. This was not a bug impacting any current implementations.

## Release version: 2026.1.8
The January release for Podium includes several dashboard enhancements that were completed to improve performance, scalability, and usability. Updates include more sustainable data models, expanded access to state-level growth results, improved filtering and table views, clearer chart labeling, alignment of dashboard layouts and color mappings, increased data capacity for large districts, and added context in student assessment views.

Improvements
- Profile Dashboard: Users with access to multiple districts can now view district information in the Summary table when multiple districts are selected 
- Some chart labels have been updated to ensure consistency across dashboards. Chart labels ask a questions, which the chart answers. 
- Section Information tables in the Section Profile dashboard have had row limits increased to 100,000 to account for larger districts. 
- District Metrics in the Assessment and Behavior Dashboards have been updated, allowing for main metrics to come first. 
- Models for the Behavior, Course, and Enrollment dashboards were completed to increase model performance and sustainability. 
- The WI Forward exam has updated color mapping to align to performance levels.

Advanced Add-ons
- State level growth results will now load through district warehouses. Users in a state with District dashboard access will now be able to view Growth results from the state. 
- Legends have been added to identify student group charts in the Growth dashboard when charts are downloaded, or the chart is shown in full-screen format. 

Bugs and other fixes
- A bug in the Growth dashboard interrupted filters after the "Lowest Performing 20% of Students" was selected in the "Select Growth Metric" filter. This issue has been resolved to ensure uninterrupted filter selection functionality for users.
- The Student Profile Assessment table has had subject and grade columns added to make a more stable view for users.

## Release version: 2025.12.04
The December 2025 Leadership Analytics release includes new filters for Gifted & Talented and Homeless student groups, enabled multi-district users to select multiple LEAs, and improved error pages for clearer troubleshooting. The Assessment Dashboard now features updates to performance distribution and refined performance colors. Enrollment Status filtering is now more intuitive, and backend model updates improve overall performance. We also introduced the new Predictions and Targets Dashboard and resolved several issues, including API credential stability, behavior chart errors, and table ordering in downloads.

Improvements
- Filters for Gifted and Talented Status and Homeless Status were added to all dashboards to allow exploration of metrics by these student groups. 
- Users who have access to data from multiple districts will be able to select more than one district in the Select LEA filter in order to see a holistic picture across districts. This feature will not be added to the Student or Section Profile dashboards. 
- Error pages have been updated when a user encounters an error on the dashboard to provide more information on troubleshooting 
- The assessment dashboard now has a chart that shows performance levels distributed across selected schools. This is used to understand student performance across schools or districts.
- Enrollment Status Filter has been updated to default to "Enrolled" if there are enrolled students and "Not Enrolled" when there are no enrolled students 
- Models for demographics and student groups were refactored in order to increase model performance and sustainability. 

Bugs and other fixes:
- API credentials have been updated to service email credentials to ensure more stable application usage. 
- Fixed a bug in the section profile dashboard that was causing the behavior charts to error for some users. 
- A bug that caused an error in table order when downloaded from the Student Detail section of the Assessment and Course Grades dashboards has been fixed. 


## 5.0.0 - 08/20/2025

This release introduces several enhancements aimed at improving usability and providing more detail across the Leadership Analytics platform. Improvements were also made to the Assessment dashboard to enable multi-season selection and update the order of assessment seasons to chronological order (Fall, Winter, Spring). Additionally, LA added discipline rate metrics and the number of incidents to the Behavior Dashboard, enhanced the Course Grade Dashboards with course and teacher information, implemented grade level ordering for clearer data organization, and loosened the required numeric grade filter to improve flexibility in grade reporting. Finally, LA improved the Section Profile dashboard to match the unique section definition across dashboards. A set of minor user feedback based improvements across dashboards. Please see the "Improvements" and "Bug Fixes" sections for a more detailed list.

Breaking changes:

- All dashboards:
  - Added grade to the list of student groups that can have flexibility with the backing variable in order to enable ordering. This will cause a break if the dashboards are update before edu_ext_podium
  - Added gender and race to the list of student groups that can have flexibility with the backing variable at a partner level
- Behavior Dashboard:
  - Added count of incidents to dashboard which relies on an edu and edu_ext_podium update. This will cause a break if the dashboards are updated before edu and edu_ext_podium

New Features:

- The Enrollment dashboard now has an "enrollment type" filter. This allows users to select one or more enrollment types.

Improvements:

- All Dashboards:
 - School year will now be displayed as academic year (e.g., 2024-25). This is configurable by implementation.
 - Grade levels now can be ordered across all dashboards
 - Student tables now use a new interactive table format with improved filtering, sorting, and ordering capabilities.
- Behavior Dashboard:
 - Added a metric to display discipline rate (number of students with a discipline action out of the total number of students overall).
 - Added the number of incidents to the Behavior dashboard, this includes: Number of incidents in school table, student table, and as a district metric
 - Over time chart now just displays number of discipline actions per day for clarity
 - Distribution of behavior and actions charts now displays Top 15 most frequent items for clarity
 - In Student Table, replaced Yes/No with number of In-School Suspensions and Out-of-School Suspensions for each student

- Section Profile & Course:
  - Improved resilience of the Section Profile dashboard by matching Section definition with Ed-Fi definition ( Section ID, Local Course Code, Session Name)

- Course Grade Dashboards:
  - Course Grades Snapshot no longer requires a numeric grade. Users can now select either a range of numeric grades or letter grades.
  - Users can now filter to specific courses by course information, local course information, or teachers.
  - Also added the new section definition to the filter in the Course Grades dashboards

- Enrollment Dashboard:
  - Add enrolled grade to the Student Table alongside the most recent enrolled grade

- Assessment:
  - Student Detail: Fixed a bug that caused the Select Student filter to be NULL

- Average Daily Attendance:
  - Add percentages to the tooltip of the Attendance Category Over Time chart to allow users to better understand the breakdown of the attendance categories at a point in time and over time.

- Assessment Dashboard:
  - Enablement of multi-season selection for educators to analyze the trends across multiple seasons of tests, for example, ACT and SAT. Order of Assessment Seasons in the dashboards was updated to follow the chronological order of Fall, Winter, Spring.

- Dashboard Descriptions:
  - Descriptions now include a date for the last time the description itself was updated

Infrastructural changes:

- Introduced a feature to the CLI Tool that allows implementations to swap the language used for student groups/programs

Bug Fixes:

- A bug that duplicated courses in the BI model originated in Stadium. This was fixed, but we are still tracking duplicates caused by co-teaching. We will aim to address that issue in the October release.

## 4.0.9 - 05/22/2025

This release incorporates a number of minor visual enhancements to the LA dashboard. Please review the “Improvements” section for a more detailed list.

Breaking changes: None in this release

New Features (if any): None in this release

Improvements:

- Search in filter values will now search across all values.
- Assessment dashboard tables will now reflect custom assessment labels
- Rename “School Year” to “Assessment Year” in Student Profile Assessment chart
- Assessment dashboards can now display assessments that have overall performance levels, but no scale score
- A variety of small visual enhancements:
  - Severity of attendance categories and/or category of chronic absenteeism indicated by stoplight color scheme.
  - Improved consistency of color palette across student group charts
  - Clarified language of most recent date across dashboards (With the exception of Section Profile)
  - Uppercase titles on all section separators.
  - Added separator in Profile dashboard below School table
- Updates to Chronic Absenteeism and Attendance dashboards:
  - Added Absence Percentages to Student and School (ADA only) tables
  - Changed metric name in School table from “Number of Students” to “Total Number of Students”
  - Updated chart descriptions for Attendance and Chronic Absenteeism to clarify data availability by selected date
- Updates to Behavior dashboard:
  - Clarification of subtitle of number of students in the district metrics
  - Changed filter name from “Discipline Type” to “Discipline Action”
  - Updated “Discipline Rate” metric name to “Actions per Student”
  - Enhancements to the custom assessment label logic to allow for labels to be set at the assessment or assessment family level

Bug Fixes:

- Profile dashboard: Fix bug that restricted discipline data from surfacing in dashboard consistently
  
## 3.1 - 03/27/2025
This release includes a variety of front-end adjustments to enhance and standardize the user experience.
- Assessment: Student Detail redesign to clarify selected year assessments vs assessment history.
- Remove separators between tables in Section Profile and Assessment: Student Detail
- Add "Search" to all school and student tables
- Update Most Recent Date language to be more descriptive and consistent
- Standardize order of student group charts for yes/no variables.
- Sort attendance rate charts so that the best attendance group is at the top of the chart
- Add timeline navigator to time series charts

## 3.0 - 01/28/2025

This release includes updating the Exchange SDK to V2.3.1.

## 2.2.0 - 09/24/2024

This release introduces a new cross-year assessment feature to the Assessment: Student Detail.

- The Assessment: Student Detail dashboard now allows the user to look at a student's historical assessment results. The tables and filters have an Enrollment School Year and Asssessment School Year. The user can select the Enrollment School Year to see the historic (enrollment year and previous) test results for those students. They can filter to a specific Assessment School Year if they only want to see assessment results from one year. 

## 2.1.0 - 07/23/2024

This release includes minor features across all relevant dashboards.
- Added a student filter to all dashboards with a student table to allow users to select any group of students.
- Increased the row limit to the maximum for the student tables to allow users to see as many students as possible.
- Revised the district metric section to improve visibility of titles.
- Updated Enrollment Status filter values on Attendance and Behavior dashboards
  
## 2.0.0 - 06/11/2024

This release introduces three new dashboards and a significant re-work of three existing dashboards. 

- Section Profile: This is a new dashboard that offers a comprehensive overview of the academic performance and demographic characteristics of the students in each section and/or educator's classes.Users can explore detailed information about the students in each section or educator's classes, including student grades, daily attendance, overall discipline actions, and demographic data aggregated by section.

- Student Profile: This is a new dashboard that offers a comprehensive overview of individual students, providing valuable insights into their behaviors, academic performance, demographic characteristics, and other student attributes.
  
- Course Grades Snapshot: This dashboard is replacing the D/F Counts dashboard. This allows users more freedom to chose a grade cutoff and see all of the students to have at least one grade that meet that criteria instead of just D/Fs.

- Profile Grades Change: The Percentage of Students at least one Non-Passing Grade chart is now based on transcript data instead of the most recent grading period in the grades resource. It shows the percentage of students who have at least one non-passing grade on any of their courses on their transcript in the chosen year. Denominator is the unique number of students with a course grade on transcript. This is calculated at the district, school, and grade level.
  
- Assessment: Changes to the assessment dashboard include improving chart selection and color schemes to allow users to make more meaning from the dashboard. 
  
- Asessment Student Detail: This is a new dashboard that provides information about assessment results at the student-level. The dashboard allows users several ways to filter the data, like filtering to one or more assessments and test seasons at the same time, selecting a performance level or student characteristics. 

## 1.2.0 - 04/07/2024
- Profile Dashboard: Change to allow district metrics to flow to Profile dashboard without staff data populated in the warehouse
- Update Exchange SDK to 2.0.9

## 1.1.0 - 03/10/2024

- Removed future exit dates from enrollment dashboard withdraw counts
- Added subheaders to district charts in Attendance and Chronic Absenteeism dashboards
- Enhancements to dashboard descriptions

## 1.0.0 - 01/31/2024

This version introduced a Profile dashboard that allows district administrators and school leaders to explore summary metrics related to domains covered in the platform such as enrollment, attendance, behavior, and grades. 

##  Initial Release - 09/06/2023 

Leadership Analytics is an application that enables school and district leadership to explore their data and more easily answer questions about their students. This initial release contains six dashboards.

1. Average Daily Attendance
2. Chronic Absenteeism
3. Enrollment
4. Behavior
5. Course Grades: Ds and Fs
6. Assessment

Detailed information about the metrics and business rules for each of those dashboards can be found in the "About this Dashboard" modal to the right of the selected dashboard title.

Users can navigate to any of these dashboards from a left-side navigation bar that can be expanded to see dashboard names and minimized when exploring selected dashboards.

Within each dashboard, users have multiple ways to interact with visualizations.
* Filters: Each dashboard has a filter panel where users can select data by school(s), student groups, and other data. Filters are applied by clicking "Apply Filters" at the bottom of the filter panel. The filter panel can also be minimized while viewing the dashboard.
* Cross-Filters Users can also cross-filter the dashboard by clicking within visuals and selecting a group of interest. Multiple cross-filters can be applied within each dashboard.
* Hover-Over: Users can hover over any visual to see additional information.
* Visual Menu: If they choose, users can also download the underlying data of each visual by clicking on the three-dot menu in the top right of a chart and selecting download and the format of their choice. The three-dot menu also allows users to view specific visuals in full screen or see descriptions of charts.

Each dashboard contains the most recent date of data for the metric displayed and a table displaying which filters have been selected at the top of the page. A "key metrics" section that contains district aggregates and high-level information of interest for that metric is located at the top of each dashboard. In the middle of each dashboard, there is a student table allowing users to quickly identify students of interest. Finally, at the bottom of each dashboard, the key metric is displayed by various student groups.
