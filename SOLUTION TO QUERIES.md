
SELECT AVG(grade) AS avg_grade FROM Enrollments;
![370382188-67ed020d-56c3-4b38-8e39-510fb3175a9b](https://github.com/user-attachments/assets/513e946f-e4a8-4f2e-b6fb-b3cd0a0f6616)



SELECT s.name, c.course_name FROM Students s JOIN Enrollments e ON s.student_id = e.student_id JOIN Courses c ON e.course_id = c.course_id;
![370383293-32dd5d74-854d-48cb-8cd4-3bf89628e9cf](https://github.com/user-attachments/assets/3b0757ac-b913-4295-90bd-fd7b2d56de33)



SELECT grade_level, COUNT(*) AS student_count FROM Students GROUP BY grade_level;
![370384189-038900be-852f-42e9-9a37-e420fef8bc86](https://github.com/user-attachments/assets/1ddf89de-1867-4c9d-874f-b4883864769c)



SELECT c.course_name, MAX(e.grade) AS max_grade FROM Enrollments e JOIN Courses c ON e.course_id = c.course_id GROUP BY c.course_name;

![370384647-edc0663c-155a-4f7a-8380-ef5e2a642631](https://github.com/user-attachments/assets/7300103f-3df4-44a9-b0c2-cdabb06614d5)


SELECT AVG(e.grade) AS avg_grade FROM Enrollments e JOIN Students s ON e.student_id = s.student_id WHERE s.grade_level = 3;
![370384845-76a7e701-0bb6-4842-87e2-3652fa28a080](https://github.com/user-attachments/assets/eecac9cf-acdc-406e-8aab-ef07dbfdf782)



SELECT s.name, c.course_name, c.credits FROM Students s JOIN Enrollments e ON s.student_id = e.student_id JOIN Courses c ON e.course_id = c.course_id;
![370385834-9b312798-07a0-44b5-b5b4-e690258c8918](https://github.com/user-attachments/assets/72634a31-2712-4f13-9a62-2254953b79bf)



SELECT c.course_name, AVG(e.grade) AS avg_grade FROM Enrollments e JOIN Courses c ON e.course_id = c.course_id GROUP BY c.course_name HAVING AVG(e.grade) > 3.0;
![370386026-24cd5c6b-ce64-44a9-bd68-aeb3ac632863](https://github.com/user-attachments/assets/81ce1099-ccca-4722-b908-cef2bd447ada)



SELECT DISTINCT s.name FROM Students s WHERE NOT EXISTS ( SELECT 1 FROM Enrollments e WHERE e.student_id = s.student_id AND e.grade = 4.0

);
![370386698-0e0ab676-875f-4abf-bff2-47d7c561dd6a](https://github.com/user-attachments/assets/86632b6e-6763-4ef4-8317-80210ac1f3ce)



SELECT s.name FROM Students s JOIN Enrollments e ON s.student_id = e.student_id GROUP BY s.name HAVING AVG(e.grade) > (SELECT AVG(grade) FROM Enrollments);
![370386944-ea70a511-a7b7-497b-b735-9eaa569fbd5c](https://github.com/user-attachments/assets/f8494419-3215-4daf-8434-eff1c1e8f220)



SELECT s.name, COUNT(e.course_id) AS total_courses, AVG(e.grade) AS avg_grade FROM Students s JOIN Enrollments e ON s.student_id = e.student_id GROUP BY s.name;
![370387328-e9babd50-7e8c-426d-8232-b2472cddab87](https://github.com/user-attachments/assets/13a9506d-1f34-456c-816f-ba69d2066752)

