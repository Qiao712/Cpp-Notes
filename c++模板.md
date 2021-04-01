````c++
#include <iostream>
using namespace std;

template<typename T> class A;
template<typename T> class B;

//一个模板类 
template<typename T>
class A{
	friend B<char>;//声明用char实例化的B是A的友元类
	friend B<T>;
	
	template<typename X> friend class B;//B的所有实例都是A的友元类 
public:
	//它的一个模板成员函数 
	template<typename X> void Fuck(X x){
		cout<<x<<endl;
	}
	
	
	T hello();
};

//类外定义函数 
template<typename T>
T A<T>::hello(){
	cout<<"hello"<<endl;
}



template<typename T = int> 
class B{

};


extern template class A<int>;//实例化声明 
template class A<int>;//实例化定义 

int main(){
	A<int> a;
	a.Fuck<double>(712); 
	a.hello();
	
	B<> b;//使用默认实参 
} 
```