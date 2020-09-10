给定一个会议时间安排的数组，每个会议时间都会包括开始和结束的时间 [[s1,e1],[s2,e2],...] (si < ei)，为避免会议冲突，同时要考虑充分利用会议室资源，请你计算至少需要多少间会议室，才能满足这些会议安排。

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/meeting-rooms-ii
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。

示例 1:

输入: [[0, 30],[5, 10],[15, 20]]
输出: 2
示例 2:

输入: [[7,10],[2,4]]
输出: 1

class Solution {
public:
    
    struct cmp{    
        bool operator() (vector<int> first,vector<int> second)
        {
            if(first[0]<second[0])
            {
                return true;
            }else{
                return false;    
            }
        }
        };
    
    struct cmp1
    {
        bool operator()(vector<int> first, vector<int> second)
        {
             if(first[1]>second[1])
             {
                 return true;
             }
            return false;
        }
    };
    
    
    int minMeetingRooms(vector<vector<int>>& intervals) {
        
        sort(intervals.begin(),intervals.end(),cmp());
        
        if(intervals.size()==0)return 0;
        
        priority_queue<vector<int>,vector<vector<int> >,cmp1> pd;
        
        
        int res = 0;
         
        for(auto each : intervals)
        { 
            if(pd.size()!=0)
            {
                vector<int>  temp = pd.top();
                while(pd.size()!=0 && each[0]>=temp[1]) 
                {
                    pd.pop();
                    if(pd.size()!=0)
                    {
                    temp = pd.top();
                    }
                    else{
                        break;
                    }
                }
               
            }
             pd.push(each);
            if(res<pd.size())res = pd.size();
        }
            
         return res;      
        };
};
