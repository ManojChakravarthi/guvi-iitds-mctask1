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
if avg > 90:
    print("Grade A")
elif avg <= 89 and avg >= 80:
    print("Grade B")
elif avg <=79 and avg >=70:
    print("Grade C")
elif avg <=69 and avg >=60:
    print("Grade D")
elif avg <=59 and avg >=50:
    print("Grade E")
else:
    print("Grade F")

import mysql.connector

db = mysql.connector.connect(
    host="localhost",
    user="root",
    password="",
    database="learning"
)
mycursor = db.cursor()
mycursor.execute("INSERT INTO mytrial (name,dept,mark1,mark2,mark3,mark4,mark5,total,avg) VALUES (%s,%s,%s,%s,%s,%s,%s,%s,%s)",(n,dep,a,b,c,d,e,total,avg))
db.commit()