
# ASSIGNMENT VIDEO LINK

ASSIGNMENT 1.https://youtu.be/xDBu5-UiPog


ASSIGNMENT 2.https://www.youtube.com/watch?v=TIaSmoeB2qU

ASSIGNMENT 2 for  insufficient functions   https://youtu.be/GWJeo4uNd18

ASSIGNMENT 3 https://youtu.be/HzY07OpwZtg?si=eB495m7f2BazqnyH

ASSIGNMENT 4 https://youtu.be/4yx89M-krEY?si=wqtuuGPso3Ouc4ZH

# Final Project 


https://youtu.be/Oaso01xU7nA?si=_V-mpcOP_WtQy8z7



link: https://github.com/pupupeter/database-/tree/main/final%20project






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
  
  2.i add a blueprint -->delete_bp = Blueprint('delete_bp', __name__) , because last week i did not use the code, so in order to use properly, i add this.


  3. maybe i didn,t enroll the blueprint.consequently i set  app.register_blueprint(delete_bp) up at the same time


  4. i combine with delete and create so as to make my functions complete.

# 0930/1002 make the html beautiful

Use css's model to modify the html style 

you could choose the style you are favorite with. 



refer to https://github.com/marcelinechang/DatabaseSystem

if you are not stisfied with the style, you may get to the website 

https://www.free-css.com/free-css-templates

