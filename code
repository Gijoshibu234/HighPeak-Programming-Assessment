with open("/uploads/sample_input3.txt") as file:
    file.seek(0)
    text = file.readlines()

goodies=[]
price=[]
n=int(input('Number of employees: '))
for i in text:
    temp=str(i).split(":")
    goodies.append(temp[0])
    price.append(int(str(temp[1]).strip().split('\n')[0]))

print(goodies)


for i in range(len(price)):
    for j in range(i+1,len(price)):
        if price[j]<price[i]:
            temp=price[j]
            price[j]=price[i]
            price[i]=temp
            goodies[i],goodies[j] = goodies[j],goodies[i]

            

ans = price[n-1] - price[0]
index = 0

t = len(price)

for i in range(1,t-n-1):
    temp = price[i+n-1] - price[i]
    if temp < ans:
        ans = temp
        index = i
        
f = open("output.txt", "w")
f.write("Number of Employees:  "+str(n)+"\n")
f.write("\nSelected goodies:\n")
for j in range(index,index+n):
    f.write(str(goodies[j])+' : '+str(price[j])+'\n')
f.write("\nThe difference between the chosen goodie with highest price and the lowest price is "+str(ans)+"\n")
f.write("\n")
f.close()
print("\nOutput.txt\n")
f = open("output.txt", "r")
print(f.read())
