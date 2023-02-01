# 1. Khái quát chung về java
## a. Khái niệm
- Java là một một ngôn ngữ lập trình hiện đại, bậc cao, hướng đối tượng, bảo mật và mạnh mẽ. và là một Platform.
- Platform: Bất cứ môi trường phần cứng hoặc phần mềm nào mà trong đó có một chương trình chạy, thì được hiểu như là một Platform. Với môi trường runtime riêng cho mình (JRE) và API, Java được gọi là Platform.
## b. Các kiểu của Java
 - ***Standalone App***: Standalone App cũng được biết đến như Desktop App hoặc Window-based App. Để tạo ra ứng dụng kiểu này người ta thường sử dụng AWT, Swing hoặc JavaFX framework.
 - ***Web App***: Web App là ứng dụng chạy trên server và tạo được các trang động. Hiện nay, servlet, jsp, struts, jsf, spring... là những công nghệ được sử dụng để tạo Web App trong java.
 - ***Enterprise App***: Một ứng dụng dạng như Banking App, có lợi thế là tính bảo mật cao, cân bằng tải (load balancing) và clustering. Trong java, EJB được sử dụng để tạo các Enterprise App.
 - ***Mobile App***: Mobile App là ứng dụng được tạo ra cho các thiết bị di động. Hiện nay Android và Java ME được sử dụng để chạy các ứng dụng này.
 ## c. Java Platforms
 - ***Java SE (Java Standard Edition)***: Java SE là một nền tảng lập trình Java. Nó bao gồm các API lập trình Java như java.lang, java.io, java.net, java.util, java.sql, java.math, v.v. Nó bao gồm các chủ đề cốt lỗi như OOPs, String, Regex, Exception, Inner classes, Multithreading, I/O Stream, Networking, AWT, Swing, Reflection, Collection, v.v.
 - ***Java EE (Java Enterprise Edition)***: Đây là một nền tảng doanh nghiệp chủ yếu được sử dụng để phát triển các ứng dụng web và doanh nghiệp. Nó được xây dựng trên nền tảng Java SE. Nó bao gồm các chủ đề như Servlet, JSP, Web Services, EJB, JPA , v.v.
 - ***Java ME (Java Micro Edition)***: Đây là một nền tảng vi mô chủ yếu được sử dụng để phát triển các ứng dụng di động.
 - ***JavaFX***: JavaFX là một nền tảng phần mềm phát triển các ứng dụng Internet phong phú (Rich Internet Applications – RIAs) có thể chạy trên nhiều loại thiết bị, nhiều hệ điều hành khác nhau. JavaFX là một giải pháp công nghệ cho GUI trên nền tảng Java nhằm tạo giao diện đồ họa người dùng dựa trên Swing và Java2D.
# 2. Syntax cơ bản
## a. Ví dụ Java về chương trình Hello World
 ```cpp 
 public class LearnJava {

    public static void main(String[] args) {
        System.out.println("Hello World!");
    }
}
```
- ***class***: được sử dụng để khai báo một lớp trong Java.
- ***public***: là một Access Modifier mà biểu diễn tính nhìn thấy, nghĩa rằng nó là nhìn nhất với tất cả.
- ***static***: à một từ khóa, mà nếu chúng ta khai báo bất cứ phương thức nào là static thì nó còn được gọi là phương thức tĩnh hoặc phương thức static. Lợi thế chủ yếu của phương thức static là không cần thiết tạo đối tượng để triệu hồi phương thức static.
- ***void***: là kiểu trả về của phương thức, nghĩa là phương thức không trả về bất cứ giá trị nào.
- ***main***: đại diện cho khởi động chương trình.
- ***String[] args***: được sử dụng cho tham số dòng lệnh.
- ***System.out.println()***: được sử dụng như là lệnh in.
## b. Nhập xuất
- Để nhập dữ liệu từ bàn phím, khai báo 1 đối tượng `Scanner` và `System.in`, sau đó gọi ra với cú pháp: `tên biến.next(...)`. Ví dụ như nhập 2 số a và b rồi tính tổng:
    ```cpp
    public class LearnJava {
        
        public static void main(String[] args) {
            Scanner scanner = new Scanner(System.in);
            int a = scanner.nextInt();
            int b = scanner.nextInt();
            System.out.println(a+b);
        }
    }
    ```
    - nextByte(): Đọc một số nguyên kiểu byte
     nextShort(): Đọc một số nguyên kiểu short
    - nextInt(): Đọc một số nguyên kiểu int
    - nextLong(): Đọc một số nguyên kiểu long
    - nextFloat(): Đọc một số kiểu float
    - nextDouble(): Đọc một số kiểu double
    - next(): Đọc một string kết thức trước một ký tự trắng
    - nextLine(): Đọc một line of text (kết thúc bằng phím Enter)
