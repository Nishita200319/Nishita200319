





# coding:



#creating class name student_info with member function display_info() and constructor

# this class willrepresent the information of students

class student_info:

    #constructor

    def __init__(self,name,rollno,marks1,marks2):

        self.name=name

        self.rollno=rollno

        self.marks1=marks1

        self.marks2=marks2

        

    def display_info(self):

        print("Student's name: ",self.name)

        print("Student's roll number: ",self.rollno)

        print("Marks scored in first subject: ",self.marks1)

        print("Maeks scored in second subject: ",self.marks2)

        

#creating class student with member function accept(),display(),search(),update(),deete()

#this class will manage a list of student record

class student:

    def __init__(self):

        self.st_list=[]

        

    def accept(self,name,rollno,marks1,marks2):

        stud=student_info(name,rollno,marks1,marks2)

        self.st_list.append(stud)

        

    def display(self):

        print("------students record-------")

        for student_info in self.st_list:

            

            student_info.display_info()

            print("----------------------------")

            

    def search(self,rollno):

        for student_info in self.st_list:

            if student_info.rollno==rollno:

                print("student found")

                print("the required information is as follows:")

                student_info.display_info()

                print("____________________________")

                

    def update(self,rollno):

        for student_info in self.st_list:

            if student_info.rollno==rollno:

                print("student found___update record")

                student_info.name=input("enter new name of student: ")

                    

                student_info.marks1=input("enter marks of first subject to update: ")

                student_info.marks2=input("enter marks of second subject to be update: ")

                print("record updated successfully!!")

                self.display()

                return

            print("the given roll number is invalid!!")

         

        

                

    def delete(self,rollno):

        for student_info in self.st_list:

            if student_info.rollno==rollno:

                self.st_list.remove(student_info)

                print("record deleted!!")

                print("_________________")

                print("_________________")

        

        

#object created:- obj

obj=student()

#student data

obj.accept("Abhi",1,67,89)

obj.accept("Babita",2,99,90)

obj.accept("Isha",3,45,67)

obj.accept("Harsh",4,87,43)

obj.accept("Nishant",5,78,54)

obj.accept("Palak",6,90,34)

#this function will dispaly information of students

obj.display()

#this function will display the information of particular roll number given

obj.search(2)

obj.update(1)

#this function will delete the information of student

obj.delete(6)

obj.display()
