# 1. Tìm hiểu về Java Swing
- Java Swing là một phần của Java Foundation Classes (JFC) được sử dụng để tạo các ứng dụng window-based. Nó được xây dựng trên API AWT (Abstract Windowing Toolkit) và được viết hoàn toàn bằng Java.
- Không giống như AWT, Java Swing cung cấp các thành phần không phụ thuộc vào nền tảng và nhẹ hơn.
- Gói javax.swing cung cấp các lớp cho java swing API như JButton, JTextField, JTextArea, JRadioButton, JCheckbox, JMenu, JColorChooser, v.v.
# 2. Phân cấp các lớp Java Swing
![](https://imgur.com/dn61QmN.png)
# 3. JFrame
- Lớp `JFrame` là một lớp kế thừa từ java.awt.Frame mà bổ sung các hỗ trợ cho cấu trúc thành phần `JFC/Swing`. Cú pháp khai báo cho lớp `javax.swing.JFrame là`:
``` cpp
public class JFrame
   extends Frame
      implements WindowConstants, Accessible, RootPaneContainer
```
- Lớp này kế thừa các phương thức từ các lớp sau:
    - java.awt.Frame
    - java.awt.Window
    - java.awt.Container
    - java.awt.Component
    - java.lang.Object
- Lớp JFrame này có các constructor sau:
    - `JFrame()`: Xây dựng một Frame mới, ban đầu là không nhìn thấy (invisible).
    - `JFrame(GraphicsConfiguration gc)`: Tạo một Frame trong GraphicsConfiguration đã cho của một thiết bị màn hình và một title trống.
    - `JFrame(String title)`: Tạo một Frame mới, ban đầu là không nhìn thấy (invisible) với title đã cho.
    - `JFrame(String title, GraphicsConfiguration gc)`: Tạo một Frame với title đã cho và GraphicsConfiguration đã cho của một thiết bị màn hình.
# 4. JTextField
- Lớp `JTextField` trong Java Swing là một thành phần cho phép sửa đổi một dòng text đơn. Dưới đây là cú pháp khai báo của lớp `javax.swing.JTextField`:
``` cpp
public class JTextField extends JTextComponent
        implements SwingConstants
```
- Lớp này kế thừa các phương thức từ các lớp sau:
javax.swing.text.JTextComponent
    - javax.swing.JComponent
    - java.awt.Container
    - java.awt.Component
    - java.lang.Object
- Lớp JTextField có trường static String notifyActio. Trường này là tên của action để gửi thông báo rằng các nội dung của trường này đã được chấp nhận.
- Lớp JTextField này có các constructor sau:
    - `JTextField()`: Xây dựng một TextField mới.
    - `JTextField(Document doc, String text, int columns)`: Xây dựng một JTextField mới mà sử dụng mô hình lưu trữ text đã cho và số cột đã cho.
    - `JTextField(int columns)`: Xây dựng một TextField mới và trống với số cột đã cho.
    - `JTextField(String text)`: Xây dựng một TextField mới được khởi tạo với text đã cho.
    - `JTextField(String text, int columns)`: Xây dựng một TextField mới được khởi tạo với text và các cột đã cho.
- Các phương thức được sử dụng phổ biến của lớp JTextField trong Java Swing:
    - void setActionCommand(String command): 
Thiết lập chuỗi lệnh được sử dụng cho action event
    - void setColumns(int columns): 
Thiết lập số cột trong TextField này, và sau đó làm mất hiệu lựa layout đó
    - void setDocument(Document doc): Liên kết editor với một tài liệu text
    - void setFont(Font f):
Thiết lập font hiện tại
    - void setHorizontalAlignment(int alignment):
Thiết lập căn chỉnh ngang cho text
    - void setScrollOffset(int scrollOffset):
Thiết lập scroll offset, giá trị pixel
    - protected void actionPropertyChanged(Action action, String propertyName):
Cập nhật trạng thái của textfield trong phản hồi các thay đổi của thuộc tính trong action liên kết với
    - void addActionListener(ActionListener l):
Thêm action listener đã cho để nhận các action event từ textfield này
    - protected void configurePropertiesFromAction(Action a):
Thiết lập các thuộc tính của textfield này để kết nối chúng trong Action đã cho
    - protected PropertyChangeListener createActionPropertyChangeListener(Action a):
Tạo và trả về PropertyChangeListener mà chịu trách nhiệm nghe các thay đổi từ Action đã cho và cập nhật các thuộc tính thích hợp

    - protected Document createDefaultModel():
Tạo trình triển khai mặc định của model để được sử dụng tại sự xây dựng nếu không được cung cấp tường minh

    - Action[] getActions():
Gọi danh sách lệnh cho trình soạn thảo Editor

    - void postActionEvent():
Xử lý action event xảy ra trên textfield này bằng cách gửi chúng tới bất cứ đối tượng ActionListener đã được đăng ký nào

    - void removeActionListener(ActionListener l):
Xóa action listener đã cho để nó không bao giờ nhận action event từ textfield này nữa

    - void scrollRectToVisible(Rectangle r):
Cuốn trường này sang trái hoặc phải

    - void setAction(Action a):
Thiết lập Action cho ActionEvent source
# 5. JButton
- Lớp `JButton` trong Java Swing được sử dụng để tạo một nút có thể click. Thành phần này có một label và tạo một sự kiện (event) khi được nhấn. Bạn cũng có thể chèn ảnh vào button.
- Cú pháp của lớp javax.swing.JButton:
``` cpp
public class JButton extends AbstractButton
        implements Accessible
```
- Lớp này kế thừa các phương thức từ các lớp sau:
    - javax.swing.AbstractButton

    - javax.swing.JComponent

    - java.awt.Container

    - java.awt.Component

    - java.lang.Object
- Lớp JButton có các constructor sau:
    - JButton(): Tạo một button mà không thiết lập text hoặc icon.

    - JButton(Action a): Tạo một button tại đây các thuộc tính được nhận từ Action đã cung cấp.

    - JButton(Icon icon): Tạo một button với một icon.

    - JButton(String text): Tạo một button với text.

    - JButton(String text, Icon icon): Tạo một button với text ban đầu và một icon.
- Các phương thức được sử dụng phổ biến của lớp JButton:
    - void removeNotify(): Ghi đè JComponent.removeNotify để kiểm tra xem button này hiện tại được thiết lập như là button mặc định trên RootPane hay không, và nếu có, thiết lập button mặc định của RootPane về null để bảo đảm rằng Rootpane không giữ một tham chiếu button không hợp lệ.

    - void setDefaultCapable(boolean defaultCapable): Thiết lập thuộc tính defaultCapable, mà quyết định xem có hay không button này có thể được tạo là button mặc định cho Root Pane của nó

    - void updateUI(): Phục hồi thuộc tính UI về một giá trị từ L&F hiện tại
# 6. JPanel
- Lớp JPanel là một container chung và gọn nhẹ. Cú pháp khai báo cho lớp javax.swing.JPanel là:
``` cpp
public class JPanel
   extends JComponent
      implements Accessible
```
- Lớp này kế thừa các phương thức từ các lớp sau:
    - javax.swing.JComponent

    - java.awt.Container

    - java.awt.Component

    - java.lang.Object



- Lớp này bao gồm các constructor sau:
    - JPanel(): Tạo một JPanel mới với một double buffer và một Flow Layout.

    - JPanel(boolean isDoubleBuffered): Tạo một JPanel mới với Flow Layout và trình đệm đã xác định.

    - JPanel(LayoutManager layout): Tạo một JPanel mới với Layout Manager đã cho

    - JPanel(LayoutManager layout, boolean isDoubleBuffered): Tạo một JPanel mới với Layout Manager đã cho và trình đệm đã xác định.

- Các phương thức của lớp JPanel
    - AccessibleContext getAccessibleContext(): Lấy AccessibleContext được liên kết với JPanel này.

    - PanelUI getUI(): Trả về đối tượng L&F mà truyền thành phần này

    - String getUIClassID(): Trả về một chuỗi xác định tên của lớp L&F mà truyền thành phần này

    - protected String paramString(): Trả về một biểu diễn chuỗi của JPanel này

    - void setUI(PanelUI ui): Thiết lập đối tượng L&F mà truyền thành phần này

    - void updateUI():Phục hồi thuộc tính UI về một giá trị Look và Feel hiện tại.
# 7. JMenu
- Lớp JMenu trong Java biểu diễn thành phần pull-down menu mà được triển khai từ một thanh trình đơn. Cú pháp khai báo cho lớp javax.swing.JMenu là:
``` cpp
public class JMenu
   extends JMenuItem
      implements Accessible, MenuElement
```
- Lớp này kế thừa các phương thức từ các lớp sau:
    - javax.swing.JAbstractButton

    - javax.swing.JComponent

    - java.awt.Container

    - java.awt.Component

    - java.lang.Object

- Lớp JMenu này có trường protected JMenu.WinListener popupListener.



- Các constructor của lớp JMenu
    - JMenu(): Xây dựng một JMenu mới không có text.

    - JMenu(Action a): Xây dựng một menu có các thuộc tính được nhận từ Action đã cho.

    - JMenu(String s): Xây dựng một JMenu mới với chuỗi s đã cho (như là text của nó).

    - JMenu(String s, boolean b): Xây dựng một JMenu mới với chuỗi s đã cho (như là text của nó) và một giá trị boolean để xác định có hay không một tear-off menu.
# 8. JLabel
- Lớp JLabel trong Java Swing có thể hiển thị hoặc text, hoặc hình ảnh hoặc cả hai. Các nội dung của Label được gán bởi thiết lập căn chỉnh ngang và dọc trong khu vực hiển thị của nó. Theo mặc định, các label được căn chỉnh theo chiều dọc trong khu vực hiển thị. Theo mặc định, text-only label là căn chỉnh theo cạnh, image-only label là căn chỉnh theo chiều ngang.
- Cú pháp khai báo cho lớp javax.swing.JLabel là:

``` cpp
public class JLabel extends JComponent
        implements SwingConstants, Accessible
```
- Lớp javax.swing.JLabel có một trường là protected Component labelFor.
- Constructor của lớp JLabel trong Java Swing
    - JLabel(): Tạo một instance của JLabel, không có hình ảnh, và với một chuỗi trống cho title.

    - JLabel(Icon image): Tạo một instance của JLabel với hình ảnh đã cho.

    - JLabel(Icon image, int horizontalAlignment): Tạo một instance của JLabel với hình ảnh và căn chỉnh ngang đã cho.

    - JLabel(String text): Tạo một instance của JLabel với text đã cho.

    - JLabel(String text, Icon icon, int horizontalAlignment): Tạo một instance của JLabel với text, hình ảnh, và căn chỉnh ngang đã cho.
    - JLabel(String text, int horizontalAlignment): Tạo một instance của JLabel với text và căn chỉnh ngang đã cho.
- Lớp này kế thừa các phương thức từ các lớp sau:
    - javax.swing.JComponent

    - java.awt.Container

    - java.awt.Component

    - java.lang.Object
# 9. JComboBox
- Lớp JComboBox trong Java Swing là một thành phần mà kết hợp một button, một trường có thể chỉnh sửa và một drop-down list. Tại một thời điểm chỉ có một item có thể được lựa chọn từ list. Cú pháp khai báo cho lớp javax.swing.JComboBox là:
``` cpp
public class JComboBox
   extends JComponent
      implements ItemSelectable, ListDataListener, 
         ActionListener, Accessible
```
- Lớp này kế thừa các phương thức từ các lớp sau:
    - javax.swing.JComponent

    - java.awt.Container

    - java.awt.Component

    - java.lang.Object



- Lớp JComboBox bao gồm các trường sau:
    - protected String actionCommand

    - protected ComboBoxModel dataModel

    - protected ComboBoxEditor editor

    - protected boolean isEditable

    - protected JComboBox.KeySelectionManager keySelectionManager

    - protected boolean lightWeightPopupEnabled

    - protected int maximumRowCount

    - protected ListCellRenderer renderer

    - protected Object selectedItemReminder

- Các constructor được sử dụng phổ biến của lớp JComboBox
    - JComboBox(): Tạo một JComboBox với data model mặc định.

    - JComboBox(Object[] items): Tạo một JComboBox mà chứa các phần tử trong mảng đã cho.

    - JComboBox(Vector items): Tạo một JComboBox mà chứa các phần tử trong Vector đã cho.



- Các phương thức được sử dụng phổ biến của lớp JComboBox
    - public void addItem(Object anObject): được sử dụng để thêm một item tới list.

    - public void removeItem(Object anObject): được sử dụng để xóa một item từ list.

    - public void removeAllItems(): được sử dụng để xóa tất cả item từ list.

    - public void setEditable(boolean b): được sử dụng để xác định xem có hay không JComboBox là editable.

    - public void addActionListener(ActionListener a): được sử dụng để thêm ActionListener.

    - public void addItemListener(ItemListener i): được sử dụng để thêm ItemListener.