- Để xuất dữ liệu ra màn hình thì dùng `System.out.println`
- `printf` như trong C, đặc tả.
## c. Toán tử
- Trương tự như trong C, C++, Java cũng có các toán tử cơ bản như +,-,*,/,%
- Ép kiểu cũng tương tự trong C, C++.
## d. Biến  
- **Biến cục bộ (local)**: 
    - Biến local được khai báo trong các phương thức, hàm contructor hoặc trong các block.
    - Biến local được tạo bên trong các phương thức, contructor, block và sẽ bị phá hủy khi kết thúc các phương thức, contructor và block.
    - Không được sử dụng "access modifier" khi khai báo biến local.
    - Các biến local được lưu trên vùng nhớ stack của bộ nhớ.
    - Bạn cần khởi tạo giá trị mặc định cho biến local trước khi có thể sử dụng.
    ```cpp
    public class LearnJava {
    
    public void Input()
    {
        Scanner scanner = new Scanner(System.in);
        int a = scanner.nextInt();
        System.out.println("Gia tri cua n la: " + a);
    }
    
    public static void main(String[] args) 
    {
        LearnJava bienLocal = new LearnJava();
        bienLocal.Input();
    }
}

- **Biến toàn cục (instance)**:
    - Biến instance được khai báo trong một lớp(class), bên ngoài các phương thức, constructor và các block.
    - Biến instance được lưu trong bộ nhớ heap.
    - Biến instance được tạo khi một đối tượng được tạo bằng việc sử dụng từ khóa “new” và sẽ bị phá hủy khi đối tượng bị phá hủy.
    - Biến instance có thể được sử dụng bởi các phương thức, constructor, block, ... Nhưng nó phải được sử dụng thông qua một đối tượng cụ thể.
    - Bạn được phép sử dụng "access modifier" khi khai báo biến instance, mặc định là `"default"`.
    - Biến instance có giá trị mặc định phụ thuộc vào kiểu dữ liệu của nó. Ví dụ nếu là kiểu int, short, byte thì giá trị mặc định là 0, kiểu double thì là 0.0d, ... Vì vậy, bạn sẽ không cần khởi tạo giá trị cho biến instance trước khi sử dụng.
    - Bên trong class mà bạn khai báo biến instance, bạn có thể gọi nó trực tiếp bằng tên khi sử dụng ở khắp nới bên trong class đó.
    ```cpp
    public class LearnJava {
    
    public int a;
    
    public void Input()
    {
        Scanner scanner = new Scanner(System.in);
        a = scanner.nextInt();
        System.out.println("Gia tri cua n la: " + a);
    }
    
    public static void main(String[] args) 
    {
        LearnJava bienInstance = new LearnJava();
        bienInstance.Input();
    }
}
- **Biến Static**:
    - Biến static được khai báo trong một class với từ khóa "static", phía bên ngoài các phương thức, constructor và block.
    - Sẽ chỉ có duy nhất một bản sao của các biến static được tạo ra, dù bạn tạo bao nhiêu đối tượng từ lớp tương ứng.
    - Biến static được lưu trữ trong bộ nhớ static riêng.
    - Biến static được tạo khi chương trình bắt đầu chạy và chỉ bị phá hủy khi chương trình dừng.
    - Giá trị mặc định của biến static phụ thuộc vào kiểu dữ liệu bạn khai báo tương tự biến `instance`.
    - Biến static được truy cập thông qua tên của class chứa nó, với cú pháp: `TenClass.tenBien`.
    - Trong class, các phương thức sử dụng biến static bằng cách gọi tên của nó khi phương thức đó cũng được khai báo với từ khóa `"static"`.