# 1007 add  "edit" and "search" and  function 

   1. """edit""
```   
   @update_bp.route('/update/<int:post_id>', methods=['POST'])
def update_post(post_id):
    # 获取所有字段的新值
    new_address = request.form.get(f'post_{post_id}_address')
    new_address2 = request.form.get(f'post_{post_id}_address2')
    new_district = request.form.get(f'post_{post_id}_district')
    new_city_id = request.form.get(f'post_{post_id}_city_id')
    new_postal_code = request.form.get(f'post_{post_id}_postal_code')
    new_phone = request.form.get(f'post_{post_id}_phone')

    # 检查是否有输入资料，没有的话返回错误
    if not new_address or not new_district or not new_city_id or not new_postal_code or not new_phone:
        return "所有字段都是必需的", 400  # 返回 400 错误，告知缺少必填字段

    # 连接到数据库并更新内容
    conn = mysql.connector.connect(**db_config)
    cursor = conn.cursor()

    update_query = """
        UPDATE address 
        SET address = %s, address2 = %s, district = %s, city_id = %s, postal_code = %s, phone = %s 
        WHERE address_id = %s
    """
    
    # 执行更新语句
    cursor.execute(update_query, (new_address, new_address2, new_district, new_city_id, new_postal_code, new_phone, post_id))
    conn.commit()  # 提交更改
    
    cursor.close()
    conn.close()
    
    # 更新完成后，重定向到主页
    return redirect(url_for('index'))


   app.register_blueprint(update_bp)
```
This is a way to show how I run the "update" function, you could change the code with AI's assistance.

The function shows that once i change the  value or name of every item and update it, it would change,too.

Remember , you should use """app.register_blueprint(update_bp)""" in order to run properly.



   2. """Search"""

```
   @app.route('/search', methods=['GET'])
def search_by_city():
    city_id = request.args.get('city_id')

    if not city_id:
        return "城市ID是必需的", 400  # 返回 400 错误，告知缺少城市 ID

    conn = mysql.connector.connect(**db_config)
    cursor = conn.cursor()

    search_query = """
        SELECT address_id, address, address2, district, city_id, postal_code, phone, last_update
        FROM address
        WHERE city_id = %s
    """
    cursor.execute(search_query, (city_id,))
    addresses = cursor.fetchall()

    cursor.close()
    conn.close()

    return render_template('index4.html', addresses=addresses)
 ```

This is a way to show how I run the "search" function, you could change the code with AI's assistance.

Only designd the city_id search fuction, if you want to modify other coulmn, remember to change the code """city_id """to what you want to represent.

 *0930/1002  I had change html's style, so it would be different to the last one. 


code:https://github.com/pupupeter/database-/blob/main/1007end.ipynb

html:https://github.com/pupupeter/database-/blob/main/index4%20.html

# 1014 final project data create+ inner join

***Remember ***


HTML:https://github.com/pupupeter/database-/blob/main/template1.html

CODE:https://github.com/pupupeter/database-/blob/main/1014.ipynb

I had established  new database and several tables, if you want to do the task,you should establish a new database. And set up new tables

I set up new data randomly in python.You could just establish the data in mysql or python.

If you use python, it can be sucessfully updated in the mysql.Rest assured! 

But in order to  play it for save , i suggest that you should check again





![image](https://github.com/user-attachments/assets/8427db2f-c4bc-43c5-ada1-c33c360a899e)
this is code for inner join 

![image](https://github.com/user-attachments/assets/78b18846-71f1-4358-a4cc-ea4c28013c50)
It means that if you have several database which you want to find something in common, you have to make them together, and select what you want.


--> in mysql, you need to set up more than 2 tables in you database

e.g.![image](https://github.com/user-attachments/assets/09c1f15e-f7d8-497b-bd9a-63b557fd7597)


so you could refer to my sample

1. chatbot_interactions

![image](https://github.com/user-attachments/assets/940f9e7b-cf12-46f9-959c-0d15125a933e)  --> ![image](https://github.com/user-attachments/assets/3321ad87-3c95-4556-a11b-9fc093648cb4)



2.recommendations 

![image](https://github.com/user-attachments/assets/f2a660ee-63e4-43f4-b799-ecd1c85063e8)-->  ![image](https://github.com/user-attachments/assets/80ee3721-27a7-40d5-ba66-4a4071c3f447)



The same item is  user id. because of it  you could make them together. And than, if you do not under stand the meaning, you could just refer to my code 


ER diagram

![MYSQLDIAGRAM](https://github.com/user-attachments/assets/d611c41b-c5b7-4e30-85f3-f9f4945e4cdd)


# 1022 add email、user id search function for the inner join
code:https://github.com/pupupeter/database-/blob/main/1022.ipynb

html:https://github.com/pupupeter/database-/blob/main/template2.html
# 1023 add feedback table and recommendations table

I had added the feedback table and recommendations table function to see user's ID and others, if you input the value that mysql database does not  exist. The execution would have problem, so you have to add a proper UserID in advance, like  "add user management" in html or from mysql itself.

code:https://github.com/pupupeter/database-/blob/main/1023.ipynb

html:https://github.com/pupupeter/database-/blob/main/template4.html

# 1021 NOSQL-mongoDB 
The link for mongoDB download:

https://fastdl.mongodb.org/windows/mongodb-windows-x86_64-8.0.1-signed.msi

1.![image](https://github.com/user-attachments/assets/ac262e03-8ede-441e-b353-783293358dc4)

2.![image](https://github.com/user-attachments/assets/954e1023-575b-43f5-ac67-7347523ba4ba)

3.![image](https://github.com/user-attachments/assets/d6de747b-4f8a-4c17-be67-4ea1fc4d036f)

I use jupyter notebook to show mongoDB, if you want to build a database for the complex and random data,mongoDB is a suitable application to be used.
# 1028 MongoDB with other page

I set up a function to suitablely add new data --> description and Profession

And in order to make the website clear, i also adjust the page, making the adding data page could be a independent page.

![image](https://github.com/user-attachments/assets/1d2a5323-5414-4c70-974a-5a64070681bb)

![image](https://github.com/user-attachments/assets/64d58839-fd83-4e57-bf69-47bd4e27e0a8)

so it means that you have to generate two different html to present the function.

code: https://github.com/pupupeter/database-/blob/main/NOSQLWITHOTHERPAGE.ipynb

html: create.html    https://github.com/pupupeter/database-/blob/main/create.html

123.html   https://github.com/pupupeter/database-/blob/main/123.html



# 1104 Use db.collection.find and db.collection.aggregate. (Read) and add a new column to input new item

I set up a  function that make UI clear.

What's more, I also create a function that  can add  a new column and content which i could input something by myself   

```
def add_data():
    if request.method == 'POST':
        # Get basic data from the form
        name = request.form.get('name')
        description = request.form.get('description')
        profession = request.form.get('profession')

        # Basic fields
        new_doc = {
            'name': name,
            'description': description,
            'profession': profession
        }

        # Retrieve the names and attributes of dynamically added fields
        field_names = request.form.getlist('fieldName[]')
        field_values = request.form.getlist('fieldValue[]')

        # Add dynamic fields to the document
        for i in range(len(field_names)):
            field_name = field_names[i]
            field_value = field_values[i]
            new_doc[field_name] = field_value

        # Insert the new data into the MongoDB collection
        collection.insert_one(new_doc)

        # Redirect to the homepage to display the newly added data after submission
        return redirect(url_for('index'))

    # Display the form page for adding new data on GET requests
    return render_template('your.html')



```


![image](https://github.com/user-attachments/assets/fbb75d5f-f5c2-4463-b58d-d829cdc67eec)


you could find that there are different column stored, and in mangoDB you can also see the data sucessfully stored

![image](https://github.com/user-attachments/assets/3d690a55-e896-4a6d-85ec-742fc6cd76be)


Once you think  information is too much , you can just click Hide 

![image](https://github.com/user-attachments/assets/fcd4bf28-4820-4445-96fd-db0c830dd91a)  -->hide 



If you want to establish a new column , click  adding column

![擷取1](https://github.com/user-attachments/assets/ab5a3d98-d310-4113-ac32-255fef507142)


And than you can input something here 

![image](https://github.com/user-attachments/assets/90360fee-6f87-4d58-be28-643e7970f6ea)





html: search1.html https://github.com/pupupeter/database-/blob/main/search1.html
123-2.html   https://github.com/pupupeter/database-/blob/main/123-2.html

code: https://github.com/pupupeter/database-/blob/main/1104new.ipynb

# 1111 nosql with edit and delete

Add  edit and delete function to properly manage user's information. 

e.g. ![image](https://github.com/user-attachments/assets/4f18ef05-3074-4ee1-b0de-b2368e926b25)
 you could find 編輯/刪除， choose 編輯
![image](https://github.com/user-attachments/assets/88f0c4ec-042b-485e-ae51-f1bb231b05bd)

you can just modify the user's information, after you finish, click update. you can find the new data

![image](https://github.com/user-attachments/assets/7fe7f552-5a49-446d-8f72-365254313ece)


once you think the data that is not important, you could just click 刪除. 
![image](https://github.com/user-attachments/assets/a1f0ab67-e3fa-46ef-8583-93c987f460e9)

![image](https://github.com/user-attachments/assets/33a94597-acea-4005-b3de-cb0ad5acfbc5)

done~


html: update12:https://github.com/pupupeter/database-/blob/main/update12.html

index12:https://github.com/pupupeter/database-/blob/main/index12.html

create11:https://github.com/pupupeter/database-/blob/main/create11.html


code:https://github.com/pupupeter/database-/blob/main/1111%E6%88%90%E5%8A%9F%E7%9A%84.ipynb


# 1125/1202 project login、summary

1. i add a login interface to make sure if the staff could suitably use the function
  ![image](https://github.com/user-attachments/assets/6e42dda4-7fd5-4eaa-8c88-132a36d92fe6)
 
2. using Retrieval-augmented generation(RAG) to query someone's interest so that staff could understand what customers want(by using gemini)
   ![image](https://github.com/user-attachments/assets/4ce4caf2-0e71-466f-a406-d7d2c1b7729a)

3. Translate from Chinese to English




