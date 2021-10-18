# code
import random

x = int(input("输入你的年级："))
y = int(input("输入题目数量："))

t = 0   #正确题目数量
m = 0   #当前答题总数

#一二年级学生（一百以内的加减乘除）
if x == 1 or x == 2:
    print("开始")
    while m < y:
        a = [ '+','-','*','/' ]
        sign = random.choice(a)        #随机选择算法

        if sign == '/':        #除法
            Num1 = int(random.randint(0, 100))
            Num2 = int(random.randint(1, 100))
            print('%.d%s%.d=?' % (Num1, sign, Num2))
            Answer = input('请输入答案【有小数请保留小数点后三位】: ')
            Correct_Answer = float(Num1 / Num2)
        m += 1
        if sign == '*':        #乘法
            Num1 = int(random.randint(0, 100))
            Num2 = int(random.randint(1, 100))
            print('%.d%s%.d=?' % (Num1, sign, Num2))
            Answer = float(input('请输入答案: '))
            Correct_Answer = Num1 * Num2

        if sign == '+':        #加法
            Num1 = int(random.randint(0, 100))
            Num2 = int(random.randint(1, 100))
            print('%.d%s%.d=?' % (Num1, sign, Num2))
            Answer = float(input('请输入答案: '))
            Correct_Answer = Num1 + Num2

        if sign == '-':        #减法
            Num1 = int(random.randint(0, 100))
            Num2 = int(random.randint(1, 100))
            print('%.d%s%.d=?' % (Num1, sign, Num2))
            Answer = float(input('请输入答案: '))
            Correct_Answer = Num1 - Num2

        if sign == '/':         #除法特殊情况（除不尽）保留3位
            if Correct_Answer % 1 != 0:
                Correct_Answer = ('%.3f' %Correct_Answer)

        if Answer == Correct_Answer:        #判断对错
            print('正确！')
            t += 1
        else:
            print('错误！')

    print('正确题目数量:%d道,得分为:%d' %(t,10*t))
