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

        Sample Input : 
        Utsav 1 2 3
        Chokshi 1 7 8
        
        
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

