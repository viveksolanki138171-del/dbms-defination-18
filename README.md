Definition 1:
Write a PL/SQL block to accept student name from a user if it is exist
display his/her result from RESULT table otherwise display appropriate
message using exception handling.
set serveroutput on; declare cursor
a1 is select * from student2; d
student2%rowtype; begin open a1;
loop fetch a1 into d; exit
when a1%notfound;

dbms_output.put_line('rollno:' || d.rlno ||' grno:' || d.grno ||
' name:' || d.name ||' stream:' || d.stream); end
loop; close a1; exception when invalid_cursor then
dbms_output.put_line('cursor is not opened properly'); end;
/
