import java.util.*;

public class Demo {
    public static void main(String[] args){
        Scanner in = new Scanner(System.in);
        int n, capacity, rate;
        int size[] = new int[100];
        System.out.print("Enter the number of packets: ");
        n = in.nextInt();
        System.out.print("Enter the size of packets: ");
        for(int i=0; i<n; i++) size[i] = in.nextInt();
        System.out.print("Enter the bucket capacity: ");
        capacity = in.nextInt();
        System.out.print("Enter output rate: ");
        rate = in.nextInt();
        leakyBucket(n, rate, capacity, size);

        in.close();
    }

    public static void leakyBucket(int n, int rate, int capacity, int size[]){
       System.out.println("clock\t size\t accept\t sent\t rem");
       int accept=0, rem=0, sent=0;
       for(int i=0; i<n; i++){
            if(size[i] <= capacity){
                accept = size[i];
                if(accept <= rate){
                    sent = accept;
                    rem = 0;
                }
                else{
                    sent = rate;
                    rem = accept - rate;
                }
                System.out.println((i+1)+"\t"+size[i]+"\t"+accept+"\t"+sent+"\t"+rem);
            }
            else{
             sent = rem;
             rem=0;
             System.out.println((i+1)+"\t"+size[i]+"\tdropped\t"+sent+"\t"+rem);
            }
       }
    }

    
}
