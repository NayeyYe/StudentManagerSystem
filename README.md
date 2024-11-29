## 复杂版学生管理系统：Java OOP 综合实践

**项目目标：**

- 深入理解并应用面向对象编程（OOP）的高级概念，例如继承、多态、封装、抽象、接口、内部类、包装类、设计模式、异常处理和多线程。
- 设计和实现一个功能更丰富、结构更复杂的Java应用程序。

**项目描述：**

开发一个功能更全面的学生管理系统，除了基本的学生信息管理外，还包括课程管理、成绩管理、用户权限管理等功能。系统应支持多用户同时操作，并具备良好的异常处理机制。

**项目结构：**

复制

```
AdvancedStudentManagementSystem/
├── src/
│   ├── Main.java
│   ├── model/
│   │   ├── Student.java
│   │   ├── Course.java
│   │   ├── Grade.java
│   │   ├── User.java
│   │   ├── Admin.java
│   │   ├── Teacher.java
│   │   └── StudentUser.java
│   ├── manager/
│   │   ├── StudentManager.java
│   │   ├── CourseManager.java
│   │   ├── GradeManager.java
│   │   └── UserManager.java
│   ├── ui/
│   │   └── UserInterface.java
│   ├── utils/
│   │   ├── FileHandler.java
│   │   └── Validator.java
│   ├── exceptions/
│   │   ├── StudentNotFoundException.java
│   │   └── InvalidInputException.java
│   ├── threads/
│   │   └── ConcurrentAccessManager.java
│   ├── patterns/
│   │   └── Singleton.java
│   └── interfaces/
│       └── Manageable.java
└── README.md
```

**类设计：**

- **model 包:**
  - **Student.java:** 表示一个学生对象，包含以下属性：
    - `String name` (姓名)
    - `String id` (学号)
    - `int age` (年龄)
    - `String gender` (性别)
    - `String className` (班级)
    - `List<Grade> grades` (成绩列表)
  - **Course.java:** 表示一个课程对象，包含以下属性：
    - `String courseId` (课程编号)
    - `String courseName` (课程名称)
    - `Teacher teacher` (授课教师)
  - **Grade.java:** 表示一个成绩对象，包含以下属性：
    - `Course course` (课程)
    - `Student student` (学生)
    - `double score` (分数)
  - **User.java:** 表示一个用户对象，包含以下属性：
    - `String username` (用户名)
    - `String password` (密码)
    - `String role` (角色)
  - **Admin.java:** 继承自 `User`，表示管理员用户。
  - **Teacher.java:** 继承自 `User`，表示教师用户。
  - **StudentUser.java:** 继承自 `User`，表示学生用户。
- **manager 包:**
  - **StudentManager.java:** 负责管理学生对象的集合，并提供以下方法：
    - `void addStudent(Student student)` (添加学生)
    - `List<Student> getAllStudents()` (获取所有学生)
    - `Student findStudentById(String id)` (根据学号查找学生)
    - `Student findStudentByName(String name)` (根据姓名查找学生)
    - `void updateStudent(Student student)` (更新学生信息)
    - `void deleteStudent(String id)` (删除学生)
  - **CourseManager.java:** 负责管理课程对象的集合，并提供以下方法：
    - `void addCourse(Course course)` (添加课程)
    - `List<Course> getAllCourses()` (获取所有课程)
    - `Course findCourseById(String id)` (根据课程编号查找课程)
    - `void updateCourse(Course course)` (更新课程信息)
    - `void deleteCourse(String id)` (删除课程)
  - **GradeManager.java:** 负责管理成绩对象的集合，并提供以下方法：
    - `void addGrade(Grade grade)` (添加成绩)
    - `List<Grade> getGradesByStudent(Student student)` (获取学生的所有成绩)
    - `List<Grade> getGradesByCourse(Course course)` (获取课程的所有成绩)
    - `void updateGrade(Grade grade)` (更新成绩)
    - `void deleteGrade(Grade grade)` (删除成绩)
  - **UserManager.java:** 负责管理用户对象的集合，并提供以下方法：
    - `void addUser(User user)` (添加用户)
    - `List<User> getAllUsers()` (获取所有用户)
    - `User findUserByUsername(String username)` (根据用户名查找用户)
    - `void updateUser(User user)` (更新用户信息)
    - `void deleteUser(String username)` (删除用户)
- **ui 包:**
  - **UserInterface.java:** 负责与用户交互，提供以下功能：
    - 显示主菜单
    - 获取用户输入
    - 调用 `StudentManager`、`CourseManager`、`GradeManager` 和 `UserManager` 类的方法来执行用户请求的操作
- **utils 包:**
  - **FileHandler.java:** 负责读取和写入文件，用于持久化数据。
  - **Validator.java:** 负责验证用户输入，例如检查学号是否唯一，分数是否在合理范围内等。
- **exceptions 包:**
  - **StudentNotFoundException.java:** 自定义异常类，表示未找到学生。
  - **InvalidInputException.java:** 自定义异常类，表示输入无效。
- **threads 包:**
  - **ConcurrentAccessManager.java:** 负责管理多线程访问，确保数据一致性。
- **patterns 包:**
  - **Singleton.java:** 使用单例模式确保 `StudentManager`、`CourseManager`、`GradeManager` 和 `UserManager` 类的实例唯一。
- **interfaces 包:**
  - **Manageable.java:** 定义一个接口，包含 `add`、`getAll`、`findById`、`update` 和 `delete` 方法，供 `StudentManager`、`CourseManager`、`GradeManager` 和 `UserManager` 类实现。

**扩展功能：**

- 使用图形用户界面 (GUI) 代替命令行界面。
- 使用数据库代替文件存储数据。
- 实现更复杂的设计模式，例如观察者模式、策略模式等。

**学习资源：**

- [Oracle Java 官方文档](https://docs.oracle.com/en/java/)
- [Head First Design Patterns](https://www.oreilly.com/library/view/head-first-design/9781492077992/)
- [Java Concurrency in Practice](https://www.oreilly.com/library/view/java-concurrency-in/9780134000892/)

**提示：**

- 使用 `ArrayList` 或 `LinkedList` 来存储对象。
- 使用 `Scanner` 类从控制台读取用户输入。
- 使用 `System.out.println()` 方法向控制台输出信息。
- 使用 `try-catch` 块处理异常。
- 使用 `synchronized` 关键字或 `ReentrantLock` 类实现线程安全。

这个项目可以帮助你深入理解并应用 Java OOP 的高级概念，并设计和实现一个功能更丰富、结构更复杂的 Java 应用程序。你可以根据自己的兴趣和学习进度添加更多功能。