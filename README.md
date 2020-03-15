#include<iostream>
#include<time.h>
#include<fstream>
using namespace std;

		//Please explain what is in the int main function: int argc and char* argv
		int main(int argc, char* argv[]) {

		fstream f;
		f.open("output.txt", ios::out); //what does the ios::out mean
			clock_t startTime;
		long int freeBytes;
			int freePage;
		int freeVirtual;

			MEMORYSTATUS MemoryInfo;
			GlobalMemoryStatus(&MemoryInfo);	
		freeBytes = MemoryInfo.dwAvailPhys;
			freePage = MemoryInfo.dwAvailPageFile;
		freeVirtual = MemoryInfo.dwAvailVirtual;

		cout << "Available Physical Memory: " << MemoryInfo.dwAvailPhys << endl;
			cout << "Available Page File: " << MemoryInfo.dwAvailPageFile << endl;
	cout << "Available Virtual Memory" << MemoryInfo.dwAvailVirtual << endl;
		f << "Avaiable Physical Memory: " << MemoryInfo.dwAvailPhys << endl;
			f << "Available Page File: " << MemoryInfo.dwAvailPageFile << endl;
	f << "Available Virtual Memory" << MemoryInfo.dwAvailVirtual << endl;

		double Cache_size[15] = { 05, 0.6, 0.7, 0.8, 0.9, 0.95, 0.99, 1.0, 1.01, 1.1, 1.5 , 2, 5, 10, 50 };
	long int num_of_Bytes;

			int* num_array;

		for (int i = 0; i < 15; i++) {
			cout << "--------------------\n\n";
		cout << "Cache Size: " << Cache_size[i] << "*M\n"
			f << "--------------------\n\n";
		f << " Cache Size: " << Cache_size[i] << "*M\n";

		startTime = clock();
			num_of_Bytes = abs((int)(Cache_size[i] * (freeBytes)));

		int size = num_of_Bytes / sizeof(int);
			num_array = new int[size];

			GlobalMemoryStatus(&MemoryInfo);
				cout << "Available Physical Memory: " << MemoryInfo.dwAvailPhys << endl;
				cout << "Available Page File: " << MemoryInfo.dwAvailPageFile << endl;
			cout << "Available Virtual Memory" << MemoryInfo.dwAvailVirtual << endl;
			f << "Avaiable Physical Memory: " << MemoryInfo.dwAvailPhys << endl;
			f << "Available Page File: " << MemoryInfo.dwAvailPageFile << endl;
				f << "Available Virtual Memory" << MemoryInfo.dwAvailVirtual << endl;
		}

		for (int i = 0; i < size; i++) {
			num_array[i] = i;
		}
			for (int i = 0; i < size; i++) {
				num_array[i] += i;
		}

	delete[] num_array;
		cout << "Time elapsed: " << ((double)(clock() - startTime) / (double)CLOCKS_PER_SEC) << "seconds " << endl;
			f << "Time elapsed: " << ((double)(clock() - startTime) / (double)CLOCKS_PER_SEC) << "seconds " << endl;
	}
		system("pause");
	return 0;
}//The f's stand for file
//Fix my code so it is more efficient, readable, and understandable
