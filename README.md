# Digital-Attendance-Tracker
OCR-based smart attendance management system using Zoho Creator and microservices architecture

**1. Problem Statement**

In many schools and colleges, attendance is still recorded manually using registers which leads to several problems such as human errors, incorrect calculations of percentages, time consumption and difficulty in maintaining historical records. A Digital Attendance Tracker solves these problems by automating attendance recording and calculating percentages. It reduces errors, saves classroom time and improves transparency for students and faculty.

Application Link: [Digital-Attendance-Tracker](https://digital-attendance-tracker-tanyashree2410477ssn.zohocreatorportal.in)

Github Link : https://github.com/Tanyashree-M/Digital-Attendance-Tracker

**2. Forms Used**

**2.1 Students**

The Students form stores the data of all students. It acts as the primary reference table for attendance tracking. All attendance records are linked to this form using the unique Register Number. This ensures data consistency and prevents duplication of student information across the system.

**2.2 Staff**

The Staff form maintains records of teaching staff and faculty details. It is used to assign courses and track attendance sessions conducted by each faculty member.

**2.3 Courses**

The Courses form stores details of all subjects offered by the institution. It is used in timetable scheduling and attendance tracking. Each course is linked to a specific department, year and semester.

**2.4 Staff-Course Mapping**

The Staff–Course Mapping form establishes a relationship between staff members and the courses they teach. This ensures that only assigned faculty members can conduct attendance sessions for their subjects. This form helps maintain academic responsibility and avoids unauthorized attendance marking.

**2.5 Timetable**

The Timetable form defines the weekly schedule for each class. It maps the class, course, staff, day, and period together.

**2.6 Attendance Entry**

The Attendance Entry form records individual student attendance for each session. It is integrated with OCR technology to automatically extract the register number from a student ID card image and mark attendance.

**3. Workflows Used**

**3.1 Auto populate course details**

The Auto-Populate Course Details workflow is to fill course information like Course Name, Department, Year and Semester from the Courses form automatically when a Course Code is selected in the form. This eliminates manual data entry, reduces errors and ensures data consistency across the system.

**Deluge Script**

if(input.Course_Code != null)
{
	input.Course_Name = input.Course_Code.Course_Name;
	input.Department = input.Course_Code.Department;
	input.Year_field = input.Course_Code.Year_field;
	input.Semester = input.Course_Code.Semester;
}

**4. Microservices Used**

**4.1 ID Card OCR**

The ID Card OCR (Optical Character Recognition) microservice is used to automatically extract the student register number from an uploaded ID card image. This microservice enables automated attendance marking without manual data entry.

The primary purpose of the ID Card OCR microservice is to

  * Eliminate manual attendance entry
  
  * Reduce human errors
  
  * Improve attendance marking speed
  
  * Automate student identification

**5. Dashboard**
  
  * Attendance Report
  
  * Attendance Bar Chart
  
  * Student Attendance Status
