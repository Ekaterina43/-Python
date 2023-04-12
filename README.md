Для онлайн-конференции необходимо написать программу, которая будет подсчитывать общую стоимость билетов. Программа должна работать следующим образом:

1. В начале у пользователя запрашивается количество билетов, которые он хочет приобрести на мероприятие.

2. Далее для каждого билета запрашивается возраст посетителя, в соответствии со значением которого выбирается стоимость:

Если посетителю конференции менее 18 лет, то он проходит на конференцию бесплатно.
От 18 до 25 лет — 990 руб.
От 25 лет — полная стоимость 1390 руб.
3. В результате программы выводится сумма к оплате. При этом, если человек регистрирует больше трёх человек на конференцию, то дополнительно получает 10% скидку на полную стоимость заказа.

# в начале запрашивается необходимое колличество билетов
all_tickets = int(input('Введите колличество билетов:'))
# создаётся список, куда добавляется возраст участников
num_ages = []
for i in range(0, all_tickets):
    age = int(input(f'Введите возраст участника №{i + 1}:'))
    num_ages.append(age)
# затем участник узнаёт стоимость своего билета по возрастным ограничениям
def prise(age):
    if age < 18:
        print('Просмотр конференции бесплатный')
    elif 18 >= age <= 25:
        print('Стоимость вашего билета 990 рублей')
    elif age > 25:
        print('Стоимость вашего билета 1390 рублей')
# после высчитывается полная стоимость билетов
full_prise = sum(map(prise, num_ages))
# если билеты покупаются больше 3 штук, высчитывается скидка
discount_prise = int(full_prise * 0.9)
if all_tickets > 3:
    print('Стоимость всех билетов со скидкой: ', discount_prise, "руб.")
else:
    print('Стоимость всех билетов: ', full_prise, "руб.")

-
