# Codeforces-Exercise
Inverting a number and get the min
import java.util.ArrayList;
public class CodeForce01 {
    
    public int invertingNumber(int number) {
        int result = 0;
        ArrayList<Integer> num = new ArrayList<>(); 
        while(number > 0) {
            int element = number % 10;
            inverting(num, element);
            number /= 10;
        }
        
        for(int i = num.size()-1; i >= 0; i--) {
            int component = num.get(i);
            result += component * Math.pow(10, i);
        }
        return result;
    }
    
    private void inverting(ArrayList<Integer> num, int element) {
        if(element < 5) {
            num.add(element);
        }else {
            int other = 9 - element;
            num.add(other);
        }
    }
