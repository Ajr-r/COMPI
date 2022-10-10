# Max number of trees in forest 
```c++

    #include <bits/stdc++.h>
    using namespace std;

    int main()
    {
    
        int n;
        cin >> n;
        char arr[n][n];
        for (int i = 0; i < n; i++)
        {
            for (int j = 0; j < n; j++)
            {
                cin >> arr[i][j];
            }
        }

    
        int dx[] = {-1, 0, 1, 0};
        int dy[] = {0, -1, 0, 1};

    
        bool visited[n][n];
        for (int i = 0; i < n; i++)
        {
            for (int j = 0; j < n; j++)
            {
                visited[i][j] = false;
            }
        }

    
        int largest_size = 0;

    for (int i = 0; i < n; i++)
        {
            for (int j = 0; j < n; j++)
            {
                if (arr[i][j] == 'T' && visited[i][j] == false)
                {
                    visited[i][j] = true;

              
                    queue<pair<int, int>> q;
                    q.push({i, j});

              
                    int size = 0;

                    while (!q.empty())
                    {
                        pair<int, int> p = q.front();
                        q.pop();
                        size++;

                        
                        int x = p.first;
                        int y = p.second;

                        
                        for (int k = 0; k < 4; k++)
                        {
                            int newx = x + dx[k];
                            int newy = y + dy[k];

                        
                        
                            if (newx >= 0 && newx < n && newy >= 0 && newy < n && arr[newx][newy] == 'T' && visited[newx][newy] == false)
                            {
                                
                                visited[newx][newy] = true;
                                q.push({newx, newy});
                            }
                        }
                    }

                    
                    largest_size = max(largest_size, size);
                }
            }
        }

        
        cout << largest_size << endl;
        return 0;
    }
```

(https://practice.geeksforgeeks.org/problems/minimum-number-of-jumps-1587115620/1?page=1&sortBy=submissions)
