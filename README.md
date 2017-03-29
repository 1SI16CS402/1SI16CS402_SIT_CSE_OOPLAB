# 1SI16CS402_SIT_CSE_OOPLAB



#include <iostream>
#include <string>
using namespace std;

//Abstract Class
class Polygon
{
	protected:
		int num_sides;
		double area;
		string name;
	public:
		void show_sides_area();
		virtual void calc_area()=0; //pure virtual function
};

class Triangle : public Polygon
{
	private:
		double base, height;
	public:
		Triangle(double,double);
		void calc_area();
};

class Square : public Polygon
{
	private:
		double side_length;
	public:
		Square(double);
		void calc_area();
};

void Polygon::show_sides_area()
{
	cout<<name<<" "<<num_sides<<" sides, area = "<<area<<endl;
}

Triangle::Triangle(double base_var, double height_var):
		 base(base_var),  height(height_var)
{
    name = "Triangle";
    num_sides = 3;
	cout<<"Triangle constructor called."<<endl;
}

void Triangle::calc_area()
{
	area = 0.5* base*height;
}


Square::Square (double side_length_var):
		 side_length(side_length_var)
{
    name = "Square";
    num_sides = 4;

	cout<<"Square constructor called."<<endl;
}

void Square::calc_area()
{
	area = side_length * side_length;
}

int main()
{
	Triangle triangle1(3.5, 2);
	Square square1(2.5);

	triangle1.calc_area();
	triangle1.show_sides_area();
	square1.calc_area();
	square1.show_sides_area();

	return (0);
}





#include <iostream>
using namespace std;
class base {
    int i, j;
    public:
    void set(int a, int b) { i=a; j=b; }
    void show() { cout << i << " " << j << "\n"; }
};

class derived : public base {
    int k;
    public:
    derived(int x) { k=x; }
    void showk() { cout << k << "\n"; }
};


int main()
{
    derived ob(3);
    ob.set(1, 2); // access member of base
    ob.show(); // access member of base
    ob.showk(); // uses member of derived class
    return 0;
}

