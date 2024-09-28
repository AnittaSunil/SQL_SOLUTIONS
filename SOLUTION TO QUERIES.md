
SELECT AVG(grade) AS avg_grade FROM Enrollments;
![SQL 2 1](https://github.com/user-attachments/assets/aa2f973a-ad45-4272-9c09-32a5d8a09abb)



SELECT s.name, c.course_name FROM Students s JOIN Enrollments e ON s.student_id = e.student_id JOIN Courses c ON e.course_id = c.course_id;
![SQL 2 2](https://github.com/user-attachments/assets/26784d9f-d3e2-4577-b06f-e83c9ea9ac2e)



SELECT grade_level, COUNT(*) AS student_count FROM Students GROUP BY grade_level;
![SQL 2 3](https://github.com/user-attachments/assets/9876b824-4dc5-4e4d-b862-170e5924c000)


SELECT c.course_name, MAX(e.grade) AS max_grade FROM Enrollments e JOIN Courses c ON e.course_id = c.course_id GROUP BY c.course_name;
![SQL 2 4](https://github.com/user-attachments/assets/4a97ac17-1c71-4587-b829-c6477d000d6b)



SELECT AVG(e.grade) AS avg_grade FROM Enrollments e JOIN Students s ON e.student_id = s.student_id WHERE s.grade_level = 3;
![SQL 2 5](https://github.com/user-attachments/assets/4c6d916f-2e34-44d2-90d5-e57953e857fe)



SELECT s.name, c.course_name, c.credits FROM Students s JOIN Enrollments e ON s.student_id = e.student_id JOIN Courses c ON e.course_id = c.course_id;
![SQL 2 6](https://github.com/user-attachments/assets/9f22e094-27e6-46e8-af92-cd6a3850b53f)



SELECT c.course_name, AVG(e.grade) AS avg_grade FROM Enrollments e JOIN Courses c ON e.course_id = c.course_id GROUP BY c.course_name HAVING AVG(e.grade) > 3.0;
![SQL 2 7](https://github.com/user-attachments/assets/d5b7103b-d4f8-4ea5-9601-8cdb58249c29)



SELECT DISTINCT s.name FROM Students s WHERE NOT EXISTS ( SELECT 1 FROM Enrollments e WHERE e.student_id = s.student_id AND e.grade = 4.0

);
![SQL 2 8](https://github.com/user-attachments/assets/647ba38c-10b0-4f5e-9027-ac8fda5506cb)



SELECT s.name FROM Students s JOIN Enrollments e ON s.student_id = e.student_id GROUP BY s.name HAVING AVG(e.grade) > (SELECT AVG(grade) FROM Enrollments);
![SQL 2 9](https://github.com/user-attachments/assets/f39cb02b-8509-4083-9802-183e3f9b37f4)



SELECT s.name, COUNT(e.course_id) AS total_courses, AVG(e.grade) AS avg_grade FROM Students s JOIN Enrollments e ON s.student_id = e.student_id GROUP BY s.name;
![SQL 2 10](https://github.com/user-attachments/assets/3d854837-1f0e-4c49-8669-b04319f1f149)

