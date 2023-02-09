# 1. Collection và Collections trong Java
### a. **`Collections trong java`** là một khuôn khổ cung cấp một kiến trúc để lưu trữ và thao tác tới nhóm các đối tượng. Tất cả các hoạt động mà bạn thực hiện trên một dữ liệu như tìm kiếm, phân loại, chèn, xóa,... có thể được thực hiện bởi Java Collections.
### b. **`Collection trong java`** là một root interface trong hệ thống cấp bậc Collection. Java Collection cung cấp nhiều interface (Set, List, Queue, Deque vv) và các lớp (ArrayList, Vector, LinkedList, PriorityQueue, HashSet, LinkedHashSet, TreeSet vv).
# 2. Khái quát chung về hệ thống cấp bậc Collection trong Java
## `Lưu ý`: Gói java.util chứa tất cả các lớp và interface của Collection.
## **`a. Set`**: 
- Là một collection không thể chứa 2 giá trị trùng lặp. Set được sử dụng để biểu diễn các bộ, chẳng hạn như bộ tú lu khơ, thời khóa biểu của học sinh, các tiến trình đang chạy trên máy tính...
- SortedSet: là một Set chứa các phần tử theo thứ tự tăng dần.
- Ở SortedSet ta sẽ tìm hiểu kĩ về TreeSet sau.
## **`b. List`**:
- Là một collection có thứ tự (đôi khi còn được gọi là một chuỗi). List có thể chứa các phần tử trùng lặp. Thường có quyền kiểm soát chính xác vị trí các phần tử được chèn vào và có thể truy cập chúng bằng chỉ số (vị trí của chúng).
- Ở List ta sẽ tìm hiểu kĩ về ArrayList sau.
## **`c. Map`**:
- Là một đối tượng ánh xạ mỗi key tương ứng với một giá trị. Map không thể chứa giá trị trùng lặp. Mỗi key có thể ánh xạ đến nhiều nhất một giá trị.
- SortedMap: là một Map chứa các phần tử được sắp xếp theo thứ tự tăng dần của key của chúng. Các SortedMap được sử dụng cho các collection theo thứ tự tự nhiên của cặp key/value, chẳng hạn như từ điển và danh bạ điện thoại.
- Ở Map ta sẽ tìm hiểu kĩ về TreeMap và HashMap sau.

