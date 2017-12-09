# 06_tutorial_details_student
Code shown and explained in teachings    
### Code added to the controller
````java 
  ArrayList<Student> students = new ArraList<>();
  
  @GetMapping("/create")
  public   String   create(Model   model)   {
         model.addAttribute("student",   new   Student());  
         return   "create";
  }           
  
  @PostMapping("/create")
  public String create(@ModelAttribute Student student)   {
         String   index   =   Integer.toString(students.size() + 1);          
         student.setStudentId(index);
         students.add(student);
         return   "redirect:/";
  }

````   
### create.html
````java    
  <form method="Post" th:action="@{/create}">         
         <input   type="text"   th:field="${student.firstName}"   />
         <input   type="text"   th:field="${student.lastName}"/>
         <input   type="date"   th:field="${student.enrollmentDate}"/>
         <input   type="text"   th:field="${student.cpr}"/>          
         <input   type="submit"   value="Send"   />
  </form>
```` 
### Student.java
````java    
//The annotation is needed for input field on html pages (in order to serve the right format)

@DateTimeFormat(pattern = "yyyy-MM-dd") 
private Date enrollmentDate;

```` 
