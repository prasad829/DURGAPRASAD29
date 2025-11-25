# multithreading:

package nov25;



import java.util.Scanner;



public class OMRKing {

 	public static void main(String args\[]) {



 		// object creation for thread classes

 		Numeric num = new Numeric();

 		Alpha alp = new Alpha();



 		// start the thread

 		num.start();

 		alp.start();



 		// get the name of the thread

 		System.out.println("Number Thread : " + num.getName());

 		System.out.println("Alphabets Thread : " + alp.getName());



 		// get the priority

 		System.out.println("Number Thread : " + num.getPriority());

 		System.out.println("Alphabets Thread : " + alp.getPriority());



 		// check the state of the thread

 		System.out.println("Number Thread : " + num.getState());

 		System.out.println("Alphabets Thread : " + alp.getState());

 

 		// checking the current thread

 		System.out.println(Thread.currentThread().getName());



 		// set the name to thread

 		num.setName("Jayanth");

 		alp.setName("Karthick");



 		// check the state of the thread

 		System.out.println("Number Thread : " + num.getState());

 		System.out.println("Alphabets Thread : " + alp.getState());



 		// checking whether its alive or not



 		if (num.isAlive()) {

 		System.out.println("Jayanth thread is Alive");

 		} else {

 			System.out.println("Jayanth Thread is dead");

 		}



 		if (alp.isAlive()) {

 		System.out.println("Karthick thread is Alive");

 		} else {

 		System.out.println("Karthiread is dead");

 		}



 	}



}



class Numeric extends Thread {

    public void run() {

        for (int i = 1; i <= 10; i++) {

            System.out.println("Numeric Thread : " + i);

        }

    }

}



class Alpha extends Thread {

    public void run() {

        char ch = 'A';

        for (int i = 0; i < 26; i++) {

            System.out.println("Alpha Thread   : " + ch);

            ch++;

        }

    }

}



class Numeric extends Thread {

    public void run() {

        for (int i = 1; i <= 10; i++) {

            System.out.println("Numeric Thread : " + i);

        }

    }

}



class Alpha extends Thread {

    public void run() {

        char ch = 'A';

        for (int i = 0; i < 26; i++) {

            System.out.println("Alpha Thread   : " + ch);

            ch++;

        }

    }

}



public class OMRKing {

    public static void main(String\[] args) {



        Numeric num = new Numeric();

        Alpha alp = new Alpha();



        try {

            // Start numeric thread and wait till it finishes

            num.start();

            num.join();   // main waits here till num is done



            // Now start alphabet thread and wait till it finishes

            alp.start();

            alp.join();   // main waits here till alp is done



        } catch (InterruptedException e) {

            System.out.println("Thread interrupted: " + e);

        }



        System.out.println("Both threads finished. Main thread exiting.");

    }



}

# string:

package string;



public class Solution

{

public static void main(String\[] args)

{

 	String s=new String("Sathyabama");

 	s.concat("college");

 

 

 	StringBuffer s1=new StringBuffer("Sathyabama");

 	s1.append("college");

 



 	StringBuilder s2=new StringBuilder("Sathyabama");

 	s2.append("college");

 

 

 	System.out.println(s);

 	System.out.println(s1);

 	System.out.println(s2);



 

}

}

# thread without join:

class Numeric extends Thread {

    public void run() {

        for (int i = 1; i <= 10; i++) {

            System.out.println("Numeric Thread : " + i);

        }

    }

}



class Alpha extends Thread {

    public void run() {

        char ch = 'A';

        for (int i = 0; i < 26; i++) {

            System.out.println("Alpha Thread   : " + ch);

            ch++;

        }

    }

}



public class WithoutJoinDemo {

    public static void main(String\[] args) {



        Numeric num = new Numeric();

        Alpha alp = new Alpha();



        // Both start together – output will be mixed / not stable

        num.start();

        alp.start();



        System.out.println("Main thread finished (child threads may still be running)");

    }

}

# thread with join:

class Numeric extends Thread {

    public void run() {

        for (int i = 1; i <= 10; i++) {

            System.out.println("Numeric Thread : " + i);

        }

    }

}



class Alpha extends Thread {

    public void run() {

        char ch = 'A';

        for (int i = 0; i < 26; i++) {

            System.out.println("Alpha Thread   : " + ch);

            ch++;

        }

    }

}



public class WithJoinDemo {

    public static void main(String\[] args) {



        Numeric num = new Numeric();

        Alpha alp = new Alpha();



        try {

            // Start numeric thread and wait till it finishes

            num.start();

            num.join();   // main waits here till num is done



            // Now start alphabet thread and wait till it finishes

            alp.start();

            alp.join();   // main waits here till alp is done



        } catch (InterruptedException e) {

            System.out.println("Thread interrupted: " + e);

        }



        System.out.println("Both threads finished. Main thread exiting.");

    }

}

# string buffer string builder:

package nov19;

import java.util.Arrays;

public class array {

 	public static void main (String args\[]) {

 		String s = "Sathyabama";

 		StringBuffer s1= new StringBuffer("Sathyabama");

 		StringBuilder s2=new StringBuilder ("Sathyabama");

 		s = s.concat(" college");

 		s.concat(" chennai");

 		s1 = s1.append(" college");

 		s1.append(" chennai");

 		s2 = s2.append(" college");

 		s2.append(" chennai");

 		System.out.println(s);

 		System.out.println(s1);

 		System.out.println(s2);

 		System.out.println(s.toUpperCase());

 		System.out.println(s.toLowerCase());

 		String ss= " Sathyabama";

 		System.out.println(ss.trim());

 		System.out.println(s.startsWith("Sa"));

 		System.out.println(s.endsWith("n"));

 		System.out.println(s.charAt(3));

 		System.out.println(s.length());

 	}

}

