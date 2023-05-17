#include<bits/stdc++.h>
using namespace std;

int dfs(int k, vector<vector<pair<int,int>>> &gr,vector<int> &vis)
{
	vis[k] = 1;
	int tm = 0;
	for(auto it:gr[k])
	{
		if(vis[it.first]==0)
		{
			tm = max(tm, it.second + dfs(it.first,gr,vis));

		}
	}
	return tm;
}

int min_timetaken_forAllNodes(vector<vector<pair<int,int>>> &gr, int k, int n)
{
	
	vector<int> vis(n+1,0);
	int minTime = dfs(k,gr,vis);

	for(int i=1;i<=n;i++)
	{
		if(vis[i]==0)
		{
			return -1;
		}
	}

	return minTime;

}

int main()
{
	int n;
	cin>>n;

	vector<vector<pair<int,int>>> gr(n+1);
	
	int edge;
	cin>>edge;
	
	while(edge--)
	{
		int u,v,t;
		cin>>u>>v>>t;
		gr[u].push_back({v,t});

	}

	int k;
	cin>>k;

	int ans = min_timetaken_forAllNodes(gr,k,n);

	cout<<ans<<endl;
	

	return 0;
}
