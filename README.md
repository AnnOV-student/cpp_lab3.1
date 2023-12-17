#include <iostream>
#include <stdio.h>
#include <stdlib.h>

using namespace std;

int minimum(int i, int n, int* a, int sum1, int sum2)
{
	if (i < n) {
		int min1 = minimum(i + 1, n, a, sum1 + a[i], sum2);
		int min2 = minimum(i + 1, n, a, sum1, sum2 + a[i]);
		if (min1 < min2)
			return min1;
		return min2;
	}
	return abs(sum1 - sum2);
}
int main()
{
	int n;
	cin >> n;
	int* a = new int [n];
	for (int i = 0; i < n; i++)
	{
		cin >> *(a+i);
	} 
	cout << minimum(0, n, a, 0, 0);
}
