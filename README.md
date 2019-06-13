# 4-1
def HC(meeting):
    length=len(meeting)
    meeting.sort(key=lambda x:x[1]) # 从第二位开始取
    result=[False for i in range(length)]
    j=0 #当前选中的活动
    result[j]=True #选中第一个活动
    for i in range(1,length):
        if meeting[i][0]>=meeting[j][1]:
            j=i
            result[j]=True
    return result
 
def show(result):
    length=len(result)
    print('安排的活动为：')
    count=0
    for i in range(length):
        if result[i]:
            print('第',i+1,'个活动')
            count+=1
    print('\n共计',count,'个活动')
if __name__=='__main__':
    meetings=[(1,4),(3,5),(0,6),(5,7),(3,8),(5,9),(6,10),(8,11),(8,12),(2,13),(12,14)]
    res=HC(meetings)
    show(res)
