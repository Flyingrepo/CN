import java.util.*;

public class CRC {
    static String msg;
    static String genpoly = "1011";
    static char t[] = new char[100];
    static char cs[] = new char[100];
    static char g[] = new char[100];
    static int mlen, glen, i, x, c, test, flag=0;
    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
            System.out.print("Enter the message to be transfered: ");
            msg = in.nextLine();
            mlen = msg.length();
            for(i=0; i<mlen; i++){
                t[i] = msg.charAt(i);
            }
            System.out.println("predefined generator polynomial is "+genpoly);
            g = genpoly.toCharArray();
            glen = genpoly.length();
            for(x=mlen; x<(mlen + glen)-1; x++ ){
                t[x] = '0';
            }
            System.out.println("Zero extended msg is "+new String(t));
            crc();
            System.out.println("Checksum is "+new String(cs));
            for(x=mlen; x<(mlen + glen)-1; x++ ){
                t[x] = cs[x-mlen];
            }
            System.out.println("final codeword generated is "+new String(t));
            System.out.println("test error ");
            test = in.nextInt();
            if(test ==1){
                System.out.println("Enter the position");
                x = in.nextInt();
                t[x] = (t[x] == '0')? '1': '0';
                System.out.println("errorneous data "+new String(t));
            }
            crc();
            for(x=0; x<(glen-1); x++){
                if(cs[x] == '1'){
                    flag=1; break;
                }
            }
            if(flag==1) System.out.println("Error was detected");
            else System.out.println("no error");
            
        in.close();
    }
    public static void crc(){
        for(x=0; x<glen; x++){
            cs[x] = t[x];
        }
        do{
        if(cs[0] == '1') xor();
        for(c=0; c<glen-1; c++){
            cs[c] = cs[c+1];
        }
        cs[c] = t[x++];
    }while(x <= mlen + glen-1);
    }

    public static void xor(){
        for(c=1; c<glen; c++){
            cs[c] = (cs[c]==g[c]? '0': '1');
        }
    }
}
