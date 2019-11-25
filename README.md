# quick-sort
using namespace std;
void swap(int &a,int &b)
{
    int t;
    t=a;
    a=b;
    b=t;
}
int partition(int input[],int low,int high)
{    
    int j;
     int pivot=input[low];
    int i=low-1;
    for(j=low+1;j<high;j++)
    {
         if(input[j]<pivot)
         {
              i++;
             swap(input[j],input[i]);
         }
    }
    swap(input[i+1],input[low]);
    return (i+1);
}
void qsort(int input[],int low,int high)
{ 
   int p;
    int l=low;
    int h=high;
   if(l<h)
  {
     p=partition(input,l,h);
     qsort(input,l,p-1);
     qsort(input,p+1,h);
  }
}
void quickSort(int input[], int size) {
    qsort(input,0,size-1);

}

#include<iostream>
using namespace std;
int main(){
    int n;
    cin >> n;
  
    int *input = new int[n];
    
    for(int i = 0; i < n; i++) {
        cin >> input[i];
    }
    
    quickSort(input, n);
    for(int i = 0; i < n; i++) {
        cout << input[i] << " ";
    }
    
    delete [] input;

}