```cpp
public class LearnJava {
    
    public static int a;
    
    public static void Input()
    {
        Scanner scanner = new Scanner(System.in);
        a = scanner.nextInt();
    }
    
    public static void Output()
    {
        System.out.println("Gia tri cua n la: " + a);
    }
    
    public static void main(String[] args) 
    {
        LearnJava.Input();
        LearnJava.Output();
    }
}
```
## e. Câu lệnh rẽ nhánh, vòng lặp
- Câu lệnh rẽ nhánh (if-else, switch-case), vòng lặp(while) tương tự như trong C++
- Vòng lặp For cải tiến:
    - Cú pháp: 
    ```cpp
    for (Type var : array) {  
    // Khối lệnh được thực thi
    }
    ```
    - Ví dụ:
    ```cpp
    public class LearnJava {
    
        public static void main(String[] args) 
        {
            int arr[] = { 12, 23, 44, 56, 78 };
            for (int i : arr) 
            {
                if(i < 50) System.out.println(i);
            }
        }
    }
    ```
    ``` 
    Output: 
        12
        23
        44
    ```
- Vòng lặp For dán nhãn:
    - Chúng ta có để đặt tên cho mỗi vòng lặp for bằng cách gán nhãn trước vòng lặp for. Điều này rất hữu dụng khi chúng ta muốn thoát/tiếp tục(break/continues) chạy vòng lặp for.
    - Cú pháp: 
    ```cpp
    ten_nhan:
    for (khoi_tao_bien ; check_dieu_kien ; tang/giam_bien) {  
        // Khối lệnh được thực thi
    }  
    ```
    - Ví dụ:
    ```cpp
    public class LearnJava {
    
        public static void main(String[] args) {
            aa: for (int i = 1; i <= 3; i++) {
                bb: for (int j = 1; j <= 3; j++) {
                    if (i == 2 && j == 2) {
                        break aa;
                    }
                    System.out.println(i + " " + j);
                }
            }
        }
    }
    ```
    ```
    Output:
        1 1
        1 2
        1 3
        2 1 
    ```
## f. Mảng
- Khai báo mảng:
    ```cpp
    // tạo một mảng có độ dài 4, thêm các phần tử sau tạo
    String[] number = new String[4];
 
    // tạo một mảng không cần chỉ định số phần tử cụ thể
    String[] number = new String[] { "12", "13", "14", "15" };
 
    // tạo một mảng không cần chỉ định số phần tử cụ thể và không cần dùng từ khóa new
    String[] number = { "12", "13", "14", "15" };
    ```
- Một số lệnh:
    - Kích thước mảng: `ten_mang.length`
    - Sao chép mảng: 
    ```cpp 
    public static void arraycopy (Obj src, int srcPos, Obj dest, int destPos, int length)
    ``` 
    - Obj src: tên mảng From
    - srcPos: ví trí cần copy của mảng From
    - Obj dest: tên mảng To
    - destPos: ví trí được copy đến của mảng To
    - length: độ dài cần sao chép
- Ví dụ:
    ```cpp
    public class LearnJava {
    
        public static void main(String[] args) {
            char[] copyFrom = { 'd', 'e', 'c', 'a', 'f', 
                'f', 'e', 'i', 'n', 'a', 't', 'e', 'd' };
            char[] copyTo = new char[9];
            copyTo[0] = copyTo[1] = '0';
            System.arraycopy(copyFrom, 2, copyTo, 1, 7);
            System.out.println(new String(copyTo));
        }
    }
    ```
    ```
    Output: 0caffein
    ```
