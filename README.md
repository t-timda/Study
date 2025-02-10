#define _CRT_SECURE_NO_WARNINGS
#include <iostream>
using namespace std;

class Point {
private:
	int xpos, ypos;
public:
	void Init(int x, int y) {
		xpos = x;
		ypos = y;
	}
	void ShowPointInfo() const{
		cout << "[" << xpos << ", " << ypos << "]" << endl;
	}
};
class Circle {
private:
	Point cnt;
	int radius;
public:
	void Init(int x, int y, int r) {
		cnt.Init(x, y);
		radius = r;
	}
	void ShowCircleInfo() const{
		cout << "radius: " << radius << endl;
		cnt.ShowPointInfo();
	}
};
class Ring {
private:
	Circle crin;
	Circle crout;
public:
	void Init(int x1, int y1, int r1, int x2, int y2, int r2) {
		crin.Init(x1,y1,r1);
		crout.Init(x2, y2, r2);
	}
	void ShowRingInfo() const{
		cout << "Inner Circle Info..." << endl;
		crin.ShowCircleInfo();
		cout << "Outter Circle Info..." << endl;
		crout.ShowCircleInfo();
	}
};

int main(void) {
	Ring ring;
	ring.Init(1, 1, 4, 2, 2, 9);
	ring.ShowRingInfo();
	return 0;
}