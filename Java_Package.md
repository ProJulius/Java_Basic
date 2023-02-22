# 1. Package trong java
## A. Định nghĩa
- Một Package (gói) trong Java là một nhóm các class, interface và các package con tương tự, liên quan đến nhau.
- Chúng ta có thể coi package giống như là một folder vậy.
- Các package trong Java được sử dụng để tránh việc xung đột trong khi đặt tên, để kiểm soát truy cập, giúp bạn tìm kiếm và sử dụng các class, interface… một các dễ dàng hơn.
## B. Các loại pakage
- Các package có sẵn trong Java API: 
    -java.lang: Chứa các lớp hỗ trợ ngôn ngữ (ví dụ: lớp được định nghĩa các kiểu dữ liệu nguyên thủy, các phép toán). Package này được import tự động.
    - java.io: Chứa lớp để hỗ trợ input / output (I/O)
    - java.util: Chứa các lớp tiện ích thực hiện các cấu trúc dữ liệu như danh sách liên kết, dictionary và hỗ trợ cho các hoạt động date / time.
    - java.applet: Chứa các lớp để tạo Applet.
    - java.awt: Chứa các class để triển khai các thành phần cho giao diện người dùng đồ họa (ví dụ như button, menu,…).
    - java.net: Chứa các lớp để hỗ trợ các thao tác trong mạng (network)
- Các package do người dùng tự định nghĩa (đây là package do bạn tự tạo ra) – User defined packages 
## C. Truy câp package từ package khác
- Sử dụng `packagename.*`: 
    - Nếu sử dụng packagename.*. Thì tất cả các lớp và các interface của các gói này sẽ có thể truy cập, nhưng gói con của gói này thì không được truy cập.
    - Từ khóa import được sử dụng để truy cập các lớp và interface của gói khác từ gói hiện tại.
- Sử dụng `packagename.classname`: 
    - Nếu khai báo import package.classname thì chỉ được truy cập tới lớp đã được khai báo của package này.
``` cpp
package pack;  
public class A {
    public void PrintHello() {
        System.out.println("Hello");
    }
} 

package mypack;  
import pack.A;  
   
class B {
    public static void main(String args[]) {
        A obj = new A();
        obj.PrintHello();
    }
}
```
- Sử dụng tên đầy đủ:
    - Nếu sử dụng tên đầy đủ thì chỉ được truy cập tới lớp đã được khai báo của package này, không cần phải sử dụng đến từ khóa import. Nhưng cần phải sử dụng tên đầy đủ mỗi khi truy cập vào các lớp hoặc interface.
    - Cách này thường được sử dụng khi 2 package có tên lớp giống nhau. Ví dụ, 2 package java.util và java.sql chứa lớp có tên giống nhau là lớp Date.
``` cpp
package pack;  
public class A {
    public void PrintHello() {
        System.out.println("Hello");
    }
} 

package mypack;  
import pack.A;  
   
class B {
    public static void main(String args[]) {
        pack.A obj = new pack.A();
        obj.PrintHello();
    }
}
```
## D. Pakage con trong java
- Package bên trong một package khác được gọi là subpackage hay package con trong java.
# 2. Xử lý ngoại lệ trong Java (Xử lý Exception)
- Khối lệnh try trong java được sử dụng để chứa một đoạn code có thế xảy ra một ngoại lệ. Nó phải được khai báo trong phương thức.
- Sau một khối lệnh try bạn phải khai báo khối lệnh catch hoặc finally hoặc cả hai.
- Cú pháp của khối lệnh try-catch trong java: 
    - Cú pháp: 
    ``` cpp
    try {  
        // code có thể ném ra ngoại lệ
    } catch(Exception_class_Name ref) {
        // code xử lý ngoại lệ
    }  
    ``` 
    - Đôi khi một tình huống có thể phát sinh khi một phần của một khối lệnh có thể xảy ra một lỗi và toàn bộ khối lệnh chính nó có thể xảy ra một lỗi khác. Trong những trường hợp như vậy, trình xử lý ngoại lệ phải được lồng nhau.
    - Khối catch trong java được sử dụng để xử lý các Exception. Nó phải được sử dụng sau khối try.
    - Có thể sử dụng nhiều khối catch với một khối try duy nhất.
    ``` cpp
    try {  
        statement 1;  
        statement 2;  
        try {  
            statement 1;  
            statement 2;  
        }  
        catch(Exception e) {
            
        }  
    }  
    catch(Exception e) {
        
    }
    ```
- Cú pháp của khối lệnh try-finally trong java:
    - Cú pháp:
    ``` cpp
    try {  
        // code có thể ném ra ngoại lệ
    } finally {
        // code trong khối này luôn được thực thi
    }  
    ```
    - Khối lệnh finally trong java được sử dụng để thực thi các lệnh quan trọng như đóng kết nối, đóng các stream,...

    - Khối lệnh finally trong java luôn được thực thi cho dù có ngoại lệ xảy ra hay không hoặc gặp lệnh return trong khối try.

    - Khối lệnh finally trong java được khai báo sau khối lệnh try hoặc sau khối lệnh catch.
    - Quy tắc: Đối với mỗi khối try, có thể có không hoặc nhiều khối catch, nhưng chỉ có một khối finally

    - Note: Khối finally sẽ không được thực thi nếu chương trình bị thoát (bằng cách gọi System.exit() hoặc xảy ra một lỗi không thể tránh khiến chương trình bị chết).
- Từ khóa throw trong Java:
    - Từ khoá throw trong java được sử dụng để ném ra một ngoại lệ cụ thể.

    - Từ khóa throw chủ yếu được sử dụng để ném ngoại lệ tùy chỉnh (ngoại lệ do người dùng tự định nghĩa).
    - Cú pháp: 
    ``` cpp
    // Cú pháp
    throw exception;

    //ví dụ
    throw new IOException("File không tồn tại");
    ```
    - Quy tắc: Nếu bạn đang gọi một phương thức khai báo throws một ngoại lệ, bạn phải bắt hoặc throws ngoại lệ đó