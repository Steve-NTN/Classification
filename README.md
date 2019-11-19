# Classification
## Mô tả cách hiểu về câu hỏi và cách giải

- **Perceptron**
  - Không giống như trình phân loại Bayes ngây thơ, một tri giác không sử dụng xác suất để đưa ra quyết định. Thay vào đó, nó giữ một vectơ trọng số w^y của mỗi lớp y. Đưa ra một danh sách tính năng f, perceptron tính toán lớp y có vectơ trọng số tương tự như vectơ đầu vào f. Chính thức, được cung cấp một vectơ đặc trưng f.
  - Duyệt hết các iteration, mỗi iteration sẽ thực hiện vòng lặp duyệt hết điểm dữ liệu.tData là mảng lưu dữ liệu các ảnh, tLabel là mảng lưu các nhãn tương ứng. Nếu mà điểm dữ liệu được phân lớp đúng tức y = y' thì không làm gì cả, còn nếu không thì cập nhập lại điểm đó qua công thức đã cho ở đề. Tiếp tục như thế, còn điểm nào chưa phân lớp thì tiếp tục bước trên, còn nếu hết điểm thì kết thúc thuật toán. 
- **Perceptron Analysis**
  - Hoàn thành ở hàm findHighWeightFeatures(self, label) trong perceptron.py. Nó sẽ trả về một cái danh sách gồm 100 đặc trưng với cái trọng lượng lớn nhất đối với nhãn ấy. 
  - Trả về 1 danh sách 100 tính năng được sắp xếp theo trọng lượng. Duyệt hết các tính năng, mỗi vòng lặp sẽ tính trọng lượng của tính năng đó. Kết thúc vòng lặp sắp xếp tính năng theo trọng lượng và trả về danh sách ấy.
- **MIRA**
  - Việc triển khai bộ xương của trình phân loại MIRA được cung cấp cho bạn trong mira.py. MIRA là một người học trực tuyến có liên quan chặt chẽ với cả máy phân loại vectơ hỗ trợ và phân loại perceptron. Bạn sẽ điền vào hàm trainAndTune. Tương tự như trình phân loại perceptron đa lớp, trình phân loại MIRA đa lớp cũng giữ một vectơ trọng lượng của mỗi nhãn y. Điểm khác với perceptron thì MIRA cập nhật các vectơ trọng lượng của các nhãn này với kích thước bước thay đổi: wy=wy+τf và wy′=wy′−τf. Thêm các ràng buộc với τ.

- **Digit Feature Design**
  - Thêm các tính năng nhị phân mới cho bộ dữ liệu số trong hàm EnhizedFeatureExtractorDigit. Lưu ý có thể mã hóa một tính năng có 3 giá trị [1,2,3] bằng cách sử dụng 3 tính năng nhị phân, trong đó chỉ có một tính năng được bật vào lúc đó, để chỉ ra khả năng nào trong ba khả năng ấy. Về lý thuyết, các tính năng không độc lập có điều kiện như Bayes ngây thơ yêu cầu, nhưng trình phân loại của bạn vẫn có thể hoạt động tốt trong thực tế. Để tăng độ chính xác của trình phân loại của bạn hơn nữa, bạn sẽ cần trích xuất các tính năng hữu ích hơn từ dữ liệu. Khi phân tích kết quả của bộ phân loại, chúng ta nên xem xét một số lỗi của mình và tìm đặc điểm của đầu vào sẽ cung cấp cho bộ phân loại thông tin hữu ích về nhãn. Chúng ta có thể thêm mã vào chức năng phân tích trong dataClassifier.py để kiểm tra xem trình phân loại của chúng ta đang làm gì.
  - Features gồm các thành phần:
    Số lần gấp khúc (đổi hướng từ theo chiều dọc thành chiều ngang hoặc ngược lại).
    Tỉ lệ của ảnh (lấy chiều rộng chia cho chiều dài)
    Số pixel không có giá trị 0
    Số pixel không phải có giá trị 0 ở phía bên trên tấm hình
    Số pixel không phải có giá trị 0 ở phía bên phải tấm hình

- **Behavioral Cloning**
  - Chúng ta đã xây dựng hai loại phân loại khác nhau, phân loại perceptron và mira. Bây giờ chúng ta sẽ sử dụng một phiên bản sửa đổi của perceptron để tìm hiểu từ các tác nhân pacman. Trong câu hỏi này, ta sẽ điền vào các phương pháp phân loại và huấn luyện trong perceptron_pacman.py. Mã này phải tương tự như các phương thức ta đã viết trong perceptron.py. Đối với ứng dụng phân loại này, dữ liệu sẽ là các trạng thái và nhãn cho trạng thái sẽ là tất cả các hành động có thể có từ trạng thái đó. Không giống như perceptron cho các chữ số, tất cả các nhãn đều có chung một vectơ trọng lượng w và các tính năng được trích xuất là một chức năng của cả trạng thái và nhãn có thể.
  - Lặp lại max_iterations lần.
    Lặp lại số lần bằng độ dài trainingDatamax_iterations.
    Lấy từng cặp data vàd đáp án từ trainingData, trainingLabels.
    Với mỗi label trong phần tử thứ 2 trong data lấy ra từng cặp feature, value.
    Nếu label đúng thì trọng số của feature được tăng 1 lượng value nếu sai thì sẽ giảm đi đúng lượng đó.

- **Pacman Feature Design**
  - Thêm các tính năng mới để nhân bản hành vi trong chức năng EnhizedPacmanFeatures trong dataClassifier.py. Trong phần này, bạn sẽ viết các tính năng của riêng mình để cho phép tác nhân phân loại nhân bản hành vi của các tác nhân được quan sát. Một số đại lý được cung cấp để chúng ta cố gắng sao chép hành vi từ:
  - Features gồm các thành phần:
    STOP: bằng 0 nếu action là dừng không sẽ là 0.01
    nearest_ghost: khoảng cách mahattan đến ghost gần nhất
    các thành phần (ghost, i) với i trong khoảng từ 0 đến số ma hiện có: 5 chia cho tổng 0.1 với khoảng cách mahattan đến ghost
    các thành phần (capsule, i) với i trong khoảng từ 0 đến số capsule hiện có: 15 chia cho tổng 1 với khoảng cách mahattan đến capsule
    các thành phần (food, i) với i trong khoảng từ 0 đến số thức ăn hiện có:
    capsule_count: Số capsules nhân với 10
    win: bằng 1 nếu thua ngược lại sẽ là 0
    lose: bằng 1 nếu thua ngược lại sẽ là 0
    score: số điểm nhân với 10

  
## _______________________ The end ___________________________
  
