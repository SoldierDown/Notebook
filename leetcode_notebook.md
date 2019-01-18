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
