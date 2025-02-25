---
title: Welcome to Quartz
---
```java
public static void main(String[] args) throws IOException {  
  
    //记录差  
    BufferedReader in=new BufferedReader(new InputStreamReader(System.in));  
    PrintWriter out=new PrintWriter(System.out);  
    int n=Integer.parseInt(in.readLine());  
    StringTokenizer st=new StringTokenizer(in.readLine());  
    int[] arr=new int[n];  
    for(int i=0;i<n;i++){  
        arr[i]=Integer.parseInt(st.nextToken());  
    }  
    int[] diff=new int[n/2];  
    for (int i = 0; i < diff.length; i++) {  
        diff[i]=arr[i]-arr[n-i-1];  
    }  
    long count=0;  
    for (int i = 0; i < diff.length; i++) {  
        if(diff[i]==0) continue;  
        count+=Math.abs(diff[i]);  
        //如果后续同号  
        if(i+1< diff.length&&diff[i] > 0 == diff[i + 1]>0){  
            diff[i+1]=Math.abs(diff[i])>Math.abs(diff[i+1])?0:diff[i+1]-diff[i];  
        }  
    }  
    out.println(count);  
    out.flush();  
    out.close();  
}
```