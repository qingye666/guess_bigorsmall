#import random
#摇骰子
def roll_dice(dice_lib):
    print('<'*8 +'ROLE THE DICE!'+ '>'*8)
    i = 0
    while i < 3:
        dice_lib.append(random.randrange(1,7))
        i = i+1
    return dice_lib

#计算大小
def big_small(dice_list):
    count = sum(dice_list)
    if 3 <= count <= 10:
        result = 'Big'
    elif 11 <= count <=18:
        result = 'Small'
    return result

#比较大小
def compare(a,x,dice_list,result,guess):
    if result == guess:
        a = a + (x*2)
        print('The Points are {} You Win!'.format(dice_list))
        print('You gainel {} You have {} now'.format(x*2,a))
    else:
        print('The lost {} You have {} now!'.format(x,a))
    return a

#猜大小
if __name__ == '__main__':
    a = 1000
    while a > 0:
        dice_lib = []
    #Bs_lib =['Big','Small']
        print('<' * 8 + '   GAME STARTS!   ' + '>' * 8)
        guess = input('Big or Small: ')
        money = input('How much you wanna bet? --')
        x = int(money)
        list = roll_dice(dice_lib)
        result = big_small(list)
        compare(a,x,list,result,guess)



 guess_bigorsmall
