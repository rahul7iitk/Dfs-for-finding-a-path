# Dfs-for-finding-a-path
#include <bits/stdc++.h>
using namespace std;

void conquer_all(vector<int> m[],int n,int id[]);
void dfs(vector<int> m[],int p,int id[],int count);

int main() {
    
	int n,t,a,b,i;
	
	
	cin>>n;
	
	int id[n];
	
	vector<int> m[n];
	
	cin>>t;
	
	while(t-->0)
	{
	 cin>>a>>b;
	 m[a].push_back(b);
	}
	
	for(i=0;i<n;i++)
	id[i]=-1;

	int p,q;
	cin>>p>>q;
	
	
	conquer_all(m,n,id);
	
	if(id[p]==id[q])
	cout<<"There is a path";
	else
	cout<<"There is no path";
	
}

void conquer_all(vector<int> m[],int n,int id[])
{
    int count=0;
    
    for(int i=0;i<n;i++)
    {
        if(id[i]==-1)
        {
            dfs(m,i,id,count);
        count++;
        }
    }
    return;
}
void dfs(vector<int> m[],int p,int id[],int count)
{
    id[p]=count;
    
    for(int i=0;i<m[p].size();i++)
    {
        int a=m[p].at(i);
        if(id[a]==-1)
        dfs(m,a,id,count);
    }
    return;
}
    

    


    
    


















