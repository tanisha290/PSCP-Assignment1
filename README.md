# PSCP-Assignment1

#Basic Math

Q1)Count Digigts
// Function to count the number of digits in n that evenly divide n

    int evenlyDivides(int n) {
        int x=n;
        
        vector<int>s;
        while(x>0){
            int d=x%10;
            s.push_back(d);
            x/=10;
        }
        int ct=0;
        for(auto it:s){
            if(it!=0 && n%it==0){
                ct++;
            }
        }
        return ct;
    }

Q2)Reverse Digits
      
      int reverseDigits(int n) {

        int x=n;
        string s;
        while(x){
            int d=x%10;
            char c='0'+d;
            if(c!='0'){
                s.push_back(c);
            }
            x/=10;
        }
        int y=stoi(s);
        return y;
    }

Q3) Palindrome Numbers
  
    int isPallindrome(long long int N){
        int x=N;
        string s;
        while(x){
            int y=x%2;
            s.push_back(y+'0');
            x/=2;
        }
        string a=s;
        reverse(s.begin(),s.end());
        if(s==a){
            return 1;
        }else{
            return 0;
        }
    }
  
4) Armstrong Numbers

        bool armstrongNumber(int n) {
        int x=n;
        int sum=0;
        while(x){
            int y=x%10;
            sum+= pow(y,3);
            x/=10;
        }
        if(sum==n){
            return true;
        }else{
            return false;
        }
        }
6) All divisors of a Number
        

       void print_divisors(int n) {
        set<int>v;
        for(int i=1;i*i<=n;i++){
            if(n%i==0){
                v.insert(i);
                v.insert(n/i);
            }
        }
        for(auto k:v){
            cout<<k<<" ";
        }
        }
8) Prime Number

        bool isPrime(int n) {
        if(n==1){
            return 0;
        }
        for(int i=2;i*i<=n;i++){
            if(n%i==0){
                return 0;
            }
        }
        return 1;
          }
10) GCD

        int gcd(int a, int b) {
        if(a==0){
            return b;
        }
        if(b==0){
            return a;
        }
        if(a==b){
            return b;
        }
        if(a>b) return gcd(a-b,b);
        else return gcd(a,b-a);
        }

   #STL Practice Problems
1. Vector Sort

        int main() {
          int n;
          cin>>n;
          vector<int>v(n);
          for(int i=0;i<n;i++){
              cin>>v[i];
          }
          sort(v.begin(),v.end());
          for(int i=0;i<n;i++){
              cout<<v[i]<<" ";
          }
             
          return 0;
        }

2. Vector Erase


       int main() {
        int n;
        cin>>n;
        vector<int>v(n);
        for(int i=0;i<n;i++){
            cin>>v[i];
        }
        int x;cin>>x;
        int a,b;
        cin>>a>>b;
         v.erase(v.begin()+a-1,v.begin()+b);  
         cout<<v.size()<<endl;
         for(int x:v){
            cout<<x<<" ";
         }
        return 0;
        
          }

4. Lower Bound STL

       int main() {
        int n;
        cin>>n;
        vector<int>v(n);
        for(int i=0;i<n;i++){
            cin>>v[i];
        }
        int x;cin>>x;
        for(int i=0;i<x;i++) {
            int y;cin>>y;
            auto found=lower_bound(v.begin(),v.end(),y);
            if(*found==y){
                cout<<"Yes"<<" "<<found-v.begin()+1<<endl;
            }else{
                 cout<<"No"<<" "<<found-v.begin()+1<<endl;
               
            }
        } 
        return 0;
        }
6. Sets STL

       int main() {
        int n;
        cin>>n;
        set<int>s;
        for(int i=0;i<n;i++){
            int a,b;
            cin>>a>>b;
            if(a==1){
                s.insert(b);
            }else if(a==2){
                s.erase(b);
            }else if(a==3){
                if(s.find(b)==s.end()){
                    cout<<"No"<<endl;
                }else{
                    cout<<"Yes"<<endl;
                }
            }
        }
        return 0;
        }

8. Maps STL

        int main() {
        int n;
        cin>>n;
        map<string,int>m;
        for(int i=0;i<n;i++){
            int a;string s;
            cin>>a>>s;
            if(a==1){
                int b;cin>>b;
                m[s]+=b;
            }else if(a==2){
                m.erase(s);
            }else if(a==3){
                if(m.find(s)==m.end()){
                    cout<<0<<endl;
                }else{
                    cout<<m[s]<<endl;
                }
            }
        }   
        return 0;
        }

9. Deque STL

       void printKMax(int arr[], int n, int k){
	    deque<int>d(arr,arr+k);
        auto max=max_element(d.begin(),d.end());
        cout<<*max<<" "; 
    
        if(*max==d.front()){
            max=max_element(d.begin()+1,d.end());
        }
        d.pop_front();  
        for(int i=k;i<n;++i){
            d.push_back(arr[i]);
            if(arr[i]>=*max) {
                max=d.end()-1;              
            }
            cout<<*max<<" ";
            if(max==d.begin()){ 
                max=max_element(d.begin()+1,d.end());
            }  
            d.pop_front();
        } 
        }
#Basic Ad hoc Problems
1. Tsort


        int main() {
    	int n;
    	cin>>n;
    	vector<int>v(n);
    	for(int i=0;i<n;i++){
    	    cin>>v[i];
    	}
    	sort(v.begin(),v.end());
    	for(int i=0;i<n;i++){
    	    cout<<v[i]<<endl;
    	}
        }

2. Fruits

       int main() {
        int t;cin>>t;
        while(t--){
            int n,m,k;cin>>n>>m>>k;
            int diff=abs(n-m);
            if(diff==0){
                cout<<0<<endl;
                continue;
            }
            if(k>=diff){
                cout<<0<<endl;
            }else{
                cout<<diff-k<<endl;
            }
        }

        }
