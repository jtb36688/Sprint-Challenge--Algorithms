Exercise 1)

    A)
    

Exercise 2)

Each floor has a true or false value describing whether or not an egg breaks. The upper floors have a True value, and there may be floors below with a False value. I can use a logarithmic method to efficiently determine which floor f, which is the lowest floor that has a True value. By continuously cutting the array in half, and testing on the last index of the first half, I can determine each time which half of the array includes f.

With n representing the amount of floors,
and eggdrop(floor) representing a function which returns True or False dependent on if an egg has broken

def eggtestfunc(n):
    floorsremain = True
    while floorsremain:
        midpoint = len(n)//2
        print(midpoint)
        lefttest = n[0:midpoint][-1]
        print(lefttest)
        if eggdrop(lefttest):
            n = n[0:midpoint]
        else:
            n = n[midpoint:]
        print(n)
        if len(n) == 1:
          print("done")
          floorsremain = False
    return n[0]