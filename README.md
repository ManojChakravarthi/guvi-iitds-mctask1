# guvi-iitds-mctask1
n = input("Enter Name: ")
dep = input("Enter Department: ")
a = int(input("Enter Mark1:"))
b = int(input("Enter Mark2:"))
c = int(input("Enter Mark3:"))
d = int(input("Enter Mark4:"))
e = int(input("Enter Mark5:"))
total = a+b+c+d+e
avg = total/5
print("Total Mark is: ", total)
print("Average is: ", avg)
if avg>90:
    grade="A"
elif avg>80 and avg<89:
    grade="B"
elif avg>70 and avg<79:
    grade="C"
elif avg>60 and avg<69:
    grade="D"
elif avg>50 and avg<59:
    grade="C"
else:
    grade="E"

import mysql.connector

db = mysql.connector.connect(
    host="localhost",
    user="root",
    password="",
    database="learning"
)
mycursor = db.cursor()
mycursor.execute("INSERT INTO mytrial (name,dept,mark1,mark2,mark3,mark4,mark5,total,avg,grade) VALUES (%s,%s,%s,%s,%s,%s,%s,%s,%s,%s)",(n,dep,a,b,c,d,e,total,avg,grade))
db.commit()