# 实验目的：

1.掌握字符串String及其方法的使用  
2.掌握异常处理结构


业务要求：  
-----
利用已学的字符串处理知识编程完成《长恨歌》古诗的整理对齐工作，写出功能函数，并运行。  
达到如下功能：  

每7个汉字加入一个标点符号，奇数时加“，”，偶数时加“。”  
允许提供输入参数，统计古诗中某个字或词出现的次数  
考虑操作中可能出现的异常，在程序中设计异常处理程序  
  
输入：  
汉皇重色思倾国御宇多年求不得杨家有女初长成养在深闺人未识天生丽质难自弃一朝选在君王侧回眸一笑百媚生六宫粉黛无颜色春寒赐浴华清池温泉水滑洗凝脂侍儿扶起娇无力始是新承恩泽时云鬓花颜金步摇芙蓉帐暖度春宵春宵苦短日高起从此君王不早朝承欢侍宴无闲暇春从春游夜专夜后宫佳丽三千人三千宠爱在一身金屋妆成娇侍夜玉楼宴罢醉和春姊妹弟兄皆列士可怜光采生门户遂令天下父母心不重生男重生女骊宫高处入青云仙乐风飘处处闻缓歌慢舞凝丝竹尽日君王看不足渔阳鼙鼓动地来惊破霓裳羽衣曲九重城阙烟尘生千乘万骑西南行<未完，待续>  
输出：  
汉皇重色思倾国，御宇多年求不得。  
杨家有女初长成，养在深闺人未识。  
天生丽质难自弃，一朝选在君王侧。  
回眸一笑百媚生，六宫粉黛无颜色。  
春寒赐浴华清池，温泉水滑洗凝脂。  
侍儿扶起娇无力，始是新承恩泽时。  
云鬓花颜金步摇，芙蓉帐暖度春宵。  
春宵苦短日高起，从此君王不早朝。  
…………  
  
注意： 输入的内容，利用main方法中的args数组传递   

核心代码
-

    public static void main(String args[]) {
		if (args.length == 0)
			throw new IllegalArgumentException("Please input 长恨歌");
		String res = args[0];
		for (int i = 0; i < res.length(); i++) {
			char c = res.charAt(i);
			System.out.print(c);
			if ((i + 1) % 14 == 0) {
				System.out.println("。");
				continue;
			}
			if ((i + 1) % 7 == 0)
				System.out.print(",");
		}
 拆分格式在7个字后加‘，’14个字后加‘。’
 
    System.out.println("请输入想要查找的字符串或者字符：");
        Scanner scanner=new Scanner(System.in);
        String find=scanner.nextLine();
        countString(res,find);
 创建Scanner类查询输入的需要查找的字符串或者字符进行扫描记录
    
    private static void countString(String str,String s){
    	int count=0;
    	while(str.indexOf(s)!=-1){
    		str=str.substring(str.indexOf(s)+1,str.length());
    		count++;
    	}
    	System.out.println(s+"——出现的次数为："+count+"次");
    }
  统计扫描到的所需查找的字符串或者字符进行总计次数
  
  运行结果
  -
  
    汉皇重色思倾国,御宇多年求不得。
    杨家有女初长成,养在深闺人未识。
    天生丽质难自弃,一朝选在君王侧。
    回眸一笑百媚生,六宫粉黛无颜色。
    春寒赐浴华清池,温泉水滑洗凝脂。
    侍儿扶起娇无力,始是新承恩泽时。
    云鬓花颜金步摇,芙蓉帐暖度春宵。
    春宵苦短日高起,从此君王不早朝。
    承欢侍宴无闲暇,春从春游夜专夜。
    后宫佳丽三千人,三千宠爱在一身。
    金屋妆成娇侍夜,玉楼宴罢醉和春。
    姊妹弟兄皆列士,可怜光采生门户。
    遂令天下父母心,不重生男重生女。
    骊宫高处入青云,仙乐风飘处处闻。
    缓歌慢舞凝丝竹,尽日君王看不足。
    渔阳鼙鼓动地来,惊破霓裳羽衣曲。
    九重城阙烟尘生,千乘万骑西南行。
    请输入想要查找的字符串或者字符：
    佳丽
    佳丽——出现的次数为：1次

  实验心得
  -
  通过这次实验切实体会到了运用在格式编写与调控上有诸多的方便之处，带来了很好的作业效率。让我们大大提高了实际运用与代码联系的动手能力，在查询7位字符后加入‘，’和14位字符后加入‘。’通过String args[]数组参数的length长度判断。加个Scanner类进行扫描输入的字符串或者字符。countString来进行统计记录所查找的字符串或字符indexof索引。还需要多加练习才能熟能生巧，查询的时候也有一个bug在没有回车时会有查询结果误差。还需要不断调试，得到完整的程序。异常的处理还需要多加练习找到解决的方案。谢谢阅览。
