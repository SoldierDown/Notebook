# Array
## 832.e Flipping an Image 
	vector<int> result;
	int ele = 1;
	result.push_back(ele);	// correct
	result[0]=ele;		// wrong

## 561.e Array Partition I
	bool myfunction (int i, int j) { return (i<j);}
	struct myclass{
		bool operator() (int i, int j){ return (i<j);}
	} myobject;
	...
	int myints[] = {32,71,12,45,26,80,53,33};
	std::vector<int> myvector (myints, myints+8);               // 32 71 12 45 26 80 53 33

	// using default comparison (operator <):  
	std::sort (myvector.begin(), myvector.begin()+4);           //(12 32 45 71)26 80 53 33

	// using function as comp
	std::sort (myvector.begin()+4, myvector.end(), myfunction); // 12 32 45 71(26 33 53 80)

	// using object as comp
	std::sort (myvector.begin(), myvector.end(), myobject);     //(12 26 32 33 45 53 71 80))

## 509.e Fibonacci Number
	// avoid using recursive method because it is time-comsuming

## 922.e Sort Array By Parity II
	// a better solution will be as follows
	public int[] sortArrayByParityII(int[] A) {
		int len = A.length;        
		int[] val = new int[A.length]; // use a new array to store data
		int even = 0; // calculate odd elements and even elements 
		int odd = 1;  // separately
		for (int i = 0; i < len; i++) 
		{
			if((A[i] & 1) == 0)
       			{
                		val[even] = A[i];
                		even += 2;
           	 	}
			else 
			{
                		val[odd] = A[i];
                		odd += 2;
            		}
        	}

        	return val;
	}

## 867.e Transpose Matrix
	// don't forget to clear the vector 

## 766.e Toeplitz Matrix 
	// a better solution wll be as follows
	bool isToeplitzMatrix(vector<vector<int>>& matrix) 
	{
        	int R = matrix.size();
        	int C = matrix[0].size();
        
	// Work out all rows except for last
 		for(int i = 0; i < R - 1; i++) 
		{
            		for(int j = 0; j < C - 1; j++) 
			{
                		if(matrix[i][j] != matrix[i+1][j+1])	return false;
                
            		}
        	}
        	return true;

	}

## 566.e Reshape the Matrix
	// pay attention to = and ==

## 976.e Largest Perimeter Triangle 
	// a better solution will be as follows
	int largestPerimeter(vector<int>& A) 
	{
        	sort(A.begin(),A.end());
        	for(int i = A.size() - 1; i >= 2; i--)
        	{
            		if(A[i - 2]+A[i - 1]>A[i]) return A[i - 2] + A[i - 1] + A[i];
        	}
        		return 0;
	}


	// Explanation for Sort:
	// Without loss of generality, let's say the sidelengths of the triangle are a <= b <= c.
	// To build up a valid triangle we need: a + b > c
	// So there are two cases:
	// Case 1: C >= A + B => cannot form a valid triangle if the largest sidelength is C.
	// Case 2: C < A + B ==> valid triangle. Since we need the largest perimeter, and A' < A, B' < B, this is exactly what we need!
	// this algorithm avoids the O(N^3) case

## 888.e Fair Candy Swap
	// a better solution is to use a hashtable(O(N))

## 485.e Max Consecutive Ones
	// don't forget some details

## 283.e Move Zeroes
	// already one of the solutions

## 448.e Find All Numbers Disappeared in an Array
	// almost the same except that it uses positive/negetive to mark if a number has appeared.
	for(int i = 0; i < nums.size();) i++)
	{
		int m = abs(nums[i]) - 1;
		nums[m] = nums[m] > 0 ? -nums[m] : nums[m];
	}

## 169.e Majority Element
	// Boyer-Moore Majority Voting Algorithm
	int majorityElement(vector<int>& nums)
	{
		int candidate = nums[0];
		int count = 1;
		for(int i = 1; i < nums.size(); i++)
		{
			if(count == 0) candidate = nums[i]; // the majority element will also be the majority element of the rest of the array
			if(candidate == nums[i]) count++;
			else count--;
		}
		return candidate;
	}

	// Another algorithm is to sort the array.