- Ngoài ra trong lớp `java.util.Arrays` chứa nhiều phương thức static đa dạng để xếp thứ tự và tìm kiếm các mảng, so sánh các mảng và điền các phần tử vào mảng.
    - ``` cpp
        public static int binarySearch(Object[] a, Object key)
        // Tìm kiếm mảng của Object (byte, int, double, …) đã cho với giá trị đã xác định bởi sử dụng thuật toán tìm kiếm nhị phân. Mảng này phải được xếp thứ tự trước khi gọi phương thức này. Nó trả về chỉ mục của từ khóa tìm kiếm, nếu nó nằm trong danh sách, nếu không thì, bằng (-(điểm chèn + 1)).
    - ``` cpp
        public static boolean equals(long[] a, long[] a2)
        //Trả về true nếu hai mảng long đã cho là cân bằng nhau. Hai mảng này được cho là cân bằng nếu cả hai mảng chứa cùng số lượng phần tử, và tất cả các cặp phần tử tương ứng của hai mảng là cân bằng. Phương thức tương tự có thể được sử dụng bởi tất cả kiểu dữ liệu gốc khác (byte, short, int, …).
    - ``` cpp
        public static void fill(int[] a, int val)
        //Gán giá trị int đã cho tới mỗi phần tử của mảng int đã cho. Phương thức tương tự có thể được sử dụng bởi tất cả kiểu dữ liệu gốc khác (byte, short, int, …).
    - ```cpp
        public static void sort(Object[] a)
        //Xếp thứ tự mảng các đối tượng đã cho theo thứ tự tăng dần, theo thứ tự tự nhiên của các phần tử. Phương thức tương tự có thể được sử dụng bởi tất cả kiểu dữ liệu gốc khác (byte, short, int, …).
    - ```cpp
        s1.compareTo(s2)
        //So sanh 2 chuoi va tra ve 0 neu trung nhau hoac 1 so lon hon 0.
     ``` ```
# 3. Regex
## a. Định nghĩa
 - `Java Regex hoặc Regular Expression (biểu thức chính quy)` là một API để định nghĩa một mẫu để tìm kiếm hoặc thao tác với chuỗi. Nó được sử dụng rộng rãi để xác định ràng buộc trên các chuỗi như xác thực mật khẩu, email, kiểu dữ liệu datetime, ...
- `Gói java.util.regex` cung cấp 1 interface và 3 lớp trong gói java.util.regex.
    - **Interface MatchResult**
    - **Lớp Matcher:** cung cấp bộ máy xử lý biểu thức chính quy để thao tác với chuỗi ký tự.  
        - boolean matches(): kiểm tra xem biểu thức chính quy có khớp với mẫu hay không.
        - boolean find(): tìm biểu thức tiếp theo khớp với mẫu.
        - boolean find(int start): tìm biểu thức tiếp theo khớp với mẫu từ số bắt đầu đã cho.
        - String group(): trả về chuỗi con phù hợp.
        - int start(): trả về vị trí bắt đầu của chuỗi con phù hợp.
	    - int end(): trả về vị trí kết thúc của chuỗi con phù hợp.
	    - int groupCount(): trả về tổng số các chuỗi con phù hợp.
    - **Lớp Pattern:** Đây là phiên bản được biên dịch của một biểu thức chính quy. Nó được sử dụng để xác định một mẫu cho bộ máy regex.
        - static Pattern compile(String regex): biên dịch regex đã cho và trả về thể hiện của Pattern.
        - Matcher matcher(CharSequence input): tạo một matcher khớp với đầu vào đã cho với mẫu.
        - static boolean matches(String regex, CharSequence input): Nó biên dịch biểu thức chính quy và tìm kiếm các chuỗi con từ chuỗi input phù hợp với mẫu regex.
        - String[] split(CharSequence input); chia chuỗi input đã cho thành mảng các kết quả trùng khớp với mẫu đã cho.
        - String pattern(): trả về mẫu regex.
    - **Lớp PatternSyntaxException**
## b. Ví dụ Regex trong Java
- Ví dụ sử dụng Regex trong Java - tìm kiếm chuỗi con:
    ``` cpp 
    \d{1,2}[-|/]\d{1,2}[-|/]\d{4}
    ```
    - \d{1,2}: nghĩa là một số có 1 hoặc 2 chữ số (ngày và tháng).
    - [-|/]: nghĩa là ký tự - hoặc /.
    - \d{4}: nghĩa là một số có 4 chữ số (năm).
    ``` cpp
    package vn.viettuts;
 
    import java.util.regex.Matcher;
    import java.util.regex.Pattern;
    
    public class RegexExample1 {
    public static void main(String[] args) {
            String text1 = "Hello java regex 2-12-2018, hello world 12/12/2018";
            Pattern pattern = Pattern.compile("\\d{1,2}[-|/]\\d{1,2}[-|/]\\d{4}");
            Matcher matcher = pattern.matcher(text1);
            
            System.out.println("Ngày tháng trong chuỗi text1: " + text1);
            while (matcher.find()) {
                System.out.println(text1.substring(matcher.start(), matcher.end()));
            }
            
            String text2 = "2/12/2018";
            String text3 = "12/12/aaaa";
            pattern = Pattern.compile("^\\d{1,2}[-|/]\\d{1,2}[-|/]\\d{4}$");
            System.out.println("\nChuỗi " + text2 + " có định dạng ngày tháng: "
                    + pattern.matcher(text2).matches());
            
            System.out.println("Chuỗi " + text3 + " có định dạng ngày tháng: "
                    + pattern.matcher(text3).matches());
        }
    }
    ```
    ``` 
    Kết quả:
    Ngày tháng trong chuỗi text1: Hello java regex 2-12-2018, hello world 12/12/2018
    2-12-2018
    12/12/2018

    Chuỗi 2/12/2018 có định dạng ngày tháng: true
    Chuỗi 12/12/aaaa có định dạng ngày tháng: false
    ```
- Ví dụ sử dụng Regex trong Java - xác thực email:
    ``` cpp 
    ^[a-zA-Z][\\w-]+@([\\w]+\\.[\\w]+|[\\w]+\\.[\\w]{2,}\\.[\\w]{2,})$
    ```
    ``` cpp
    package vn.viettuts;
 
    import java.util.regex.Pattern;
    
    public class RegexExample2 {
        public static void main(String[] args) {
            String EMAIL_PATTERN = 
                "^[a-zA-Z][\\w-]+@([\\w]+\\.[\\w]+|[\\w]+\\.[\\w]{2,}\\.[\\w]{2,})$";
            
            String email1 = "test1@gmail.com.vn";
            String email2 = "123test@gmail.com.vn";
            String email3 = "test2@gmail.com";
            String email4 = "test3-1@gmail.com";
            String email5 = "test4@@gmail.com";
            String email6 = "test5@domain.com";
            String email7 = "test6@gmail";
            
            System.out.println(email1 + ": " + Pattern.matches(EMAIL_PATTERN, email1));
            System.out.println(email2 + ": " + Pattern.matches(EMAIL_PATTERN, email2));
            System.out.println(email3 + ": " + Pattern.matches(EMAIL_PATTERN, email3));
            System.out.println(email4 + ": " + Pattern.matches(EMAIL_PATTERN, email4));
            System.out.println(email5 + ": " + Pattern.matches(EMAIL_PATTERN, email5));
            System.out.println(email6 + ": " + Pattern.matches(EMAIL_PATTERN, email6));
            System.out.println(email7 + ": " + Pattern.matches(EMAIL_PATTERN, email7));
        }
    }
    ```
    ```
    Kết quả:
    test1@gmail.com.vn: true
    123test@gmail.com.vn: false
    test2@gmail.com: true
    test3-1@gmail.com: true
    test4@@gmail.com: false
    test5@domain.com: true
    test6@gmail: false
    ```
## c. Cú pháp Regex trong Java
### c1. Các lớp ký tự Regex
- [...]: trả về một ký tự phù hợp
- [abc]: a, b, hoặc c
- [^abc]: Bất kỳ ký tự nào ngoại trừ a, b, hoặc c
- [a-zA-Z]: a tới z hoặc A tới Z
- [a-d[m-p]]: a tới d, hoặc m tới p: [a-dm-p]
- [a-z&&[def]]: d, e, hoặc f
- [a-z&&[^bc]]: a tới z, ngoại trừ b và c: [ad-z]
- [a-z&&[^m-p]]	a tới z, ngoại trừ m tới p: [a-lq-z]
- [0-9]	0 tới 9
### c2. Số lượng ký tự trong Regex
- X?: X xảy ra một hoặc không lần
- X+: X xảy ra một hoặc nhiều lần
- X*: X xảy ra không hoặc nhiều lần
- X{n}: X chỉ xảy ra n lần
- X{n,}: X xảy ra n hoặc nhiều lần
- X{y,z}: X xảy ra ít nhất y lần nhưng nhỏ hơn z lần
### c3. Ký tự đặc biệt trong Regex
- .: Bất kỳ ký tự nào
- ^: Có 2 cách sử dụng: 
    - Đánh dấu bắt đầu của một dòng, một chuỗi.
    - Nếu sử dụng trong dấu [...] thì nó có nghĩa là phủ định.
- $: Đánh dấu Kết thúc của một dòng
- \d: Bất kỳ chữ số nào, viết tắt của [0-9]
- \D: Bất kỳ ký tự nào không phải chữ số, viết tắt của [^0-9]
- \s: Bất kỳ ký tự trống nào (như dấu cách, tab, xuống dòng, ...), viết tắt của [\t\n\x0B\f\r]
- \S: Bất kỳ ký tự trống nào không phải ký tự trống, viết tắt của [^\s]
- \w: Bất kỳ ký tự chữ nào (chữ cái và chữ số), viết tắt của [a-zA-Z_0-9]
- \W: Bất kỳ ký tự nào không phải chữ cái và chữ số, viết tắt của [^\w]
- \b: Ranh giới của một từ
- \B: Không phải ranh giới của một từ
### c4. Ký tự logic trong Regex
- |: Hoặc
- ( … ): Group các ký tự và chụp lại
- \1: Nội dung của Group 1
- \2: Nội dung của Group 2
- (?: … ): Group không được chụp lại, bạn không thể sử dụng 
# 4. Class & Object (OOP)
## 4.1: Encapsulation (Tính đóng gói)
- Tính đóng gói trong java là kỹ thuật ẩn giấu thông tin không liên quan và hiện thị ra thông liên quan. Mục đích chính của đóng gói trong java là giảm thiểu mức độ phức tạp phát triển phần mềm. Tức là thiết kế để các thuộc tính và phương thức thuộc về (bên trong) một lớp.
- Với các access modifier, tính đóng gói sẽ có thể giúp ngăn chặn những lớp bên ngoài truy cập, thay đổi thuộc tính và phương thức của một lớp. Từ đó, giúp cho việc che giấu dữ liệu, để bảo vệ trạng thái bên trong của một đối tượng. Hơn nữa, việc ẩn giấu các biến thì các lớp sẽ không chia sẻ thông tin với nhau được. Điều này làm giảm số lượng khớp nối có thể có trong một ứng dụng.
## 4.2: Inheritance (Tính kế thừa)
- Tính kế thừa trong Java là một cơ chế trong đó một đối tượng có được tất cả các thuộc tính và hành vi của một đối tượng cha.
- Khi bạn kế thừa từ một class có sẵn, bạn có thể tái sử dụng các phương thức và trường của class cha. Hơn nữa, bạn có thể thêm các phương thức và trường mới trong class hiện tại.
- Sử dụng tính kế thừa, ta có thể thực hiện Method Overriding, từ đó xuất hiện tính Đa hình trong runtime.
- Phân loại:
    - Đơn kế thừa.
    - Kế thừa nhiều cấp.
    - Kế thừa thứ bậc.
- Đa kế thừa và Kế thừa hỗn hợp không được hỗ trợ thông qua Class trong Java, nhưng vẫn được hỗ trợ thông qua Interface.
- Cú pháp: sử dụng từ khóa `extends`
``` cpp
class Subclass extends Superclass 
{  
   //... 
} 
```
## 4.3: Polymorphism (Tính đa hình)
- Đa hình là ta có thể thực hiện một hành động bằng nhiều cách khác nhau.
- Có hai kiểu của đa hình trong java, đó là đa hình lúc biên dịch (compile) và đa hình lúc thực thi (runtime). Chúng ta có thể thực hiện đa hình trong java bằng cách method overriding (ghi đè phương thức) và method overloading (nạp chồng phương thức).
- Ghi đè phương thức: method overriding - ghi đè method ở lớp cha trong lớp con, ta chỉ cần viết code thực thi khác của method đó ở trong lớp con là được.
- Nạp chồng phương thức: method overloading - Trong một class có thẻ có nhiều method cùng tên nhưng khác nhau tham số truyền vào và dữ liệu trả về, cách hoạt động khác nhau.
## 4.4: Modifiers
![](https://imgur.com/KJvujf4.png)
## 4.5: Modifier static
- Được sử dụng chính để quản lý bộ nhớ. Chúng ta có thể áp dụng từ khóa static với các biến, các phương thức, các khối, các lớp lồng nhau(nested class). Từ khóa static thuộc về lớp chứ không thuộc về instance(thể hiện) của lớp.
    - Biến static: Khi bạn khai báo một biến là static, thì biến đó được gọi là biến tĩnh, hay biến static.
    - Phương thức static: Khi bạn khai báo một phương thức là static, thì phương thức đó gọi là phương thức static.
    - Khối static: Được sử dụng để khởi tạo thành viên dữ liệu static.
- Biến Static: có thể được sử dụng để tham chiếu thuộc tính chung của tất cả đối tượng (mà không là duy nhất cho mỗi đối tượng), ví dụ như tên công ty của nhân viên, tên trường học của các sinh viên, ... Biến static lấy bộ nhớ chỉ một lần trong Class Area tại thời gian tải lớp đó.
- Phương thức static:
    - Một phương thức static thuộc lớp chứ không phải đối tượng của lớp.
    - Một phương thức static gọi mà không cần tạo một instance của một lớp.
    - Phương thức static có thể truy cập biến static và có thể thay đổi giá trị của nó.
    - Phương thức static không thể sử dụng biến non-static hoặc gọi trực tiếp phương thức non-static.
    - Từ khóa this và super không thể được sử dụng trong ngữ cảnh static.
- Khối static:
    - Được sử dụng để khởi tạo thành viên dữ liệu static.
    - Nó được thực thi trước phương thức main tại lúc tải lớp.
## 4.6: Abstract Classes (Lớp trừu tượng)
- Một phương thức được khai báo là `abstract` và không có code thực thi thì đó là phương thức trừu tượng, (giống `virtual` trong CPP), được khai báo với từ khóa `abstract` ở trước.
- Lớp trừu tượng thường được dùng để kế thừa. Và lớp trừu tượng không thể tạo ra instance.
## 4.7: Interfaces.
-Là một bản thiết kế của một lớp. Nó chỉ có các phương thức trừu tượng. Interface là một kỹ thuật để thu được tính trừu tượng hoàn toàn và đa kế thừa trong Java. Nó không thể được khởi tạo giống như lớp trừu tượng.
- Cú pháp:
``` cpp
interface InterfaceName {
    // Khai báo các thành phần bên trong interface
}
```

