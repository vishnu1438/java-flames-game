import java.util.*;
public class Main
{
	public static void main(String[] args) {
		Scanner sc=new Scanner(System.in);
		System.out.println("Enter first name :");
		String s1=sc.nextLine();
		System.out.println();
		System.out.println("Enter second name :");
		String s2=sc.nextLine();
		
		s1 = s1.replaceAll(" ", "").toLowerCase();
		s2 = s2.replaceAll(" ", "").toLowerCase();
		
		String res=" ";
		char []sa=s1.toCharArray();
		char []sd=s2.toCharArray();
		int arr[]={1,1,1,1,1,1};
		
		for(int i=0;i<sa.length;i++){
		    for(int j=0;j<sd.length;j++){
		        if(sa[i]==sd[j]){
		            sa[i]=0;
		            sd[j]=0;
		        }
		    }
		}
		int n=0;
		for(int i=0;i<sa.length;i++){
		    if(sa[i]!=0)
		    n++;
		}
		int m=0;
		for(int j=0;j<sd.length;j++){
		    if(sd[j]!=0)
		    m++;
		}
		int k=n+m;
		
		if(k==0){
		    System.out.println("enter valid names");
		    return;
		}
		int sum=0;
		int index=0;
		int ind=0;
		int arr_length=Arrays.stream(arr).sum();
		while(arr_length>1){
		    sum+=arr[index];
		    
		    if(sum==k){
		        arr[index]=0;
		        sum=0;
		        index=0;
		    }
		   else  if(index==5){
		        index=0;
		    }
		    else{
		    index++;
		    }
		    
		    arr_length = Arrays.stream(arr).sum();
		    
		    for(int i=0;i<arr.length;i++){
		        if(arr[i]==1){
		            ind=i;
		        }
		    }
		}
		if(ind==0){
		    System.out.println("F-Friends");
		}
		else if(ind==1){
		    System.out.println("L-Lovers");
		}
		else if(ind==2){
		    System.out.println("A-Affectionate");
		}
		else if(ind==3){
		   System.out.println("M-Marriage");
		}
		else if(ind==4){
		    System.out.println("E-Enemies");
		}
		else if(ind==5){
		    System.out.println("s- Siblings");
		}
		
	}
}
