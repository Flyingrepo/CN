
public class SlidingWindow {
    private int windowsize;
    private int[] frames;
    private boolean[] ack;
    public SlidingWindow(int windowsize, int framecount){
        this.windowsize = windowsize;
        this.frames = new int[framecount];
        this.ack = new boolean[framecount];
        for(int i=0; i<framecount; i++){
            frames[i] = i;
            ack[i] = false;
        }
    }

    public void sendframes(){
        int sendindex = 0;
        while(sendindex < frames.length){
            for(int i=0; i<windowsize && (sendindex + i) <frames.length; i++){
                System.out.println("Sending Frames: "+frames[sendindex + i]);
            }
            for(int i=0; i<windowsize && (sendindex + i) <frames.length; i++){
                ack[sendindex + i] = receiveack(sendindex + i);
            }
            while(sendindex < frames.length && ack[sendindex]){
                sendindex++;
            }
        }
    }
    private boolean receiveack(int frame){
        System.out.println("Recieving ack for frame: "+frame);
        return true;
    }
    public static void main(String[] args) {
        int windowsize = 4;
        int framecount = 10;
        SlidingWindow swp = new SlidingWindow(windowsize, framecount);
        swp.sendframes();
    }
}
