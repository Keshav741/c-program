# c-program
In c program which find union and intersection of two input arrays , i have a problem in intersection part .The problem is when i print out the intersection array (I[u+z])the out put is only one number repeated , without print other intersection of 2 arrays.the part of code has the problem is at the end of the code

#include <stdio.h>
#include <stdlib.h>

int main()
{
int n,z,f ;
printf("Enter size of array\n");
scanf("%d",&n);
int a[n] ;
if(n<=20){
for(int i=0 ;i<n; i++){
    printf("Enter integer \n");
    scanf("%d", &a[i]);
}
}
for(int i=0 ;i<n; i++){
    printf("%d " ,a[i]);
}
printf("\nEnter size of the 2nd array\n");
scanf("%d",&z);
int b[z] ;
if(z<=20){
for(int i=0 ;i<z; i++){
    printf("Enter integer \n");
    scanf("%d", &b[i]);
}
}
for(int i=0 ;i<z; i++){
    printf("%d " ,b[i]);
}
for(int i=0 ; i<n ; i++){
    for(int j=i+1 ; j<n ; j++){
        if(a[i]==a[j]){
            for(int l = j; l < n; l++)
                {
                    a[l] = a[l + 1];
                }
                n--;
                j--;
            }
        }
    }
printf("\nArray1: ");
for(int i=0 ;i<n; i++){
    printf("%d " ,a[i]);
}

for(int t=0 ; t<z ; t++){
    for(int u=t+1 ; u<z ; u++){
        if(b[t]==b[u]){
            for(int l = u; l < z; l++)
                {
                    b[l] = b[l + 1];
                }
                z--;
                u--;
            }
        }
    }
printf("\nArray2: ");
for(int e=0 ;e<z; e++){
    printf("%d " ,b[e]);
}
int u[n+z] ; //union

for(int i=0;i<n;i++){
    u[i]=a[i];


}
for(int i=n ; i<(n+z)  ;i++){
    u[i]=b[i-n];
}
for(int i=0 ; i< n+z ; i++){ //remove repeated values from union
    for(int j=i+1 ; j< n+z ; j++){
        if(u[i]==u[j]){
            for(int l = j; l < z+n; l++)
                {
                    u[l] = u[l + 1];
                }
                n+z--;
                j--;
            }
        }
    }
printf("\n union is ");
for(int i=0 ; i<(n+z) ;i++){
    printf("%d ",u[i]);
}

// to get intersection .........    
int I[n+z] ; // to get intersection
for(int i=0 ; i<n ; i++ ){
    for(int j=0 ; j<z ; j++ ){
        if(a[i]==b[j]){
          for(int k=0; k<(n+z);k++){
            I[k]=a[i] ;

            }

          }

        }
    }
printf("\n intersection is ");
for(int i=0 ; i<(n+z) ;i++){

    printf("%d ",I[i]);
    }
    return 0;
}
