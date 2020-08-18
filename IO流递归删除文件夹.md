## IO流递归删除文件夹

```java
import java.util.Scanner;
public class Test{
    public static void main(String[] args){
        System.out.println("输入要删除的文件夹路径：")
        String path=new Scanner(System.in).nextLine();
        deleteAll(new File(path));
    }
    
    public static void deleteAll(File file){
        File[] files = file.listFiles();
        for(File file1 : files){
            if(file1.delete()){
                
            }else{
                delete(file1);
            }
        }
        file.delete();
    }
}
```

