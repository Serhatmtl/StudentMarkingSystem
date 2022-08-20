# StudentMarkingSystem
# The program gets variables to calculate the marking.

from pandas.core.dtypes.common import infer_dtype_from_object
import matplotlib.pyplot as plt
import pandas as pd
import numpy as np

student_title =pd.DataFrame(columns = ["Student Name", "Student Surname"," Student Number", " Student Mark", "Mark-Alph", "Situation"])

Student_Name = []
Student_Surname = []
Student_Number = []
Student_Mark = []
Mark_Alph = []
Situation = []

while (True):
    program = input("Welcome To Student Record System, If you like to quit programme please press q")
    if program == "q":
       break
    Student_Name.append(input("Please enter student's name: "))
    Student_Surname.append(input("Please enter student's surname: "))
    Student_Number.append(int(input("Please enter student's number: ")))
    Student_Mark_ = (int(input("Please enter student's mark:" )))
    #for i in Student_Mark:

    if Student_Mark_ >= 101 and Student_Mark <= 0:
        print("Please enter number between 100 and 0")
        continue

    if Student_Mark_ >= 80 or Student_Mark_ == 100:
            Student_Mark.append(Student_Mark_)
            Mark_Alph.append("AA")
            Situation.append("Passed")
            print(f"The Mark is AA, {Student_Name} has passed")
            continue

    if Student_Mark_ >= 70 and Student_Mark_ <= 79 :
            Student_Mark.append(Student_Mark_)
            Mark_Alph.append("BB")
            Situation.append("Passed")
            print(f"The Mark is BB, {Student_Name} has passed")
            continue

    if Student_Mark_ >= 60 and Student_Mark_ <= 69:
            Student_Mark.append(Student_Mark_)
            Mark_Alph.append("CC")
            Situation.append("Passed")
            print(f"The Mark is CC, {Student_Name} has passed")
            continue

    if Student_Mark_ >= 50 and Student_Mark_ <= 59:
            Student_Mark.append(Student_Mark_)
            Mark_Alph.append("DD")
            Situation.append("Passed")
            print(f"The Mark is DD, {Student_Name} has passed")
            continue

    if Student_Mark_ < 50:
            Student_Mark.append(Student_Mark_)
            Mark_Alph.append("FF")
            Situation.append("Failed")
            print(f"The Mark is D, {Student_Name} hasn't been successfull. Please study more")
            continue



    #student_title.loc[student_title.shape[0]] = [Student_Name, Student_Surname, Student_Number, Student_Mark, Mark_Alph, Situation]

Dictionary = {
    "Student Name": Student_Name,
    "Student Surname": Student_Surname,
    "Number": Student_Number,
    "Mark": Student_Mark,
    "Mark-Alphabet": Mark_Alph,
    "Situation": Situation
}

#Student_Data = pd.DataFrame(Dictionary)
Student_Data = pd.DataFrame.from_dict(Dictionary,orient='index')
Student_Data = Student_Data.transpose()
Student_Data.head()
