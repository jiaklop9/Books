迪米特法则
======================================

描述
------------
【Low Of Demeter】：高内聚 低耦合 – high cohesion low coupling(类只做一类事情,类的成员函数关联尽量少)。\ 例如: \ 体育课上，体育老师要进行点名，她让体育课代表去点名 \ 类Teacher与类 StudentList, Student, Representative都有耦合关系，但他们都是内嵌到类Teacher的command方法中

代码示例
-------------------------------

.. code:: python

    class Teacher(object):

        def __init__(self, representative):
            self.representative = representative

        def command(self):
            print('老师让课代表点名')
            self.representative.count()


    class Representative(object):

        def __init__(self, studentlist):
            self.studentlist = studentlist

        def count(self):
            print('课代表开始点名')
            self.studentlist.size()


    class StudentList(list):

        def add_student(self, num):
            for _ in range(num):
                self.append(Student())

        def size(self):
            print('学生的人数为%s' % str(len(self)))


    class Student(object):
        pass


    class Client(object):
        def main(self, teacher):
            teacher.command()

    if __name__ == '__main__':
        studentlist = StudentList()
        studentlist.add_student(10)
        representative = Representative(studentlist)
        teacher = Teacher(representative)
        client = Client()
        client.main(teacher)
