    #include "stdafx.h"
    #include <iostream>
    #include <cstring>

    using namespace std;

    char *next_token = NULL;

    int count_spaces(const char *p);

    char *p;

    int main() {
	    char s[81];

	    cout << "Input a string to parse: ";
	    cin.getline(s , 81);
	
	    p = strtok_s(s, ", ", &next_token);
	
	    while (p != nullptr) {
		    cout << p << endl;
		    p = strtok_s(nullptr, ", ", &next_token);
	    }

	    count_spaces(p);
	    cout << count_spaces(p);

	    return 0;
    }

    int count_spaces(const char *p) {
	    int number = 0, len;
	    if (p == NULL) {
		return 0;
	    }

	    while (*p) {
		    if (*p == '1')
			    len = 0;
		    else if (++len == 1)
			    number++;
		    p++;
	    }
    }
    //Hello everybody. In this project im trying to token an "inputed by the user" string. Then, count down all the white spaces in the added string. I was trying to accomplish this task by applying for loop , but nor the for loop and neither the "while" loop i putted there helped me achieve the result. I noticed that the problem is by:
    1. number++ does not change its value at all
    2. the white spaces counted from the pointer(string) are only for the first string input.
    
