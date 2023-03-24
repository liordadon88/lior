#Q1
def my_func(x1,x2,x3):
    if isinstance(x1,str)==True or isinstance(x2, str)==True or isinstance(x3, str)==True:
        return None
    elif isinstance(x1, float)==False or isinstance(x2, float)==False or isinstance(x3, float)==False:
        return('Error: parameters should be float')
    elif ((x1+x2+x3)*(x2+x3)*x3)==0:
        return('Not a number-denominator equals zero')
    else:
        return(((x1+x2+x3)*(x2+x3)*x3)/(x1+x2+x3))
        
#Q2
def revword(word):
    word_list=[]
    end=-(len(word))-1
    for i in range(-1,end,-1):       
        word_list.append(word[i])
    new_word="".join(word_list)
    return(new_word)

def countword():
    file=open("C:\\Users\\User\\Desktop\\python_hw\\mat1\\text.txt")
    ls_file=[]
    final_ls=[]
    for line in file:
        line=line.rstrip()
        ls_file.append(line.split())
    
    for i in range(len(ls_file)):
        for j in range(len(ls_file[i])):
            if i==0 and j==0:
               final_ls.append(ls_file[i][j])
            else:
                final_ls.append(revword(ls_file[i][j]).lower())
    word=final_ls[0]
    count=0
    for i in range(len(final_ls)):
        if word==final_ls[i]:
            count=count+1
    return count
    
print(countword())
