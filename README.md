# Hilo_Num-Letra

package in_class;

import java.util.logging.*;


/**
 *
 * @author Martha Garcia
 * NOTA: Agregue el metodo sleep para que ambos hilos se
 * imprimieran a consola lo mas unifomemente posible
 */
public class testHiloNumeroLetra {

    public static void main(String[] args) {
        

        HiloNumerosLetras h1 = new HiloNumerosLetras(1);
        HiloNumerosLetras h2 = new HiloNumerosLetras(2);

        Thread t1 = new Thread(h1);
        Thread t2 = new Thread(h2);
        
        t1.start();
        t2.start();
        
     

    }
}

class HiloNumerosLetras implements Runnable {

    private int type;
    private int i;
    private char c;

    public HiloNumerosLetras(int type) {
        this.type = type;
    }

    @Override
    public void run() {

        while (true) {
            switch (type) {
                case 1:
                    for (i=1; i < 31; i++) {
                        String namen = Thread.currentThread().getName();
                        System.out.printf("%s:%d\n", namen, i);
                        try {
                            Thread.sleep(10);
                        } catch (InterruptedException ex) {
                            Logger.getLogger(HiloNumerosLetras.class.getName()).log(Level.SEVERE, null, ex);
                        }
                    }
                    break;

                case 2:
                    for (c = 'A'; c <= 'Z'; c++) {
                        String namel = Thread.currentThread().getName();
                        System.out.println("" + namel + ":" + c);
                        try {
                            Thread.sleep(12);
                        } catch (InterruptedException ex) {
                            Logger.getLogger(HiloNumerosLetras.class.getName()).log(Level.SEVERE, null, ex);
                        }
                    }
                    break;
            }
//            break;
        }
       
    }
    
}
