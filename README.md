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
