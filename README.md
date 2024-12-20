# PythonStudy24
파이썬 AI 기초 학습용

MBC 아카데미 컴퓨터 교육센터 수원점에서 AI 기초 학습으로 파이썬 학습 진행용

https://wikidocs.net/book/1

- 파이썬 버전 : 3.11.2
- Colab을 사용하여 예제 학습
  
## 공부 내용

![image](https://github.com/user-attachments/assets/11c14d01-59f5-4cf7-864a-796ddf89242e)
- (24/12/18) BaseType
- (24/12/19) ListType, TupleType, DictionaryType, SetType, BoolType, 변수

<br>

![image](https://github.com/user-attachments/assets/0101decb-c8b4-4027-aae8-19194f61bbe3)
- (24/12/20) IfStudy, WhileStudy
  WhileStudy 미션
# 미션
# 관리자가 커피 가겨고가 커피명을 정하고 개수를 입력한다.
# 소비자가 커피를 구매하는데 잔돈이 나와야 함
# 판매 종료 후 관리자가 커피 판매한 총액을 파악해야 함
# (if와 while 두개 사용하기)

prompt1 = """
- 금액 투입 단계-
=======================================
| 1. 음료1 300원   | 2. 음료2 400원   |
=======================================
| 3. 음료3 500원   | 4. 음료4 600원   |
=======================================

구매하기전 원하는 만큼 금액을 투입하고
         '구매'를 입력해주세요.
=======================================
"""

prompt2 = """
- 음료 구매 단계 -
=======================================
| 1. 음료1 300원   | 2. 음료2 400원   |
=======================================
| 3. 음료3 500원   | 4. 음료4 600원   |
=======================================

      구매가 끝나셨으면 거스름 돈
         '반환'을 입력해주세요.
=======================================
"""

drink = [10, 10, 10, 10]    # 음료 1,2,3,4 기본수량
totalMoney = 0  # 넣은 금액
sumPrice = 0    # 판매 총액

while True:
    print("\n\n")
    print(prompt1)
    print(" >>>    현재 잔액 : %d원" % totalMoney)
    money = input("\n 얼마를 넣을까요? : ")

    if money == "종료":
        print("\n\n\n 프로그램을 종료합니다.")
        break
    elif money == "관리자":
        while True:
            print("\n\n\n===============================================================")
            print("        관리자 모드를 실행합니다 ")
            print("       >>> 판매 총액 : %d원<<<" % sumPrice)
            print("===============================================================")
            print(" 1. 음료1(%d개), 2. 음료2(%d개), 3. 음료3(%d개), 4. 음료4(%d개)" % (drink[0],drink[1],drink[2],drink[3]))
            print("===============================================================")
            input2 = input("\n판매 모드로 돌아가려면 '판매'를 입력해주세요 : ")
            if input2 == '판매': break
    elif money == "구매":
        while True:
            print("\n\n")
            print(prompt2)
            print(" >>>    현재 잔액 : %d원" % totalMoney)
            input1 = input("\n 구매하고 싶은 음료의 번호를 입력해주세요 : ")
            print("\n\n\n >>> ")
            if input1 == "반환":
                print(" 거스름돈 %d원을 반환합니다." % totalMoney)
                print(" 이용 해주셔서 감사합니다 ^^")
                totalMoney = 0
                break
            elif input1 == '1':
                if totalMoney >= 300:
                    if drink[0] > 0:
                        drink[0] = drink[0] - 1
                        totalMoney = totalMoney - 300
                        sumPrice = sumPrice + 300
                        print(">>> 음료1을 구매합니다.")
                    else: print(">>> 음료1은 현재 품절입니다.")
                else: print(">>> 금액이 부족합니다.")
            elif input1 == '2':
                if totalMoney >= 400:
                    if drink[1] > 0:
                        drink[1] = drink[1] - 1
                        totalMoney = totalMoney - 400
                        sumPrice = sumPrice + 400
                        print(">>> 음료2을 구매합니다.")
                    else: print(">>> 음료2은 현재 품절입니다.")
                else: print(">>> 금액이 부족합니다.")
            elif input1 == '3':
                if totalMoney >= 500:
                    if drink[2] > 0:
                        drink[2] = drink[2] - 1
                        totalMoney = totalMoney - 500
                        sumPrice = sumPrice + 500
                        print(">>> 음료3을 구매합니다.")
                    else: print(">>> 음료3은 현재 품절입니다.")
                else: print(">>> 금액이 부족합니다.")
            elif input1 == '4':
                if totalMoney >= 600:
                    if drink[3] > 0:
                        drink[3] = drink[3] - 1
                        totalMoney = totalMoney - 600
                        sumPrice = sumPrice + 600
                        print(">>> 음료4을 구매합니다.")
                    else: print(">>> 음료4은 현재 품절입니다.")
                else: print(">>> 금액이 부족합니다.")
            else: print("\n\n\n!!!!!! 잘못 입력하셨습니다. !!!!!!")
    elif not money.isdigit(): print("\n\n\n!!!!!! 잘못 입력하셨습니다. !!!!!!")
    else : totalMoney = totalMoney + int(money)

     
