# #6 Tutorial details student
Code shown and explained in teachings   

<img src="/img/details.png" width="600px" />

### Code added to the controller
````java 
  ArrayList<Student> students = new ArraList<>();
  
  @GetMapping("/details")
  public String details(@RequestParam("id") int id, Model model) {
        model.addAttribute("stu", students.get(id));
        return "details";
  }
````   
### create.html
````java    
    <h1>Details</h1>
    <p th:text="'ID: ' + ${student.studentId}"/>
    <p th:text="'First Name: ' + ${student.firstName}"/>
    <p th:text="'LastName: ' + ${student.lastName}"/>
    <p th:text="'Enrollment Date: ' + ${student.enrollmentDate}"/>
    <p th:text="'CPR: ' + ${student.cpr}"/>

    <h2 th:text="'Enrollments for ' + ${student.firstName} + ' ' + ${student.lastName}"></h2>
    <p>The content here will come later</p>
```` 
_<div align="right">&copy; clbo@kea.dk</div>_
