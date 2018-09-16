/*作者： 海贼王
 * 功能：
 * 编写一个函数来查找字符串数组中的最长公共前缀。

如果不存在公共前缀，返回空字符串 ""。

示例 1:

输入: ["flower","flow","flight"]
输出: "fl"
示例 2:

输入: ["dog","racecar","car"]
输出: ""
解释: 输入不存在公共前缀。
说明:

所有输入只包含小写字母 a-z 。
*/
package 乐扣测试专用;

public class leetcode {

	public static void main(String[] argus) {
		
		Solution sl = new Solution();
		String ssss[] = {"aa","a"} ;
		
		System.out.println("22"+sl.longestCommonPrefix( ssss ));
	}
	
}

class Solution {
    public String longestCommonPrefix(String[] strs) {
        
        //String[] strs2 = null; 数组定义方法出错
        String strs2 = new String();
        
        int k = strs.length;
        
        if(k==0) {
        	return "";
        }else if(k==1){
            return strs[0];
        }
        
       for(int j =0;j<strs[0].length();j++){
           
           for(int i =1;i<strs.length;i++)
           {
                //先判定空元素 “”这个玩意不算空！！
        	   if(strs[i]==null||strs[i].length()==0){
                return "";
                }
                 //这里要先判定长度够不够，再取值。如果先取值的话，会出现数组越界取值的异常情况
        	   if( strs[i].length()<j+1||strs[0].charAt(j)!=strs[i].charAt(j)  )
                 {
                return strs[0].substring(j);
                }
           }
       }
        return strs[0];
    }
       
}
