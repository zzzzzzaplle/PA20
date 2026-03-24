// ==version1==
```
class AcademicProgram {
  - List<Course> courses

  //key operations
  + int sumClassroomCapacity()
  + double calculateAverageGrade(String courseCode)
  + int countCoursesOnSpecialDay(String day)

  //getter,setter
  + List<Course> getCourses()
}

class Course {
  - String name
  - String code
  - Date startTime
  - Date endTime
  - List<String> courseDays
  - integer quota
  - integer weeklyHours
  - Classroom classroom
  - List<Enrollment> enrollments

  //key operations
  + void increaseQuotaBy(int amount)
  + void decreaseQuotaBy(int amount)
  + void changeWeeklyHours(int newHours)
  + void changeCourseDays(List<String> newDays)

  //getter,setter
  + String getName()
  + void setName(String name)
  + String getCode()
  + void setCode(String code)
  + Date getStartTime()
  + void setStartTime(Date startTime)
  + Date getEndTime()
  + void setEndTime(Date endTime)
  + String[] getCourseDays()
  + integer getQuota()
  + void setQuota(integer quota)
  + integer getWeeklyHours()
  + void setWeeklyHours(integer weeklyHours)
  + Classroom getClassroom()
  + void setClassroom(Classroom classroom)
  + List<Enrollment> getEnrollments()
}

AcademicProgram *-- "*" Course : courses

class Classroom {
  - String id
  - integer capacity
  - String floor
  - String block

  //getter,setter
  + String getId()
  + void setId(String id)
  + integer getCapacity()
  + void setCapacity(integer capacity)
  + String getFloor()
  + void setFloor(String floor)
  + String getBlock()
  + void setBlock(String block)
}

class Instructor {
  - String name
  - String surname
  - String title
  - String specialty
  - List<Course> courses
  
  //key operations
  + int calculateTotalEnrolledStudents()
  + int calculateRemainingQuota()

  //getter,setter
  + String getName()
  + void setName(String name)
  + String getSurname()
  + void setSurname(String surname)
  + String getTitle()
  + void setTitle(String title)
  + String getSpecialty()
  + void setSpecialty(String specialty)
  + List<Course> getCourses()
}

Course --> "1" Classroom : room
Instructor --> "*" Course : courses

class Student {
  - List<Enrollment> enrollments

  //key operations
  + void enrollInCourse(Course course)
  + void dropCourse(Course course)

  //getter,setter
  + List<Enrollment> getEnrollments()
}

class Enrollment {
  - double grade
  - Student student
  - Course course

  //getter,setter
  + double getGrade()
  + void setGrade(double grade)
  + Student getStudent()
  + void setStudent(Student student)
  + Course getCourse()
  + void setCourse(Course course)
}
Enrollment "0..*" -- "1" Student : student
Enrollment -- "1" Course : course
```
// ==end==
