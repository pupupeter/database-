
# ASSIGNMENT VIDEO LINK

ASSIGNMENT 1.https://youtu.be/xDBu5-UiPog



















# database-
for the course

2024-09-09 flask and Mysql use

https://github.com/pupupeter/database-/blob/main/databaseuse.ipynb

you have to establish with a file that flask can be executed
e.g:https://github.com/pupupeter/database-/tree/main/templates 
inside, there is a html code that you should  establish with. you may use chatgpt to help you get the html code
# flask environment example
https://github.com/pupupeter/database-/blob/main/123.ipynb 

#Mysql use
1. search Mysql
https://dev.mysql.com/downloads/installer/
2. enroll it
3. Execute it
4. ![image](https://github.com/user-attachments/assets/b0959fe7-4d94-4aff-b1a8-1e451642a1b6)
5. give
   GRANT ALL PRIVILEGES ON sys.* TO 'username(your name?)'@'localhost';
FLUSH PRIVILEGES;
find sakila and click 2times, and click the data that you want(e.g:![image](https://github.com/user-attachments/assets/95c06f60-f332-437c-8263-4ce2419b154f)) i choose actor
6.click this ![image](https://github.com/user-attachments/assets/a7fdfb97-8506-4f17-addd-3d350618a605)
7. the result![image](https://github.com/user-attachments/assets/5be02687-2ad7-497b-a2a5-3fe654721530)
8. choose the flask or other to conbine with MySql

# 0916 set up the table of sql
![image](https://github.com/user-attachments/assets/e878af84-e746-49a5-b960-2f79a62399ea)
e.g.  address item
![image](https://github.com/user-attachments/assets/a25a6a84-176b-4837-b96b-dd3ae17c4b71)
check the item 

task: ![image](https://github.com/user-attachments/assets/60a6f57a-17ef-4033-acb2-96a044545f84)
add a new data in the table

solution:by using flask+mysql code
https://github.com/pupupeter/database-/blob/main/20240916databasepratice.ipynb

after executing it, you would see this ,and you can input what you want 
![image](https://github.com/user-attachments/assets/f7652939-8290-47a9-b2bf-71e1caf31295)
and you would see the new data in the html 
![image](https://github.com/user-attachments/assets/13f3021d-daef-442a-8573-4dd2b5570b33)

if you find the record in sql 
![image](https://github.com/user-attachments/assets/50aa3b7a-6192-4e95-8c8e-cbf93d90f694)
you could see this,too 

download at you desktop

![image](https://github.com/user-attachments/assets/8367da37-a2c8-4587-814c-3abaeb5baa01)
![image](https://github.com/user-attachments/assets/4f674f41-f534-46bd-b028-b2e71773331a)

choose export data

![image](https://github.com/user-attachments/assets/431ffb13-affe-47d3-b6d1-778cd5eea967)

1.choose the schema you want
2.choose your schema objects 
3.all the item of objects to export should be clicked
4.![image](https://github.com/user-attachments/assets/027a17f7-5c54-4b33-8f2c-ac64b2edd7f3)
choose the folder you want to store

![image](https://github.com/user-attachments/assets/3d90d94a-1345-4c17-986a-3a8398865bc8)
after that, you can find the file you successfully set up 
![image](https://github.com/user-attachments/assets/913cd971-556e-41a6-8949-c53a9606c7c9)
done 

# 0923 add and read new data
code: https://github.com/pupupeter/database-/blob/main/0923practice.ipynb
html: https://github.com/pupupeter/database-/blob/main/index1.html

change: 
1.The application uses session to track the last_seen_timestamp. This allows the system to remember when the user last viewed the data and only display records that were added after that time.


2.The query only selects addresses added after the last_seen_timestamp, and the results are sorted in descending order based on the last_update timestamp.
  
  the query:
  ***
  SELECT address, address2, district, city_id, postal_code, phone, last_update
FROM address
WHERE last_update > %s
ORDER BY last_update DESC


***

3. A secret_key is set, which is required for enabling session functionality and helps prevent Cross-Site Request Forgery (CSRF) attacks.

4. When inserting records, the last_update field is set to the current time, and it is also retrieved during queries to track the most recent updates.

if you want to check  thoroughly,  directly click the  link  of the code and html at 0923


# 0930 delete the data and the create new data

html: https://github.com/pupupeter/database-/blob/main/index2.html
code:https://github.com/pupupeter/database-/blob/main/delete%2Bread.ipynb

* What I have changed:
  1.i add a delete button to help me delete unnecessary data in order to choose what i need
  2.i add a bluerint -->delete_bp = Blueprint('delete_bp', __name__) , because last week i did not use the code, so in order to use properly, i add this.
  3. maybe i didn,t enroll the blueprint.consequently i set  app.register_blueprint(delete_bp) up at the same time
  4. i combine with delete and create so as to make my functions complete.