![](https://imgur.com/nbDluRM.jpg)
# 3. Interface Collection
- add(o): Được sử dụng để chèn một phần tử vào collection.
- remove(o): Được sử dụng để xóa phần tử từ collection.
- contains(o): Được sử dụng để tìm kiếm phần tử.
- clear(): Loại bỏ tổng số của phần tử khỏi collection.
- size(): Trả lại tổng số các phần tử trong collection.
- isEmpty(): Kiểm tra nếu collection trống.
- iterator(): Trả về một iterator.
- equals(o): So sánh 2 collection.
# 4. Interface List
- add(i,o): Chèn o vào vị trí i.
- add(o): Chèn o vào cuối.
- get(i): Trả về giá trị tại vị trí i.
- remove(i): Xoá phần tử tại vị trí i.
- remove(o): Xoá phần tử o.
- set(i,o): gán lại giá trị o cho vị trí i.
# 5. Interface Set
- add(E e): Thêm phần tử vào tập hợp nếu nó chưa có.
- addAll(Collection<? extends E> c): Thêm tất cả phần tử vào trong tập hợp nếu nó chưa có.
- clear(): Xoá tất cả phần tử khỏi tập hợp.
- contains(o): Tìm kiếm phần tử o.
- containsAll(Collection<?> c): Tìm kiếm tập hợp c.
- equals(o): So sánh đối tượng với tập hợp này.
- isEmpty(): Kiểm tra rỗng.
- size(): Trả về số lượng.
- remove(o): Xoá đối tượng.
# 6. Interface Map
- clear(): Xoá mọi phần tử thuộc map.
- containsKey(k): Tìm kiếm phần tử theo k.
- containsValue(v): Tìm kiếm phần tử theo v.
- size(): Trả về kích thước của map.
- get(k): Trả về giá trị với k.
- isEmpty(): Kiểm tra nếu Map trống.
- keySet(): Lấy tập hợp các key ra.
- values(): Trả về dạng Collection xem các giá trị có trong Map. 
- put(k,v): 
- remove(k): Xoá phần từ có key k khỏi Map.
- remove(k,v): Xoá phần từ có key k, value v khỏi Map.
# 6. Bài tập minh hoạ
## 6.1: ArrayList
- `Note`:
    - Source/Insert Code/... : tạo nhanh hàm khởi tạo, getter,setter, toString(đưa ra 1 loạt thông tin), equals, hashCode
    - Khi muốn so sánh 2 đối tượng, ta dùng implements Comparable<>
    - Để thêm một Comparator : click chuột vào đầu dòng Comparator -> compare
- Quy tắc khi sử dụng equals() vs hashCode() trong Java:
    - Khi phương thức equals() được ghi đè, phương thức hashCode() cũng phải được ghi đè.
    - Nếu hai đối tượng bằng nhau, mã băm của chúng phải bằng nhau.
    - Nếu hai đối tượng không bằng nhau, không có ràng buộc về mã băm của chúng (mã băm của chúng có thể bằng nhau hay không).
    - Nếu hai đối tượng có mã băm giống nhau, thì không có ràng buộc nào về sự bình nhau của chúng (chúng có thể bằng nhau hay không).
    - Nếu hai đối tượng có mã băm khác nhau, chúng không được bằng nhau.
- `Bài tập`: Tạo 1 chương trình quản lí nhiều sinh viên sử dụng ArrayList. Sinh viên gồm họ tên, MSV, năm sinh, GPA.
    - SinhVien.java
    ``` cpp
    package sinhvien;

    import java.util.Objects;

    public class SinhVien implements Comparable<SinhVien> {

        private String hoTen;
        private String MSV;
        private int namSinh;
        private float GPA;

        public SinhVien(String MSV) {
            this.MSV = MSV;
        }

        public SinhVien(String hoTen, String MSV, int namSinh, float GPA) {
            this.hoTen = hoTen;
            this.MSV = MSV;
            this.namSinh = namSinh;
            this.GPA = GPA;
        }

        public String getHoTen() {
            return hoTen;
        }

        public String getMSV() {
            return MSV;
        }

        public int getNamSinh() {
            return namSinh;
        }

        public float getGPA() {
            return GPA;
        }

        public void setHoTen(String hoTen) {
            this.hoTen = hoTen;
        }

        public void setMSV(String MSV) {
            this.MSV = MSV;
        }

        public void setNamSinh(int namSinh) {
            this.namSinh = namSinh;
        }

        public void setGPA(float GPA) {
            this.GPA = GPA;
        }

        @Override
        public String toString() {
            return "SinhVien{" + "hoTen=" + hoTen + ", MSV=" + MSV + ", namSinh=" + namSinh + ", GPA=" + GPA + '}';
        }

        @Override
        public int compareTo(SinhVien o) {
            return this.MSV.compareTo(MSV);
        }

        @Override
        public int hashCode() {
            return Objects.hash(hoTen, MSV, namSinh, GPA);
        }

        @Override
        public boolean equals(Object obj) {
            if (this == obj) {
                return true;
            }
            if (obj == null) {
                return false;
            }
            if (getClass() != obj.getClass()) {
                return false;
            }
            SinhVien other = (SinhVien) obj;
            return Objects.equals(MSV, other.MSV);
        }

        public static void main(String[] args) {
            // TODO code application logic here
        }
    }
    ```
    - DanhSachSinhVien.java
    ``` cpp
    package sinhvien;

    import java.util.ArrayList;
    import java.util.Collections;
    import java.util.Comparator;

    public class DanhSachSinhVien {
        private ArrayList<SinhVien> danhSach;

        //truong hop nguoi ta khong truyen vao cho minh 1 ArrayList
        public DanhSachSinhVien() {
            this.danhSach = new ArrayList<SinhVien>();
        }
        
        public DanhSachSinhVien(ArrayList<SinhVien> danhSach){
            this.danhSach = danhSach;
        }
    
        //them sinh vien
        public void themSinhVien(SinhVien sv){
            this.danhSach.add(sv);
        }
        
        //in tat ca sinh vien
        public void inSinhVien(){
            for(SinhVien sinhvien : danhSach){
                System.out.println(sinhvien);
            }            
        }
        
        //kiem tra danh sach rong hay khong
        public boolean kiemTraRong(){
            return this.danhSach.isEmpty();
        }
        
        //lay ra so luong
        public int laySoLuong(){
            return this.danhSach.size();
        }
        
        //lam rong danh sach
        public void lamRongDanhSach(){
            this.danhSach.removeAll(danhSach);
        }
        
        //kiem tra ton tai cua sinh vien
        public boolean kiemTraTonTai(SinhVien sv){
            return this.danhSach.contains(sv);
        }
        
        //xoa 1 sinh vien
        public boolean xoaSinhVien(SinhVien sv){
            return this.danhSach.remove(sv);
        }
        
        //tim sinh vien dua vao ten
        public void timSinhVien(String ten){
            for(SinhVien sinhvien : danhSach){
                if(sinhvien.getHoTen().indexOf(ten) >= 0){
                    System.out.println(sinhvien);
                }
            }
        }
        
        //in danh sach theo GPA giam dan
        public void sapXepGPA(){
            Collections.sort(this.danhSach, new Comparator<SinhVien>(){
                @Override
                public int compare(SinhVien sv1, SinhVien sv2) {
                    if(sv1.getGPA() < sv2.getGPA()) return -1;
                    else if(sv1.getGPA() > sv2.getGPA()) return 1;
                    else return 0;
                }  
            });
        }
    }
    ```
    Run.java
    ``` cpp
    package run;

    import java.util.Scanner;
    import sinhvien.DanhSachSinhVien;
    import sinhvien.SinhVien;

    public class Run {

        public static void main(String[] args) {
            Scanner sc = new Scanner(System.in);

            DanhSachSinhVien dssv = new DanhSachSinhVien();
            int luaChon = 0;
            do {
                System.out.println("-----------MENU----------");
                System.out.println("Chọn chức năng: ");
                System.out.println(
                        "1.  Thêm sinh viên vào danh sách.\n"
                        + "2.  In danh sách sinh viên.\n"
                        + "3.  Kiểm tra danh sách có rỗng hay không.\n"
                        + "4.  Lấy ra số lượng sinh viên có trong danh sách.\n"
                        + "5.  Làm rỗng danh sách.\n"
                        + "6.  Kiểm tra sinh viên có trong danh sách hay không dựa vào MSV.\n"
                        + "7.  Xoá một sinh viên ra khỏi danh sách theo MSV.\n"
                        + "8.  Tìm kiếm một sinh viên.\n"
                        + "9.  In ra tất cả sinh viên có điểm GPA từ cao đến thấp.\n"
                        + "10. Thoát.\n"
                );

                luaChon = sc.nextInt();
                sc.nextLine();

                if (luaChon == 1) {
                    System.out.println("Nhập tên sinh viên: ");
                    String hoTen = sc.nextLine();
                    System.out.println("Nhập mã sinh viên: ");
                    String MSV = sc.nextLine();
                    System.out.println("Nhập năm sinh: ");
                    int namSinh = sc.nextInt();
                    System.out.println("Nhập GPA: ");
                    float GPA = sc.nextFloat();
                    SinhVien sv = new SinhVien(hoTen, MSV, namSinh, GPA);
                    dssv.themSinhVien(sv);
                } else if (luaChon == 2) {
                    dssv.inSinhVien();
                } else if (luaChon == 3) {
                    System.out.println("Danh sách rỗng: " + dssv.kiemTraRong());
                } else if (luaChon == 4) {
                    System.out.println("Số lượng hiện tại: " + dssv.laySoLuong());
                } else if (luaChon == 5) {
                    dssv.lamRongDanhSach();
                } else if (luaChon == 6) {
                    System.out.println("Nhập mã sinh viên: ");
                    String MSV = sc.nextLine();
                    SinhVien sv = new SinhVien(MSV);
                    System.out.println("Kiếm tra sinh viên có trong danh sách: " + dssv.kiemTraTonTai(sv));
                } else if (luaChon == 7) {
                    System.out.println("Nhập mã sinh viên: ");
                    String MSV = sc.nextLine();
                    SinhVien sv = new SinhVien(MSV);
                    System.out.println("Xóa sinh viên trong danh sách: " + dssv.xoaSinhVien(sv));
                } else if (luaChon == 8) {
                    System.out.println("Nhập họ và tên: ");
                    String hoTen = sc.nextLine();
                    System.out.println("Kết quả tìm kiếm: ");
                    dssv.timSinhVien(hoTen);
                } else if (luaChon == 9) {
                    dssv.sapXepGPA();
                    dssv.inSinhVien();
                }
            } while (luaChon != 0);
        }
    }
    ```
## 6.2: Set
- `HashSet`: Lưu trữ các phần tử của nó trong bảng băm, là cách thực hiện tốt nhất, tuy nhiên nó không đảm bảo b=về thứ tự các phần tử được chèn vào.
- `TreeSet`: Lưu trữ các phần tử của nó trong 1 cây, sắp xếp các phần tử của nó dựa trên các giá trị của chúng, về cơ bản chậm hơn HashSet.
- `LinkedHashSet`: dược triển khai dưới dạng bảng băm với có cấu trúc dữ liệu danh sách liên kết, sắp xếp các phần tử của nó dựa trên thứ tự chúng được chèn vào tập hợp.
- `EnumSet`: là một cài đặt chuyên biệt để sử dụng cho các kiểu enum.
- `Bài tập`: Tạo 1 chương trình rút thăm trúng thưởng sử dụng HashSet, TreeSet.
    - RutThamTrungThuong_HashSet.java
    ``` cpp
    package rutthamtrungthuong;

    import java.util.Arrays;
    import java.util.HashSet;
    import java.util.Random;
    import java.util.Scanner;
    import java.util.Set;

    public class RutThamTrungThuong_HashSet {

        Set<String> thungPhieuDuThuong = new HashSet<String>();

        public RutThamTrungThuong_HashSet() {
        }

        public boolean themPhieu(String giaTri) {
            return this.thungPhieuDuThuong.add(giaTri);
        }

        public boolean xoaPhieu(String giaTri) {
            return this.thungPhieuDuThuong.remove(giaTri);
        }

        public boolean kiemTraPhieu(String giaTri) {
            return this.thungPhieuDuThuong.contains(giaTri);
        }

        public void xoaTatCaPhieu() {
            this.thungPhieuDuThuong.clear();
        }

        public int laySoLuong() {
            return this.thungPhieuDuThuong.size();
        }

        public String rutMotPhieu() {
            String ketQua = "";
            Random rd = new Random();
            int viTri = rd.nextInt(this.thungPhieuDuThuong.size());
            ketQua = (String) this.thungPhieuDuThuong.toArray()[viTri];
            return ketQua;
        }

        public void inTatCa() {
            System.out.println(Arrays.toString(this.thungPhieuDuThuong.toArray()));
        }

        public static void main(String[] args) {
            int luaChon = 0;
            Scanner sc = new Scanner(System.in);
            RutThamTrungThuong_HashSet rt = new RutThamTrungThuong_HashSet();
            do {
                System.out.println("-----------MENU----------");
                System.out.println("Chọn chức năng: ");
                System.out.println(
                        "1.  Thêm mã số dự thưởng.\n"
                        + "2.  Xoá mã số dự thưởng.\n"
                        + "3.  Kiểm tra mã số dự thưởng có tồn tại không.\n"
                        + "4.  Xoá toàn bộ mã số dự thưởng.\n"
                        + "5.  Số lượng mã số dự thưởng.\n"
                        + "6.  Rút thăm trúng thưởng.\n"
                        + "0. Thoát.\n"
                );
                luaChon = sc.nextInt();
                sc.nextLine();
                if (luaChon == 1 || luaChon == 2 || luaChon == 3) {
                    System.out.println("Nhập vào mã phiếu dự thưởng: ");
                    String giaTri = sc.nextLine();
                    if (luaChon == 1) {
                        rt.themPhieu(giaTri);
                    } else if (luaChon == 2) {
                        rt.xoaPhieu(giaTri);
                    } else {
                        System.out.println("Kết quả kiểm tra: " + rt.kiemTraPhieu(giaTri));
                    }
                } else if (luaChon == 4) {
                    rt.xoaTatCaPhieu();
                } else if (luaChon == 5) {
                    System.out.println("Số lượng phiếu là: " + rt.laySoLuong());
                } else if (luaChon == 6) {
                    System.out.println("Mã số trúng thưởng là: " + rt.rutMotPhieu());
                } else if (luaChon == 7) {
                    System.out.println("Các mã phiếu dự thưởng là: ");
                    rt.inTatCa();
                }
            } while (luaChon != 0);
        }
    }
    ```
    - RutThamTrungThuong_TreeSet.java
    ``` cpp
    package rutthamtrungthuong;

    import java.util.Arrays;
    import java.util.TreeSet;
    import java.util.Random;
    import java.util.Scanner;
    import java.util.Set;

    public class RutThamTrungThuong_TreeSet {

        Set<String> thungPhieuDuThuong = new TreeSet<String>();

        public RutThamTrungThuong_TreeSet() {
        }

        public boolean themPhieu(String giaTri) {
            return this.thungPhieuDuThuong.add(giaTri);
        }

        public boolean xoaPhieu(String giaTri) {
            return this.thungPhieuDuThuong.remove(giaTri);
        }

        public boolean kiemTraPhieu(String giaTri) {
            return this.thungPhieuDuThuong.contains(giaTri);
        }

        public void xoaTatCaPhieu() {
            this.thungPhieuDuThuong.clear();
        }

        public int laySoLuong() {
            return this.thungPhieuDuThuong.size();
        }

        public String rutMotPhieu() {
            String ketQua = "";
            Random rd = new Random();
            int viTri = rd.nextInt(this.thungPhieuDuThuong.size());
            ketQua = (String) this.thungPhieuDuThuong.toArray()[viTri];
            return ketQua;
        }

        public void inTatCa() {
            System.out.println(Arrays.toString(this.thungPhieuDuThuong.toArray()));
        }

        public static void main(String[] args) {
            int luaChon = 0;
            Scanner sc = new Scanner(System.in);
            RutThamTrungThuong_TreeSet rt = new RutThamTrungThuong_TreeSet();
            do {
                System.out.println("-----------MENU----------");
                System.out.println("Chọn chức năng: ");
                System.out.println(
                        "1.  Thêm mã số dự thưởng.\n"
                        + "2.  Xoá mã số dự thưởng.\n"
                        + "3.  Kiểm tra mã số dự thưởng có tồn tại không.\n"
                        + "4.  Xoá toàn bộ mã số dự thưởng.\n"
                        + "5.  Số lượng mã số dự thưởng.\n"
                        + "6.  Rút thăm trúng thưởng.\n"
                        + "0. Thoát.\n"
                );
                luaChon = sc.nextInt();
                sc.nextLine();
                if (luaChon == 1 || luaChon == 2 || luaChon == 3) {
                    System.out.println("Nhập vào mã phiếu dự thưởng: ");
                    String giaTri = sc.nextLine();
                    if (luaChon == 1) {
                        rt.themPhieu(giaTri);
                    } else if (luaChon == 2) {
                        rt.xoaPhieu(giaTri);
                    } else {
                        System.out.println("Kết quả kiểm tra: " + rt.kiemTraPhieu(giaTri));
                    }
                } else if (luaChon == 4) {
                    rt.xoaTatCaPhieu();
                } else if (luaChon == 5) {
                    System.out.println("Số lượng phiếu là: " + rt.laySoLuong());
                } else if (luaChon == 6) {
                    System.out.println("Mã số trúng thưởng là: " + rt.rutMotPhieu());
                } else if (luaChon == 7) {
                    System.out.println("Các mã phiếu dự thưởng là: ");
                    rt.inTatCa();
                }
            } while (luaChon != 0);
        }
    }
    ```
## 6.3: Map    
- `Bài tập`: Tạo 1 chương trình tra từ điển sử dụng HashMap,TreeMap.
    - TuDien_TreeMap.java
    ``` cpp
    package tudien_treemap;

    import java.util.Arrays;
    import java.util.HashMap;
    import java.util.Map;
    import java.util.Scanner;
    import java.util.Set;
    import java.util.TreeMap;

    public class TuDien_TreeMap {

        private Map<String, String> duLieu = new TreeMap<String, String>();

        public String themTu(String tuKhoa, String yNghia) {
            return this.duLieu.put(tuKhoa, yNghia);
        }

        public String xoaTu(String tuKhoa) {
            return this.duLieu.remove(tuKhoa);
        }

        public String traTu(String tuKhoa) {
            String yNghia = this.duLieu.get(tuKhoa);
            return yNghia;
        }

        public void inTuKhoa() {
            Set<String> tapHopTuKhoa = this.duLieu.keySet();
            System.out.println(Arrays.toString(tapHopTuKhoa.toArray()));
        }

        public int laySoLuong() {
            return this.duLieu.size();
        }

        public void xoaTatCa() {
            this.duLieu.clear();
        }

        public static void main(String[] args) {
            TuDien_TreeMap tuDien = new TuDien_TreeMap();
            int luaChon = 0;
            Scanner sc = new Scanner(System.in);
            do {
                System.out.println("---------------");
                System.out.println("MENU ");
                System.out.println("Tra từ điển Anh - Việt:\n"
                        + "1. Thêm từ (Từ khóa, Ý nghĩa)\n"
                        + "2. Xóa từ\n"
                        + "3. Tìm ý nghĩa của từ khóa ⇒ Tra từ\n"
                        + "4. In ra danh sách từ khóa\n"
                        + "5. Lấy số lượng từ\n"
                        + "6. Xóa tất cả các từ khóa\n"
                        + "0. Thoát khỏi chương trình\n"
                        + "");
                luaChon = sc.nextInt();
                sc.nextLine();
                if (luaChon == 1) {
                    System.out.println("Nhập vào từ khóa: ");
                    String tuKhoa = sc.nextLine();
                    System.out.println("Nhập vào ý nghĩa: ");
                    String yNghia = sc.nextLine();
                    tuDien.themTu(tuKhoa, yNghia);
                } else if (luaChon == 2 || luaChon == 3) {
                    System.out.println("Nhập vào từ khóa: ");
                    String tuKhoa = sc.nextLine();
                    if (luaChon == 2) {
                        tuDien.xoaTu(tuKhoa);
                    } else {
                        System.out.println("Ý nghĩa là: " + tuDien.traTu(tuKhoa));
                    }
                } else if (luaChon == 4) {
                    tuDien.inTuKhoa();
                } else if (luaChon == 5) {
                    System.out.println("Số lượng từ khóa là: " + tuDien.laySoLuong());
                } else if (luaChon == 6) {
                    tuDien.xoaTatCa();
                }
            } while (luaChon != 0);
        }
    }

    ```
    - TuDien_HashMap.java
    ``` cpp
    package tudien_treemap;

    import java.util.Arrays;
    import java.util.HashMap;
    import java.util.Map;
    import java.util.Scanner;
    import java.util.Set;
    import java.util.TreeMap;

    public class TuDien_HashMap {

        private Map<String, String> duLieu = new HashMap<String, String>();

        public String themTu(String tuKhoa, String yNghia) {
            return this.duLieu.put(tuKhoa, yNghia);
        }

        public String xoaTu(String tuKhoa) {
            return this.duLieu.remove(tuKhoa);
        }

        public String traTu(String tuKhoa) {
            String yNghia = this.duLieu.get(tuKhoa);
            return yNghia;
        }

        public void inTuKhoa() {
            Set<String> tapHopTuKhoa = this.duLieu.keySet();
            System.out.println(Arrays.toString(tapHopTuKhoa.toArray()));
        }

        public int laySoLuong() {
            return this.duLieu.size();
        }

        public void xoaTatCa() {
            this.duLieu.clear();
        }

        public static void main(String[] args) {
            TuDien_HashMap tuDien = new TuDien_HashMap();
            int luaChon = 0;
            Scanner sc = new Scanner(System.in);
            do {
                System.out.println("---------------");
                System.out.println("MENU ");
                System.out.println("Tra từ điển Anh - Việt:\n"
                        + "1. Thêm từ (Từ khóa, Ý nghĩa)\n"
                        + "2. Xóa từ\n"
                        + "3. Tìm ý nghĩa của từ khóa ⇒ Tra từ\n"
                        + "4. In ra danh sách từ khóa\n"
                        + "5. Lấy số lượng từ\n"
                        + "6. Xóa tất cả các từ khóa\n"
                        + "0. Thoát khỏi chương trình\n"
                        + "");
                luaChon = sc.nextInt();
                sc.nextLine();
                if (luaChon == 1) {
                    System.out.println("Nhập vào từ khóa: ");
                    String tuKhoa = sc.nextLine();
                    System.out.println("Nhập vào ý nghĩa: ");
                    String yNghia = sc.nextLine();
                    tuDien.themTu(tuKhoa, yNghia);
                } else if (luaChon == 2 || luaChon == 3) {
                    System.out.println("Nhập vào từ khóa: ");
                    String tuKhoa = sc.nextLine();
                    if (luaChon == 2) {
                        tuDien.xoaTu(tuKhoa);
                    } else {
                        System.out.println("Ý nghĩa là: " + tuDien.traTu(tuKhoa));
                    }
                } else if (luaChon == 4) {
                    tuDien.inTuKhoa();
                } else if (luaChon == 5) {
                    System.out.println("Số lượng từ khóa là: " + tuDien.laySoLuong());
                } else if (luaChon == 6) {
                    tuDien.xoaTatCa();
                }
            } while (luaChon != 0);
        }
    }
    ```
# 7. Phân biệt List và ArrayList
- Một trong những khác biệt quan trọng nhất giữa List và ArrayList là danh sách đó là một giao diện và ArrayList là một lớp Collection tiêu chuẩn.
- Giao diện List mở rộng khung Collection trong khi đó, ArrayList mở rộng Class trừu tượng và nó thực hiện các giao diện List .
- Không gian tên cho giao diện List là System.Collection.Generic trong khi đó, không gian tên cho ArrayList là System.Collection .
- Giao diện danh sách tạo ra một tập hợp các phần tử được lưu trữ theo trình tự và được xác định hoặc truy cập bằng số chỉ mục của chúng. Mặt khác, ArrayList tạo ra một mảng các đối tượng trong đó mảng có thể tự động phát triển khi được yêu cầu.