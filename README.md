# Week-6
# Task 1
#include <iostream>

using namespace std;

class Circle {
private:
    double radius;

public:
    
    void setRadius(double r) {
        radius = r;
    }

    
    double getRadius() const {
        return radius;
    }

  
    Circle operator+(const Circle& other) {
        Circle result;
        result.radius = this->radius + other.radius;
        return result;
    }
};

int main() {
    
    Circle c1, c2, c3;

    // Setting radius for c1 and c2
    c1.setRadius(5.0);
    c2.setRadius(3.5);

    
    c3 = c1 + c2;
    cout << "The radius of c3 is: " << c3.getRadius() << endl;

    return 0;
}
# Task 2
#include <iostream>

using namespace std;

class Complex {
private:
    double real;
    double imaginary;

public:
    friend istream& operator>>(istream& in, Complex& c) {
        cout << "Enter the real part: ";
        in >> c.real;
        cout << "Enter the imaginary part: ";
        in >> c.imaginary;
        return in;
    }

    friend ostream& operator<<(ostream& out, const Complex& c) {
        out << c.real << " + " << c.imaginary << "i";
        return out;
    }
};

int main() {
    Complex com1;
    cin >> com1;
    cout << "The complex number is: " << com1 << endl;
    return 0;
}
