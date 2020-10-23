# One-to-one-character-mapping
Determine whether there exists a one-to-one character mapping from one string s1 to another s2.


#include<bits/stdc++.h>
using namespace std;
#define maxchar 250
//function returns true if noth strings are isomorphic
bool areisomorphic(string str1, string str2)
{
	int m=str1.length(), int n=str2.length();
	//length of both the strings should be same for one to one
	if(m!=n)
		return false;
	//to mark visited characters in str2
	bool marked[maxchars]={false};
	//store mapping of every character from string 1 to string 2
	int map[maxchars];
	memset(map,-1,sizeof(map));
	//process all characters one by one
	for(int i=0;i<n;i++)
	{
		//if current character in string 1 is seen for the first time
		if (map[str1[i]] == -1) 
			//if current character in string 2 is already seen then one to one mapping is not possible
		if(marked[str2[i]]==true)
			return false;
		//mark current character of str2 visited
		marked[str2[i]]=true;
		//store mapping of current characters
		map[str1[i]]=str2[i];
	}
	//If this is not first appearance of current character in str1, then check if previous appearance mapped to same character of str2 
	else if(map[str1[i]] != str2[i]) 
            return false; 
    } 
     return true; 
} 
//driver code
int main() 
{ 
   cout << areIsomorphic("aab", "xxy") << endl; 
   cout << areIsomorphic("aab", "xyz") << endl; 
   return 0; 
} 
