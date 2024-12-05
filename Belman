import java.util.*;

public class BellmanFord {
    static Scanner in = new Scanner(System.in);
    public static void main(String[] args) {
        int V, E=1, checkNegative = 0;
        int w[][] = new int[100][100];
        int edge[][] = new int[100][100];
        System.out.print("Enter the no of vertives: ");
        V = in.nextInt();
        System.out.println("Enter the weight matrix:");
        for(int i=1; i<=V; i++) for(int j=1; j<=V; j++){
            w[i][j] = in.nextInt();
            if(w[i][j] != 0){
                edge[E][0] = i;
                edge[E++][1] = j;
            } 
        }
        checkNegative = bellmanFord(w, V, E, edge);
        if(checkNegative == 1) System.out.println("no -ve weight cycle");
        else System.out.println("-ne weight cycle exist");
    }
    public static int bellmanFord(int w[][], int V, int E, int edge[][]){
        int u, v, S, flag=1;
        int distance[]  = new int[100];
        int parent[] = new int[100];
        for(int i=1; i<=V; i++){
            distance[i] = 999;
            parent[i] = -1;
        }
        System.out.print("Enter the source vertex: ");
        S = in.nextInt();
        distance[S] = 0;
        for(int i=1; i<=V; i++){
            for(int k=1; k<=E; k++){
                u = edge[k][0];
                v = edge[k][1];
                if(distance[u] + w[u][v] < distance[v]){
                    distance[v] = distance[u] + w[u][v];
                    parent[v] = u;
                }
            }
        }
        for(int k=1; k<=E; k++){
            u = edge[k][0];
            v = edge[k][1];
            if(distance[u] + w[u][v] < distance[v]){
                flag=0;
            }

        }
        if(flag == 1)
            for(int i=1; i<=V; i++)
                System.out.println("vertex "+i+" -> cost = "+distance[i]+" parent = "+parent[i]);
                return flag;
            
        
    }
}
