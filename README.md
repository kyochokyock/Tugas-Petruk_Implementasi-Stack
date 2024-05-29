Kelompok 9

Maura Hellena (2317051105)

Muhammad Ghozi Pratama (2317051041)

//Meyta Zaskiya (2357051006) Evaluasi Postfix dan Operasi Aritmatika

double doOperation(double a, double b, string op);
double evaluateOperation(vector<string> postfix);

double evaluateOperation(vector<string> postfix){
    vector<string> op = {"+", "-", "*", "/", "%"};
    stack<double> result;
    vector<string>::iterator i = postfix.begin();
    double a,b,c;
    string temp;

    while(i != postfix.end()){
        if(checkString(*i,op)){
            a = result.top();
            result.pop();
            b = result.top();
            result.pop();
            temp = *i;
            c = doOperatio(a,b,temp);
            result.push(c);
         } else {
             result.push(strtod((*i).c_str(),NULL));
         }
         i++;
  }
  return result.top();
}

double doOperation(double a, double b, string op){
    double result;
    if(op == "+"){
        result = b + a;
    } else if(op == "-"){
        result = b - a;
    } else if(op == "/"){
        result = b / a;
    } else if(op == "%"){
        result = (int) b % (int) a;
    }
    return result;
}
            
