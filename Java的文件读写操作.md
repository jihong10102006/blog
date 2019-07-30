---
title: Java的文件读写操作
date: 2012-11-23 14:09:16
tags: CSDN迁移
---
   当我们读写文本文件的时候，采用Reader是非常方便的，比如FileReader，InputStreamReader和BufferedReader。其中最重要的类是InputStreamReader， 它是字节转换为字符的桥梁。你可以在构造器重指定编码的方式，如果不指定的话将采用底层操作系统的默认编码方式，例如GBK等。使用FileReader读取文件：

 FileReader fr = **new** FileReader("ming.txt"); 

 **int** ch = 0; 

 **while**((ch = fr.read())!=-1 ) 

 { System.out.print((**char**)ch); } 

 其中read()方法返回的是读取得下个字符。当然你也可以使用read(char[] ch,int off,int length)这和处理二进制文件的时候类似。

 事实上在FileReader中的方法都是从InputStreamReader中继承过来的。read()方法是比较好费时间的，如果为了提高效率我们可以使用BufferedReader对Reader进行包装，这样可以提高读取得速度，我们可以一行一行的读取文本，使用readLine()方法。

 BufferedReader br = new BufferedReader(new InputStreamReader(new FileInputStream("ming.txt")));  
 String data = null;  
 while((data = br.readLine())!=null)  
 {  
 System.out.println(data);   
 }

 了解了FileReader操作使用FileWriter写文件就简单了，这里不赘述。

 Eg.我的综合实例

 **[java]** [ view plain](http://blog.csdn.net/jiangxinyu/article/details/7885518#)[copy](http://blog.csdn.net/jiangxinyu/article/details/7885518#)  
   
 
  1. public class testFile { 
  2. 
  3. /** 
  4. * @param args 
  5. */ 
  6. public static void main(String[] args) { 
  7. // TODO Auto-generated method stub 
  8. //file(内存)----输入流---->【程序】----输出流---->file(内存) 
  9. File file=new File("d:/temp","addfile.txt"); 
  10. try { 
  11. file.createNewFile(); //创建文件  
  12. } catch (IOException e) { 
  13. // TODO Auto-generated catch block 
  14. e.printStackTrace(); 
  15. } 
  16. } 
  17. //向文件写入内容(输出流) 
  18. String str="亲爱的小南瓜！"; 
  19. byte bt[]=new byte[1024]; 
  20. bt=str.getBytes(); 
  21. try { 
  22. FileOutputStream in=new FileOutputStream(file); 
  23. try { 
  24. in.write(bt, 0, bt.length); 
  25. in.close(); 
  26. //boolean success=true; 
  27. //System.out.println("写入文件成功"); 
  28. } catch (IOException e) { 
  29. // TODO Auto-generated catch block 
  30. e.printStackTrace(); 
  31. } 
  32. } catch (FileNotFoundException e) { 
  33. // TODO Auto-generated catch block 
  34. e.printStackTrace(); 
  35. } 
  36. //读取文件内容 (输入流) 
  37. FileInputStream out=new FileInputStream(file); 
  38. InputStreamReader isr = new InputStreamReader(out); 
  39. while((ch = isr.read())!=-1) 
  40. { 
  41. System.out.print((char)ch); 
  42. } 
  43. } 
  44. 
  45. } 
  46. //------------------参考资料--------------------------------- 
  47. java中多种方式读文件 
  48. 1、按字节读取文件内容 
  49. 2、按字符读取文件内容 
  50. 3、按行读取文件内容 
  51. 4、随机读取文件内容 
  52. 
  53. import java.io.BufferedReader; 
  54. import java.io.File; 
  55. import java.io.FileInputStream; 
  56. import java.io.FileReader; 
  57. import java.io.IOException; 
  58. import java.io.InputStream; 
  59. import java.io.InputStreamReader; 
  60. import java.io.RandomAccessFile; 
  61. import java.io.Reader; 
  62. public class ReadFromFile { 
  63. /** 
  64. * 以字节为单位读取文件，常用于读二进制文件，如图片、声音、影像等文件。 
  65. * @param fileName 文件的名 
  66. */ 
  67. public static void readFileByBytes(String fileName){ 
  68. File file = new File(fileName); 
  69. InputStream in = null; 
  70. try { 
  71. System.out.println("以字节为单位读取文件内容，一次读一个字节："); 
  72. // 一次读一个字节 
  73. in = new FileInputStream(file); 
  74. int tempbyte; 
  75. while((tempbyte=in.read()) != -1){ 
  76. System.out.write(tempbyte); 
  77. } 
  78. in.close(); 
  79. } catch (IOException e) { 
  80. e.printStackTrace(); 
  81. return; 
  82. } 
  83. try { 
  84. System.out.println("以字节为单位读取文件内容，一次读多个字节："); 
  85. //一次读多个字节 
  86. byte[] tempbytes = new byte[100]; 
  87. int byteread = 0; 
  88. in = new FileInputStream(fileName); 
  89. ReadFromFile.showAvailableBytes(in); 
  90. //读入多个字节到字节数组中，byteread为一次读入的字节数 
  91. while ((byteread = in.read(tempbytes)) != -1){ 
  92. System.out.write(tempbytes, 0, byteread); 
  93. } 
  94. } catch (Exception e1) { 
  95. e1.printStackTrace(); 
  96. } finally { 
  97. if (in != null){ 
  98. try { 
  99. in.close(); 
  100. } catch (IOException e1) { 
  101. } 
  102. } 
  103. } 
  104. } 
  105. /** 
  106. * 以字符为单位读取文件，常用于读文本，数字等类型的文件 
  107. * @param fileName 文件名 
  108. */ 
  109. public static void readFileByChars(String fileName){ 
  110. File file = new File(fileName); 
  111. Reader reader = null; 
  112. try { 
  113. System.out.println("以字符为单位读取文件内容，一次读一个字节："); 
  114. // 一次读一个字符 
  115. reader = new InputStreamReader(new FileInputStream(file)); 
  116. int tempchar; 
  117. while ((tempchar = reader.read()) != -1){ 
  118. //对于windows下，rn这两个字符在一起时，表示一个换行。 
  119. //但如果这两个字符分开显示时，会换两次行。 
  120. //因此，屏蔽掉r，或者屏蔽n。否则，将会多出很多空行。 
  121. if (((char)tempchar) != 'r'){ 
  122. System.out.print((char)tempchar); 
  123. } 
  124. } 
  125. reader.close(); 
  126. } catch (Exception e) { 
  127. e.printStackTrace(); 
  128. } 
  129. try { 
  130. System.out.println("以字符为单位读取文件内容，一次读多个字节："); 
  131. //一次读多个字符 
  132. char[] tempchars = new char[30]; 
  133. int charread = 0; 
  134. reader = new InputStreamReader(new FileInputStream(fileName)); 
  135. //读入多个字符到字符数组中，charread为一次读取字符数 
  136. while ((charread = reader.read(tempchars))!=-1){ 
  137. //同样屏蔽掉r不显示 
  138. if ((charread == tempchars.length)&&(tempchars[tempchars.length-1] != 'r')){ 
  139. System.out.print(tempchars); 
  140. }else{ 
  141. for (int i=0; i<charread; i++){ 
  142. if(tempchars[i] == 'r'){ 
  143. continue; 
  144. }else{ 
  145. System.out.print(tempchars[i]); 
  146. } 
  147. } 
  148. } 
  149. } 
  150. } catch (Exception e1) { 
  151. e1.printStackTrace(); 
  152. }finally { 
  153. if (reader != null){ 
  154. try { 
  155. reader.close(); 
  156. } catch (IOException e1) { 
  157. } 
  158. } 
  159. } 
  160. } 
  161. /** 
  162. * 以行为单位读取文件，常用于读面向行的格式化文件 
  163. * @param fileName 文件名 
  164. */ 
  165. public static void readFileByLines(String fileName){ 
  166. File file = new File(fileName); 
  167. BufferedReader reader = null; 
  168. try { 
  169. System.out.println("以行为单位读取文件内容，一次读一整行："); 
  170. reader = new BufferedReader(new FileReader(file)); 
  171. String tempString = null; 
  172. int line = 1; 
  173. //一次读入一行，直到读入null为文件结束 
  174. while ((tempString = reader.readLine()) != null){ 
  175. //显示行号 
  176. System.out.println("line " + line + ": " + tempString); 
  177. line++; 
  178. } 
  179. reader.close(); 
  180. } catch (IOException e) { 
  181. e.printStackTrace(); 
  182. } finally { 
  183. if (reader != null){ 
  184. try { 
  185. reader.close(); 
  186. } catch (IOException e1) { 
  187. } 
  188. } 
  189. } 
  190. } 
  191. /** 
  192. * 随机读取文件内容 
  193. * @param fileName 文件名 
  194. */ 
  195. public static void readFileByRandomAccess(String fileName){ 
  196. RandomAccessFile randomFile = null; 
  197. try { 
  198. System.out.println("随机读取一段文件内容："); 
  199. // 打开一个随机访问文件流，按只读方式 
  200. randomFile = new RandomAccessFile(fileName, "r"); 
  201. // 文件长度，字节数 
  202. long fileLength = randomFile.length(); 
  203. // 读文件的起始位置 
  204. int beginIndex = (fileLength > 4) ? 4 : 0; 
  205. //将读文件的开始位置移到beginIndex位置。 
  206. randomFile.seek(beginIndex); 
  207. byte[] bytes = new byte[10]; 
  208. int byteread = 0; 
  209. //一次读10个字节，如果文件内容不足10个字节，则读剩下的字节。 
  210. //将一次读取的字节数赋给byteread 
  211. while ((byteread = randomFile.read(bytes)) != -1){ 
  212. System.out.write(bytes, 0, byteread); 
  213. } 
  214. } catch (IOException e){ 
  215. e.printStackTrace(); 
  216. } finally { 
  217. if (randomFile != null){ 
  218. try { 
  219. randomFile.close(); 
  220. } catch (IOException e1) { 
  221. } 
  222. } 
  223. } 
  224. } 
  225. /** 
  226. * 显示输入流中还剩的字节数 
  227. * @param in 
  228. */ 
  229. private static void showAvailableBytes(InputStream in){ 
  230. try { 
  231. System.out.println("当前字节输入流中的字节数为:" + in.available()); 
  232. } catch (IOException e) { 
  233. e.printStackTrace(); 
  234. } 
  235. } 
  236. public static void main(String[] args) { 
  237. String fileName = "C:/temp/newTemp.txt"; 
  238. ReadFromFile.readFileByBytes(fileName); 
  239. ReadFromFile.readFileByChars(fileName); 
  240. ReadFromFile.readFileByLines(fileName); 
  241. ReadFromFile.readFileByRandomAccess(fileName); 
  242. } 
  243. } 
  244. 二、将内容追加到文件尾部 
  245. import java.io.FileWriter; 
  246. import java.io.IOException; 
  247. import java.io.RandomAccessFile; 
  248. /** 
  249. * 将内容追加到文件尾部 
  250. */ 
  251. public class AppendToFile { 
  252. /** 
  253. * A方法追加文件：使用RandomAccessFile 
  254. * @param fileName 文件名 
  255. * @param content 追加的内容 
  256. */ 
  257. public static void appendMethodA(String fileName, 
  258. 
  259. String content){ 
  260. try { 
  261. // 打开一个随机访问文件流，按读写方式 
  262. RandomAccessFile randomFile = new RandomAccessFile(fileName, "rw"); 
  263. // 文件长度，字节数 
  264. long fileLength = randomFile.length(); 
  265. //将写文件指针移到文件尾。 
  266. randomFile.seek(fileLength); 
  267. randomFile.writeBytes(content); 
  268. randomFile.close(); 
  269. } catch (IOException e){ 
  270. e.printStackTrace(); 
  271. } 
  272. } 
  273. /** 
  274. * B方法追加文件：使用FileWriter 
  275. * @param fileName 
  276. * @param content 
  277. */ 
  278. public static void appendMethodB(String fileName, String content){ 
  279. try { 
  280. //打开一个写文件器，构造函数中的第二个参数true表示以追加形式写文件 
  281. FileWriter writer = new FileWriter(fileName, true); 
  282. writer.write(content); 
  283. writer.close(); 
  284. } catch (IOException e) { 
  285. e.printStackTrace(); 
  286. } 
  287. } 
  288. public static void main(String[] args) { 
  289. String fileName = "C:/temp/newTemp.txt"; 
  290. String content = "new append!"; 
  291. //按方法A追加文件 
  292. AppendToFile.appendMethodA(fileName, content); 
  293. AppendToFile.appendMethodA(fileName, "append end. n"); 
  294. //显示文件内容 
  295. ReadFromFile.readFileByLines(fileName); 
  296. //按方法B追加文件 
  297. AppendToFile.appendMethodB(fileName, content); 
  298. AppendToFile.appendMethodB(fileName, "append end. n"); 
  299. //显示文件内容 
  300. ReadFromFile.readFileByLines(fileName); 
  301. } 
  302. }   
 

 

 

 1、判断文件是否存在，不存在创建文件

 Java代码 [ ![](http://dpn525.iteye.com/images/spinner.gif)](http://blog.csdn.net/jiangxinyu/article/details/7885518)  
   
 
  1. File file=new File(path+filename); 
  2. if(!file.exists()) 
  3. { 
  4. try { 
  5. file.createNewFile(); 
  6. } catch (IOException e) {  
  7. // TODO Auto-generated catch block 
  8. e.printStackTrace(); 
  9. } 
  10. }   
 **[java]** [ view plain](http://blog.csdn.net/jiangxinyu/article/details/7885518#)[copy](http://blog.csdn.net/jiangxinyu/article/details/7885518#)  
   
 
  1. File file=new File(path+filename); 
  2. if(!file.exists()) 
  3. { 
  4. try { 
  5. file.createNewFile(); 
  6. } catch (IOException e) { 
  7. // TODO Auto-generated catch block 
  8. e.printStackTrace(); 
  9. } 
  10. }   
 

 2、判断文件夹是否存在，不存在创建文件夹

 Java代码 [ ![](http://dpn525.iteye.com/images/spinner.gif)](http://blog.csdn.net/jiangxinyu/article/details/7885518)  
   
 
  1. File file =new File(path+filename); 
  2. //如果文件夹不存在则创建 
  3. if (!file .exists()) 
  4. { 
  5. file .mkdir(); 
  6. }   
 

 
# [java 写文件的三种方法比较](http://www.cnblogs.com/yezhenhan/archive/2012/09/10/2678690.html)

 **[java]** [ view plain](http://blog.csdn.net/jiangxinyu/article/details/7885518#)[copy](http://blog.csdn.net/jiangxinyu/article/details/7885518#)  
   
 
  1. import java.io.File; 
  2. 
  3. import java.io.FileOutputStream; 
  4. 
  5. import java.io.*; 
  6. 
  7. public class FileTest { 
  8. 
  9. public FileTest() { 
  10. 
  11. } 
  12. 
  13. public static void main(String[] args) { 
  14. 
  15. FileOutputStream out = null; 
  16. 
  17. FileOutputStream outSTr = null; 
  18. 
  19. BufferedOutputStream Buff=null; 
  20. 
  21. FileWriter fw = null; 
  22. 
  23. int count=1000;//写文件行数  
  24. 
  25. try { 
  26. 
  27. out = new FileOutputStream(new File(“C:/add.txt”)); 
  28. 
  29. long begin = System.currentTimeMillis(); 
  30. 
  31. for (int i = 0; i < count; i++) { 
  32. 
  33. out.write(“测试java 文件操作\r\n”.getBytes()); 
  34. 
  35. } 
  36. 
  37. out.close(); 
  38. 
  39. long end = System.currentTimeMillis(); 
  40. 
  41. System.out.println(“FileOutputStream执行耗时:” + (end - begin) + ” 豪秒”); 
  42. 
  43. outSTr = new FileOutputStream(new File(“C:/add0.txt”)); 
  44. 
  45. Buff=new BufferedOutputStream(outSTr); 
  46. 
  47. long begin0 = System.currentTimeMillis(); 
  48. 
  49. for (int i = 0; i < count; i++) { 
  50. 
  51. Buff.write(“测试java 文件操作\r\n”.getBytes()); 
  52. 
  53. } 
  54. 
  55. Buff.flush(); 
  56. 
  57. Buff.close(); 
  58. 
  59. long end0 = System.currentTimeMillis(); 
  60. 
  61. System.out.println(“BufferedOutputStream执行耗时:” + (end0 - begin0) + ” 豪秒”); 
  62. 
  63. fw = new FileWriter(“C:/add2.txt”); 
  64. 
  65. long begin3 = System.currentTimeMillis(); 
  66. 
  67. for (int i = 0; i < count; i++) { 
  68. 
  69. fw.write(“测试java 文件操作\r\n”); 
  70. 
  71. } 
  72. 
  73. fw.close(); 
  74. 
  75. long end3 = System.currentTimeMillis(); 
  76. 
  77. System.out.println(“FileWriter执行耗时:” + (end3 - begin3) + ” 豪秒”); 
  78. 
  79. } catch (Exception e) { 
  80. 
  81. e.printStackTrace(); 
  82. 
  83. } 
  84. 
  85. finally { 
  86. 
  87. try { 
  88. 
  89. fw.close(); 
  90. 
  91. Buff.close(); 
  92. 
  93. outSTr.close(); 
  94. 
  95. out.close(); 
  96. 
  97. } catch (Exception e) { 
  98. 
  99. e.printStackTrace(); 
  100. 
  101. } 
  102. 
  103. } 
  104. 
  105. } 
  106. 
  107. }   
       
   
   
 