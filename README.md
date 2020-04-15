# Programming-CheatSheet
C++ Programming cheatsheet.

## Important I/O Techniques
#### How to scan two integers indefinitely?
        while(scanf("%d %d\n",&m,&n)==2)
        {
          cout << m << n << endl; 
        }

#### How to scan a line indefinitely?
        string input_line;
        while(getline(cin,input_line))
        {
                cout << input_line << endl; 
        }
        
        
#### How to scan a string and unknown number of integers on a single line indefinitely?
        #include <sstream>
        string input_line;
        string first_string;
        vector<int> vec;
        int i;
        while(getline(cin,input_line))
        {
                stringstream ss(input_line);
                ss >> first_string;

                while(ss >> i){
                        vec.push_back(i);
                }
                vec.clear();
        }


        
#### How to perform string formatting for I/O?
        #include <iomanip>
        //Setting alignment and word length
        cout << setw(20) << left << "HEADER" << endl;

        //Filling empty space with some character
        cout << setfill('-') << setw(20) << left << "HEADER" << endl;


#### How to perform float/double formatting for I/O?
        #include <iomanip>
        float pi = 3.1456;
        //Setting precision upto 2 decimal points
        cout << fixed;
        cout << setprecision(2) << pi << endl;
        
#### Defining multi-dimension array (statically and dynamically) and initializing it
        // statically
        bool mat[9][9][9];
        memset(mat,false,sizeof(mat));
        // dynamically in C style
        int n = 9;
        bool *mat[n];
        for(int i=0; i<n; i++){
                mat[i] = (int*)malloc(n*sizeof(int));
        }
        memset(mat,false,sizeof(mat));
        // dynamically using "new" keyword
        int n = 9;
        int** mat[n];
        for(int i=0; i<n; i++){
          //empty brackets make it allocate memory and initialize with zero
          mat[i] = new int[n]();
        }


## Important String functions and Techniques
#### Iterating over characters of string?

	string sample_string = "harsh";
	int length = sample_string.size();
	for(int index=0; index < length; index++){
		cout << sample_string[index] << endl;
	}


#### Sorting a string and Reveresal of a string
	string sample_string = "utsav";

	//It is similar to vector : inplace sorting
	sort(string.begin(),string.end());
	sort(string.begin(),string.begin()+2);

	//Inplace reverse
	reverse(sample_string.begin(),sample_string.end())
#### Checking a type of character
	string str = "harsh";

	isdigit(str[0])
	isalpha(str[0])
	isalnum(str[0])
	ispunct(str[0])
	isspace(str[0])
	islower(str[0])
	isupper(str[0])
	// converting character to upper or lower case
	toupper(str[0])
	tolower(str[0])
#### Converting string to integer and vice-versa
	#include <cstdlib> //for atoi
	#include <sstream> //for stringstream

	//converting string to integer
	string str = "124";
	int i = atoi(str.c_str());

	//converting integer to string
	int i = 42;
	stringstream ss;
	ss << i;
	string s = ss.str();
	//alternative method for converting integer to string
	string numStr = to_string(i);


#### String comparison
	#include <string>

	string s1 = "abc";
	string s2 = "abcd";
	string s3 = "abd";
	string s4 = "abc";
	string s5 = "aba";

	int i = s1.compare(s2); // s1 < s2 -> returns some val < 0 (-1)
	i = s1.compare(s3); // s1 < s3 -> returns some val < 0 (-1)
	i = s1.compare(s4); // s1 = s4 -> returns 0
	i = s1.compare(s5); // s1 > s5 -> return some val > 0 (2)
	
	
#### SubString and Find-Replace
	#include <string>

	string fullname = "harsh singh"
	string name = fullname.substr(1,5);    //substr(start_index,length)
	string surname = fullname.substr(6);   //returns "singh"
	size_t found = fullname.find("a"); 
	// substring to be found can be string or character
	size_t found = fullname.find('a');

	if(found != nopos){
		cout << "Pos :" << found << endl;
	}

	found = fullname.find("a",found+3,5);  

	fullname.replace(found,1,"hello");  
