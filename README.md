# Classification
## Mô tả cách hiểu về câu hỏi và cách giải

- **Perceptron**
  - Không giống như trình phân loại Bayes ngây thơ, một tri giác không sử dụng xác suất để đưa ra quyết định. Thay vào đó, nó giữ một vectơ trọng số w^y của mỗi lớp y. Đưa ra một danh sách tính năng f, perceptron tính toán lớp y có vectơ trọng số tương tự như vectơ đầu vào f. Chính thức, được cung cấp một vectơ đặc trưng f.
  - 
- **Perceptron Analysis**
  - Hoàn thành ở hàm findHighWeightFeatures(self, label) trong perceptron.py. Nó sẽ trả về một cái danh sách gồm 100 đặc trưng với cái trọng lượng lớn nhất đối với nhãn ấy. 
  -
- **MIRA**
  - Việc triển khai bộ xương của trình phân loại MIRA được cung cấp cho bạn trong mira.py. MIRA là một người học trực tuyến có liên quan chặt chẽ với cả máy phân loại vectơ hỗ trợ và phân loại perceptron. Bạn sẽ điền vào hàm trainAndTune. Tương tự như trình phân loại perceptron đa lớp, trình phân loại MIRA đa lớp cũng giữ một vectơ trọng lượng của mỗi nhãn y. Điểm khác với perceptron thì MIRA cập nhật các vectơ trọng lượng của các nhãn này với kích thước bước thay đổi: wy=wy+τf và wy′=wy′−τf. Thêm các ràng buộc với τ.
  -
- **Digit Feature Design**
  - Thêm các tính năng nhị phân mới cho bộ dữ liệu số trong hàm EnhizedFeatureExtractorDigit. Lưu ý có thể mã hóa một tính năng có 3 giá trị [1,2,3] bằng cách sử dụng 3 tính năng nhị phân, trong đó chỉ có một tính năng được bật vào lúc đó, để chỉ ra khả năng nào trong ba khả năng ấy. Về lý thuyết, các tính năng không độc lập có điều kiện như Bayes ngây thơ yêu cầu, nhưng trình phân loại của bạn vẫn có thể hoạt động tốt trong thực tế. Để tăng độ chính xác của trình phân loại của bạn hơn nữa, bạn sẽ cần trích xuất các tính năng hữu ích hơn từ dữ liệu. Khi phân tích kết quả của bộ phân loại, chúng ta nên xem xét một số lỗi của mình và tìm đặc điểm của đầu vào sẽ cung cấp cho bộ phân loại thông tin hữu ích về nhãn. Chúng ta có thể thêm mã vào chức năng phân tích trong dataClassifier.py để kiểm tra xem trình phân loại của chúng ta đang làm gì.
  -
- **Behavioral Cloning**
  - Chúng ta đã xây dựng hai loại phân loại khác nhau, phân loại perceptron và mira. Bây giờ chúng ta sẽ sử dụng một phiên bản sửa đổi của perceptron để tìm hiểu từ các tác nhân pacman. Trong câu hỏi này, ta sẽ điền vào các phương pháp phân loại và huấn luyện trong perceptron_pacman.py. Mã này phải tương tự như các phương thức ta đã viết trong perceptron.py. Đối với ứng dụng phân loại này, dữ liệu sẽ là các trạng thái và nhãn cho trạng thái sẽ là tất cả các hành động có thể có từ trạng thái đó. Không giống như perceptron cho các chữ số, tất cả các nhãn đều có chung một vectơ trọng lượng w và các tính năng được trích xuất là một chức năng của cả trạng thái và nhãn có thể.
  - 
- **Pacman Feature Design**
  - Thêm các tính năng mới để nhân bản hành vi trong chức năng EnhizedPacmanFeatures trong dataClassifier.py. Trong phần này, bạn sẽ viết các tính năng của riêng mình để cho phép tác nhân phân loại nhân bản hành vi của các tác nhân được quan sát. Một số đại lý được cung cấp để chúng ta cố gắng sao chép hành vi từ:

    - StopAgent: Một tác nhân chỉ dừng lại
    - FoodAgent: Một tác nhân chỉ nhằm mục đích ăn thức ăn, không quan tâm đến bất cứ điều gì khác trong môi trường.
    - SuicideAgent: Một tác nhân chỉ di chuyển về phía con ma gần nhất, bất kể nó sợ hay không sợ.
    - ContestAgent: Một nhân viên từ p2 thông minh tránh ma, ăn viên nang năng lượng và thức ăn.
  - 
  
## ____________________________ The end _____________________________
  
