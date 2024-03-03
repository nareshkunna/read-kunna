Source Code: 
import java.util.*; 
class crc 
{ 
void div(int a[],intk) 
{ 
intgp[]={1,0,0,0,1,0,0,0,0,0,0,1,0,0,0,0,1}; 
int count=0; 
for(int i=0;i<k;i++) 
{ 
if(a[i]==gp[0]) 
{ 
for(int j=i;j<17+i;j++) 
{ 
a[j]=a[j]^gp[count++]; 
} 
count=0; 
} 
} 
} 
public static void main(String args[]) 
{ 
int a[]=new int[100]; 
int b[]=new int[100]; 
int len,k; 
crc ob=new crc(); 
System.out.println("Enter the length of Data Frame:"); 
Scanner sc=new Scanner(System.in); 
len=sc.nextInt(); 
int flag=0; 
System.out.println("Enter the Message:"); 
for(int i=0;i<len;i++) 
{ a[i]=sc.nextInt(); 
} 
for(int i=0;i<16;i++) 
{ a[len++]=0; 
} 
k=len-16; 
for(int i=0;i<len;i++) 
{ b[i]=a[i]; 
} 
ob.div(a,k); 
for(int i=0;i<len;i++) 
a[i]=a[i]^b[i]; 
System.out.println("Data to be transmitted: ");
for(int i=0;i<len;i++) 
{ 
System.out.print(a[i]+" "); 
} 
System.out.println(); 
System.out.println("Enter the Reveived Data: "); 
for(int i=0;i<len;i++) 
{ 
a[i]=sc.nextInt(); 
} 
ob.div(a, k); 
for(int i=0;i<len;i++) 
{ 
if(a[i]!=0) 
{ 
flag=1; 
break; 
} 
} 
if(flag==1) 
System.out.println("error in data"); 
else 
System.out.println("no error"); 
} 
}




Source Code: 
import java.util.Scanner; 
public class BellmanFord 
{ 
private int D[]; 
private intnum_ver; 
public static final int MAX_VALUE = 999; 
public BellmanFord(int n) 
{ 
this.n=n; 
D = new int[n+1]; 
} 
public void shortest(int s,int A[][]) 
{ 
for (inti=1;i<=n;i++) 
{ 
D[i]=MAX_VALUE; 
} 
D[s] = 0; 
for(int k=1;k<=n-1;k++) 
{ 
for(inti=1;i<=n;i++) 
{ 
for(intj=1;j<=n;j++) 
{ 
} 
} 
} 
for(int i=1;i<=n;i++) 
{ 
if(A[i][j]!=MAX_VALUE) 
{ 
if(D[j]>D[i]+A[i][j]) 
D[j]=D[i]+A[i][j]; 
} 
for(intj=1;j<=n;j++) 
{ 
if(A[i][j]!=MAX_VALUE) 
{ 
if(D[j]>D[i]+A[i][j]) 
{ 
System.out.println("The Graph contains negative egde cycle"); 
return; 
} 
} 
} 
} 
for(int i=1;i<=n;i++) 
{ 
System.out.println("Distance of source " + s + " to "+ i + " is " + D[i]); 
} 
} 
public static void main(String[ ] args) 
{ 
intn=0,s; 
Scanner sc = new Scanner(System.in); 
System.out.println("Enter the number of vertices");
n = sc.nextInt(); 
int A[][] = new int[n+1][n+1]; 
System.out.println("Enter the Weighted matrix"); 
for(int i=1;i<=n;i++) 
{ 
for(intj=1;j<=n;j++) 
{ 
A[i][j]=sc.nextInt(); 
if(i==j) 
{ 
A[i][j]=0; 
continue; 
} 
if(A[i][j]==0) 
{ 
A[i][j]=MAX_VALUE; 
} 
} 
} 
System.out.println("Enter the source vertex"); 
s=sc.nextInt(); 
BellmanFord b = new BellmanFord(n); 
b.shortest(s,A); 
sc.close(); 


import java.util.*; 
public class leaky 
{ 
static int min(int x,int y) 
{ 
if(x<y) 
return x; 
else 
return y; 
} 
public static void main(String[] args) 
{ 
int drop=0,mini,nsec,cap,count=0,i,process; 
int inp[]=newint[25]; 
Scanner sc=new Scanner(System.in); 
System.out.println("Enter The Bucket Size\n"); 
cap= sc.nextInt(); 
System.out.println("Enter The Operation Rate\n"); 
process= sc.nextInt(); 
System.out.println("Enter The No. Of Seconds You Want To Stimulate\n"); 
nsec=sc.nextInt(); 
for(i=0;i<nsec;i++) 
{ 
sec"); 
System.out.print("Enter The Size Of The Packet Entering At "+ i+1 +" 
inp[i] = sc.nextInt();
} 
System.out.println("\nSecond | Packet Recieved | Packet Sent | Packet Left | 
Packet Dropped|\n"); 
//System.out.println("-------------------------------------------------------------------- ----\n"); 
for(i=0;i<nsec;i++) 
{ 
count+=inp[i]; 
if(count>cap) 
{  
drop=count-cap; 
count=cap; 
} 
System.out.print(i+1); 
System.out.print("\t\t"+inp[i]); 
mini=min(count,process); 
System.out.print("\t\t"+mini); 
count=count-mini; 
System.out.print("\t\t"+count); 
System.out.print("\t\t"+drop); 
drop=0; 
System.out.println(); 
} 
for(;count!=0;i++) 
{ 
if(count>cap) 
{ 
drop=count-cap; 
count=cap; 
} 
System.out.print(i+1); 
System.out.print("\t\t0"); 
mini=min(count,process); 
System.out.print("\t\t"+mini); 
count=count-mini; 
System.out.print("\t\t"+count); 
System.out.print("\t\t"+drop); 
System.out.println(); 
} 
} 
}
