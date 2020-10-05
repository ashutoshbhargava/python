# python
rint("\t\t**INSTRUCTIONS**\n->THIS IS A GUESS GAME\n->WHEN YOU HAVE TWO TOO CLOSE GUESS.YOU HAVE A MORE CHANCE FOR GUESS ")
import random
ygs=0
b=0
bc=0
l=[]
print("")
gnum=random.randint(1,25)
#gnum=int(input("enter your guess number:\n"))
cgs=int(input("-->ENTER YOUR CHANCE YOU WANT:\n"))
while(cgs>=ygs):
    yrnum=int(input("-->ENTER YOUR NUMBER:\n")) #enter number you guess
    ygs = ygs + 1
    if yrnum in l:
        print("<---YOU GUESSED IT--->")
        ygs -= 1
        print("-->YOU USED GUESS.", ygs + bc)
        print("-->YOU HAVE ", cgs - ygs)
    else:
        l.append(yrnum)
        if yrnum==gnum: #if your number is guessed
           print("CONGRALUTATIONS YOU ARE WINNER")
           print("-->GUESS NUMBER IS:--{}--.".format(gnum))
           print("YOU USED GUESS", ygs+bc)
           print("REMAIN GUESS IS ", cgs - ygs)
           break

        elif gnum>yrnum: #if your number is lower
            if yrnum>=gnum-5 :# if your number is near n lower to guess number
                print("-->YOUR GUESS **TOO CLOSE**  AND  **LOW**\n GUESS --HIGHER-- ")
                b=b+1
                if b==1:#if you guess a num is near to guess number you have a chance to bonus
                    print("**YOU HAVE A CHANCE TO GET A BONUS")
                #print(b)
            else:#your num is not near to guess num.
                print("-->YOUR GUESS IS *LOW*\n GUESS --HIGHER--")
        elif gnum<yrnum:# if your number id higher.
            if yrnum<=gnum+5:# if your number is near n higher to guess number
                print("YOUR GUESS **TOO CLOSE**  AND  **HIGH**\n GUESS --LOWER--")
                b=b+1
                if b==1:#if you guess a num is near to guess number you have a chance to bonus
                 print("**YOU HAVE A CHANCE TO GET A BONUS")
                #print(b)
            else:
             print("YOUR GUESS IS **HIGH**\n GUESS --LOWER--",)#your num is not near to guess num.
        if b==2:
            print("-->YOU HAVE A BONUS TO ONE MORE CHANCE ")
            print("-->YOU USED GUESS IS: ",ygs)
            print("-->YOU HAVE",cgs-ygs)
            ygs-=1
            #print(ygs)
            bc+=1
            print("-->YOU HAVE ONE MORE CHANCE TO GUESS")
            b=0

        else:
            #print("GUESS NUMBER IS:--{}--.".format(gnum))
            print("***YOU HAVE NO BONUS.***")
            print("-->YOU USED GUESS.", ygs + bc)
            print("-->YOU HAVE ", cgs - ygs)
    print("<-->" * 8)
    for i in l:
     print("-->YOUR GUESS NUMBER:*->{}<-*".format(i))
    print("<-->"*8)
print("-->GUESS NUMBER IS:--{}--.".format(gnum))
print ("-->IN THIS GAME YOU HAVE ",bc,"bonus")
print("*******GAME**OVER*********")

