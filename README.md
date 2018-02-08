# 541---Error-Correction

#include <bits/stdc++.h>

using namespace std;

int arr[100][100];

int main()
{

	int n;
	
	while (cin >> n && n)
	{
		for (int i = 0; i < n; i++)
		{
			for (int j = 0; j < n; j++)
			{
				cin >> arr[i][j];
			}
		}
		int nRows = 0, nCols = 0, x, y;

		int rowsum = 0, colsum = 0;

		for (int i = 0; i < n; i++)
		{
			rowsum = 0;

			for (int j = 0; j < n; j++)
			{
				rowsum += arr[i][j];
			}
			if (rowsum % 2 == 1)
			{
				nRows++;
				x = i;
			}
		}

		for (int i = 0; i < n; i++)
		{
			colsum = 0;

			for (int j = 0; j < n; j++)
			{
				colsum += arr[j][i];
			}
			if (colsum % 2 == 1)
			{
				nCols++;
				y = i;
			}
		}

		if (nRows == 0 && nCols == 0)
			cout << "OK" << endl;
		else if (nRows == 1 && nCols == 1)
			cout << "Change bit (" << x+1 << "," << y+1 << ")" << endl;
		else
			cout << "Corrupt" << endl;
	}
	
	return 0;
}
