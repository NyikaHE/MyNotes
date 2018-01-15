/*
进制转换16进制到8进制
思路：将16进制转化成2进制再进一步转化成8进制
@auther HE
2017/12/26
*/
#include<iostream>
#include<string>
#include<stack>
using namespace std;

struct B{   //定义结构体存放四位2进制
  int a;
  int b;
  int c;
  int d;
};

void TF(string H){    //转化过程
  B L[H.length()];
  stack<int> ss;
  stack<string> sc;
  string O;
  int i,h;
  for(i=0;i<H.length();i++){    //将16进制数转化成4位2进制存放在数组中
    if(H[i]>='0'&&H[i]<='9'){
      h=H[i]-'0';
      L[i].a=h/8;
      L[i].b=(h%8)/4;
      L[i].c=(h%4)/2;
      L[i].d=h%2;
    }
    else{
      h=H[i]-'A'+10;
      L[i].a=h/8;
      L[i].b=(h%8)/4;
      L[i].c=(h%4)/2;
      L[i].d=h%2;
    }
  }
  for(i=0;i<H.length();i++){    //将2进制数入栈
    ss.push(L[i].a);
    ss.push(L[i].b);
    ss.push(L[i].c);
    ss.push(L[i].d);
  }
  while(!ss.empty()){       //将2进制数出栈就得到8进制
    h=0;
    h+=ss.top();
    ss.pop();
    if(!ss.empty()){
      h+=ss.top()*2;
      ss.pop();
    }
    if(!ss.empty()){
      h+=ss.top()*4;
      ss.pop();
    }
    O=h+'0';
    sc.push(O);
  }
  O="";
  while(sc.top()=="0"){     //消除字符串首部可能存在得前导0
    sc.pop();
  }
  while(!sc.empty()){     //8进制数连接到string O上
    O+=sc.top();
    sc.pop();
  }
  cout<<O<<endl;
}

int main(){
  string H[100];
  int L,i;
  cin>>L;
  for(i=0;i<L;i++){
    cin>>H[i];
  }
  for(i=0;i<L;i++){
    TF(H[i]);
  }
  return 0;
}
