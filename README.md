public class Test1 {
	public int lengthOfLongestSubstring(String s) {
	     if(s==null || s.length()==0) {
	         return 0;
	     }
	     HashSet<Character> set = new HashSet<Character>();
	     int max = 0;
	     int mark = 0;
	     int runner = 0;
	     while(runner<s.length()){
	         if(set.contains(s.charAt(runner))){
	             while(s.charAt(mark)!=s.charAt(runner)){
	                 set.remove(s.charAt(mark));
	                 mark++;
	             }
	             if(max<runner-mark){
	                 max = runner-mark;
	             }
	             mark++;
	         }
	         else{
	             set.add(s.charAt(runner));
	         }
	         runner++;
	     }
	     max = Math.max(max,runner-mark);
	     return max;
	 }
}
