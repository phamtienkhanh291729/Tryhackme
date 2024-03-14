# Introduction to Cyber Security

# Offensive security

1. Khái niệm 

là quá trình đột nhập vào hệ thống máy tính, khai thác lỗi phần mềm và tìm ra sơ hở trong ứng dụng để truy cập trái phép vào chúng. Để bảo mật chúng ta cần phải cư xử như một hacker, tìm ra các lỗ hổng và đề xuất các bản vá trước khi tội phạm mạng thực hiện

Thường được chia ra thành 3 mảng :

- Web Application Security
- Operating System Security
- Network Security
1. Web Application Security
- Giới thiệu
    
    Ứng dụng web giống như một “chương trình” mà chúng ta có thể sử dụng mà không cần cài đặt chỉ cần chúng ta có trình duyệt web, chẳng hạn như Firefox, Safari hoặc Chrome,... Do đó, thay vì cài đặt mọi chương trình bạn cần, bạn chỉ cần duyệt trang liên quan. Sau đây là một số ví dụ về ứng dụng web: Webmail (Outlook, Gmail,…)  bộ ứng dụng văn phòng trực tuyến (Microsoft Office 365, Google Drive,..); mua sắm trực tuyến( Amazon.com, AliExpress,..); cung cấp vô số dịch vụ(ngân hàng trực tuyến, chuyển tiền, mạng xã hội,…)
    
    Ứng dụng web là nó là một chương trình chạy trên một máy chủ từ xa. Máy chủ là hệ thống máy tính chạy liên tục để “phục vụ” khách hàng. Máy chủ sẽ chạy một loại chương trình cụ thể mà trình duyệt web có thể truy cập được.
    
    VD với ứng dụng mua sắm trực tuyến:
    
    - Ứng dụng web sẽ đọc dữ liệu về sản phẩm và thông tin chi tiết của chúng từ máy chủ cơ sở dữ liệu.
    - Cơ *sở dữ liệu* được sử dụng để lưu trữ thông tin một cách có tổ chức bao gồm thông tin về sản phẩm, khách hàng và hóa đơn.
    - Máy *chủ cơ sở dữ liệu* chịu trách nhiệm về nhiều chức năng, bao gồm đọc, tìm kiếm và ghi vào cơ sở dữ liệu. Ứng dụng web mua sắm trực tuyến có thể cần nhiều cơ sở dữ liệu để truy cập, ví dụ:
        - Cơ sở dữ liệu sản phẩm: chứa thông tin chi tiết về sản phẩm
        - Cơ sở dữ liệu khách hàng: chứa tất cả các chi tiết liên quan đến khách hàng
        - Cơ sở dữ liệu bán hàng: khách hàng đã mua gì và họ thanh toán như thế nào
    
    Giả sử kẻ tấn công khai thác (hack) ứng dụng web và đánh cắp cơ sở dữ liệu của khách hàng. Trong trường hợp đó, điều này sẽ dẫn đến tổn thất đáng kể cho công ty và khách hàng.
    
    Hình ảnh mô tả việc tìm kiếm một mặt hàng trên một trang mua sắm trực tuyến:
    
    ![Untitled](Introduction%20to%20Cyber%20Security%20178cf1b17d6940898339aabb27389ee0/Untitled.png)
    
    1. Người dùng nhập tên mặt hàng hoặc từ khóa liên quan vào trường tìm kiếm. Trình duyệt web sẽ gửi (các) từ khóa tìm kiếm đến ứng dụng web mua sắm trực tuyến.
    2. Ứng dụng web truy vấn (tìm kiếm) cơ sở dữ liệu sản phẩm cho các từ khóa đã gửi.
    3. Cơ sở dữ liệu sản phẩm trả về kết quả tìm kiếm phù hợp với từ khóa được cung cấp cho ứng dụng web.
    4. Ứng dụng web định dạng kết quả dưới dạng một trang web thân thiện và trả về cho người dùng.
    
    Nhiều công ty cung cấp các chương trình tiền thưởng lỗi( bug bounty ) cho phép công ty đưa ra phần thưởng cho bất kỳ ai phát hiện ra lỗ hổng bảo mật (điểm yếu) trong hệ thống của công ty. Điều kiện chính là lỗ hổng được tìm thấy nằm trong phạm vi và quy tắc tiền thưởng lỗi
    
- Rủi ro bảo mật ứng dụng web
    
    Giả sử bạn muốn mua một mặt hàng từ một cửa hàng trực tuyến. Có một số chức năng nhất định mà bạn mong đợi có thể thực hiện được trên ứng dụng web này. Thứ tự trực tuyến có thể diễn ra như sau:
    
    ![Untitled](Introduction%20to%20Cyber%20Security%20178cf1b17d6940898339aabb27389ee0/Untitled%201.png)
    
    Có một số loại tấn công phổ biến chính chống lại các ứng dụng web. Hãy xem xét các bước sau đây và các cuộc tấn công liên quan.
    
    - Đăng nhập tại trang web: Kẻ tấn công có thể cố gắng khám phá mật khẩu bằng cách thử nhiều từ. Kẻ tấn công sẽ sử dụng một danh sách dài các mật khẩu bằng một công cụ tự động để kiểm tra chúng trên trang đăng nhập.
    - Tìm kiếm sản phẩm: Kẻ tấn công có thể cố gắng xâm nhập hệ thống bằng cách thêm các ký tự và mã cụ thể vào cụm từ tìm kiếm. Mục tiêu của kẻ tấn công là khiến hệ thống mục tiêu trả về dữ liệu không cần thiết hoặc thực thi một chương trình không đáng lẽ phải làm.
    - Cung cấp chi tiết thanh toán: Kẻ tấn công sẽ kiểm tra xem chi tiết thanh toán được gửi ở dạng văn bản rõ ràng hay sử dụng mã hóa yếu. Mã hóa đề cập đến việc làm cho dữ liệu không thể đọc được nếu không biết khóa bí mật hoặc mật khẩu.
    
    **Identification and Authentication Failure**
    
    Nhận dạng đề cập đến khả năng xác định duy nhất một người dùng. Ngược lại, xác thực đề cập đến khả năng chứng minh rằng người dùng chính là người mà họ tuyên bố. Cửa hàng trực tuyến phải xác nhận danh tính của người dùng và xác thực họ trước khi họ có thể sử dụng hệ thống. Tuy nhiên, bước này dễ mắc phải các loại điểm yếu khác nhau. Điểm yếu ví dụ bao gồm:
    
    - Cho phép kẻ tấn công sử dụng vũ lực, tức là thử nhiều mật khẩu, thường sử dụng các công cụ tự động, để tìm thông tin đăng nhập hợp lệ.
    - Cho phép người dùng chọn mật khẩu yếu. Mật khẩu yếu thường dễ đoán.
    - Lưu trữ mật khẩu của người dùng ở dạng văn bản thuần túy. Nếu kẻ tấn công đọc được tệp chứa mật khẩu, chúng tôi không muốn họ có thể biết được mật khẩu đã lưu trữ.
    
    **Broken Access Control**
    
    Kiểm soát truy cập đảm bảo rằng mỗi người dùng chỉ có thể truy cập các tệp (tài liệu, hình ảnh, v.v.) liên quan đến vai trò hoặc công việc của họ. Ví dụ: bạn không muốn ai đó ở bộ phận tiếp thị truy cập (đọc) tài liệu của bộ phận tài chính. Các lỗ hổng ví dụ liên quan đến kiểm soát truy cập bao gồm:
    
    - Không áp dụng *nguyên tắc đặc quyền tối thiểu* và cấp cho người dùng nhiều quyền truy cập hơn mức họ cần. Ví dụ: khách hàng trực tuyến có thể xem giá của các mặt hàng nhưng họ không thể thay đổi chúng.
    - Có thể xem hoặc sửa đổi tài khoản của người khác bằng cách sử dụng mã định danh duy nhất của tài khoản đó. Ví dụ: bạn không muốn một khách hàng của ngân hàng có thể xem các giao dịch của một khách hàng khác.
    - Có thể duyệt các trang yêu cầu xác thực (đăng nhập) với tư cách là người dùng chưa được xác thực. Ví dụ: chúng tôi không thể cho phép bất kỳ ai xem webmail trước khi đăng nhập
    
    **Injection**
    
    Tấn công tiêm nhiễm đề cập đến một lỗ hổng trong ứng dụng web nơi người dùng có thể chèn mã độc vào đầu vào của họ. Một nguyên nhân của lỗ hổng này là do thiếu xác thực và chuẩn hóa thích hợp đầu vào của người dùng.
    
    **Cryptographic Failures**
    
    Thể loại này đề cập đến những thất bại liên quan đến mật mã. Mật mã học tập trung vào các quá trình mã hóa và giải mã dữ liệu. Mã hóa chuyển văn bản rõ ràng thành văn bản mã hóa, điều này sẽ trở nên vô nghĩa đối với bất kỳ ai không có khóa bí mật để giải mã nó. Nói cách khác, mã hóa đảm bảo rằng không ai có thể đọc dữ liệu mà không biết khóa bí mật. Việc giải mã sẽ chuyển văn bản mã hóa trở lại văn bản gốc bằng cách sử dụng khóa bí mật. Ví dụ về lỗi mật mã bao gồm:
    
    - Gửi dữ liệu nhạy cảm ở dạng văn bản rõ ràng, chẳng hạn như sử dụng HTTP thay vì HTTPS. HTTP là giao thức được sử dụng để truy cập web, trong khi HTTPS là phiên bản bảo mật của HTTP. Những người khác có thể đọc mọi thứ bạn gửi qua HTTP, nhưng không phải HTTPS.
    - Dựa vào một thuật toán mã hóa yếu. Một thuật toán mã hóa cũ là dịch chuyển từng chữ cái một. Ví dụ: “TRY HACK ME” trở thành “USZ IBDL NF.” Thuật toán mật mã này rất dễ bị phá vỡ.
    - Sử dụng khóa mặc định hoặc khóa yếu cho các chức năng mã hóa. Sẽ không khó để phá vỡ mã hóa được sử dụng `1234`làm khóa bí mật.
    
    Chi tiết hơn xem top Ten của OWASP [https://owasp.org/Top10/](https://owasp.org/Top10/)
    
- ctf
    
    Lỗi **IDOR** chương trình cho phép người dùng truy cập tài nguyên (dữ liệu, file, thư mục, database..) một cách trực tiếp thông qua dữ liệu do người dùng cung cấp nhưng kém an toàn. 
    
    vd 
    
    [https://example.com?user_id=1234](https://example.com?user_id=1234)
    
    [https://example.com?user_id=1235](https://example.com?user_id=1235)
    
    kẻ tấn công có thể dễ dàng đọc hay sửa xóa dữ liêu bằng việc thay đổi id
    
    Nguyên nhân cơ chế phân quyền và kiểm soát truy cập người dùng trên website
    
1. Operating System Security
- Giới thiệu
    
    Hàng ngày bạn sử dụng điện thoại thông minh, máy tính xách tay hoặc hầu hết mọi loại máy tính, bạn tương tác trực tiếp hoặc gián tiếp với một hệ điều hành. Các hệ điều hành bao gồm MS Windows, macOS, iOS, Android, Chrome OS và Linux. Để định nghĩa một hệ điều hành, chúng ta cần truy cập vào một thuật ngữ máy tính: phần cứng.
    
    Phần cứng máy tính đề cập đến tất cả các bộ phận và thiết bị ngoại vi của máy tính mà bạn có thể chạm vào bằng tay. Phần cứng bao gồm màn hình, bàn phím, máy in, bộ nhớ flash USB và bo mạch máy tính để bàn. Như thể hiện trong hình bên dưới, bo mạch máy tính để bàn chứa nhiều thành phần, đặc biệt là bộ xử lý trung tâm (CPU) và chip bộ nhớ (RAM). Mặc dù không được hiển thị trong hình bên dưới nhưng bo mạch máy tính để bàn thường được kết nối với thiết bị lưu trữ (HDD hoặc SSD)
    
    ![Untitled](Introduction%20to%20Cyber%20Security%20178cf1b17d6940898339aabb27389ee0/Untitled%202.png)
    
    Bo mạch máy tính để bàn là bộ phận chính của máy tính và tất cả các phần cứng khác từ bàn phím, chuột đến màn hình và máy in đều kết nối với nó. Tuy nhiên, bản thân các thành phần phần cứng sẽ vô dụng nếu bạn muốn chạy các chương trình và ứng dụng yêu thích của mình. Chúng ta cần một hệ điều hành để điều khiển và “điều khiển” chúng.
    
    ![Untitled](Introduction%20to%20Cyber%20Security%20178cf1b17d6940898339aabb27389ee0/Untitled%203.png)
    
    Hệ điều hành (OS) là lớp nằm giữa phần cứng và các ứng dụng, chương trình bạn đang chạy. Các chương trình ví dụ bạn sử dụng hàng ngày có thể bao gồm trình duyệt web như Firefox, Safari và Chrome cũng như ứng dụng nhắn tin như Signal, WhatsApp và Telegram. Tất cả các chương trình, ứng dụng không thể chạy trực tiếp trên phần cứng máy tính; tuy nhiên, chúng chạy trên hệ điều hành. Hệ điều hành cho phép các chương trình này truy cập vào phần cứng theo các quy tắc cụ thể.
    
    Một số hệ điều hành được thiết kế để chạy trên máy tính xách tay và máy tính để bàn cá nhân, chẳng hạn như MS Windows 11 và macOS. Các hệ điều hành khác được thiết kế dành riêng cho điện thoại thông minh, chẳng hạn như Android và iOS. Ngoài ra còn có hệ điều hành dành cho máy chủ; các ví dụ bao gồm [MS Windows Server 2022](https://www.microsoft.com/en-us/windows-server/) , [IBM AIX](https://www.ibm.com/products/aix) và [Oracle Solaris](https://www.oracle.com/solaris) . Cuối cùng, có những hệ điều hành mà bạn có thể sử dụng trên máy tính cá nhân và máy chủ; một ví dụ là Linux. Hình ảnh bên dưới cho thấy mức độ phổ biến của các hệ điều hành khác nhau được sử dụng để duyệt Internet theo [Statcounter](https://gs.statcounter.com/os-market-share) dựa trên dữ liệu được thu thập trong tháng 1 năm 2022.
    
    ![Untitled](Introduction%20to%20Cyber%20Security%20178cf1b17d6940898339aabb27389ee0/Untitled%204.png)
    
    Điện thoại thông minh của bạn có thể đang chạy Android hoặc iOS và bạn có thể có nhiều dữ liệu riêng tư trên đó. Những ví dụ bao gồm: cuộc trò chuyện riêng tư với gia đình và bạn bè của bạn, hình ảnh riêng tư với gia đình và bạn bè, ứng dụng email mà bạn sử dụng để liên lạc cá nhân và công việc, mật khẩu được lưu trong trình duyệt web (hoặc thậm chí trong ghi chú), ứng dụng ngân hàng điện tử,…
    
    Danh sách các dữ liệu bí mật và riêng tư vẫn tiếp tục. Bạn không muốn người mà bạn không tin tưởng mở điện thoại và xem qua ảnh, cuộc trò chuyện và ứng dụng của bạn. Do đó, bạn cần bảo mật điện thoại và hệ điều hành của nó.
    
    Điều tương tự cũng xảy ra với máy tính xách tay hoặc máy tính chạy MS Windows, macOS hoặc Linux của bạn. 
    
    Danh sách có thể rất dài, tùy thuộc vào loại người dùng. Và xem xét tính chất của dữ liệu đã lưu, bạn muốn đảm bảo rằng dữ liệu của mình được an toàn. Khi nói về bảo mật, chúng ta nên nghĩ đến việc bảo vệ ba điều:
    
    - Tính bảo mật: Bạn muốn đảm bảo rằng các tập tin và thông tin bí mật và riêng tư chỉ được cung cấp cho những người được chỉ định.
    - Tính toàn vẹn: Điều quan trọng là không ai có thể giả mạo các tệp được lưu trữ trên hệ thống của bạn hoặc trong khi được truyền trên mạng.
    - Tính khả dụng: Bạn muốn máy tính xách tay hoặc điện thoại thông minh của mình luôn sẵn sàng để sử dụng bất cứ lúc nào bạn quyết định sử dụng.
    
    ![Untitled](Introduction%20to%20Cyber%20Security%20178cf1b17d6940898339aabb27389ee0/Untitled%205.png)
    
- 1 số bảo mật hệ điều hành phổ biến
    
    **Authentication and Weak Passwords**
    
    Xác thực là hành động xác minh danh tính của bạn, có thể là hệ thống cục bộ hoặc hệ thống từ xa. Xác thực có thể đạt được thông qua ba cách chính:
    
    - Thông tin nào đó bạn biết, chẳng hạn như mật khẩu hoặc mã PIN.
    - Một cái gì đó về bạn, chẳng hạn như dấu vân tay.
    - Thứ gì đó bạn có, chẳng hạn như số điện thoại mà bạn có thể nhận được tin nhắn SMS.
    
    Vì mật khẩu là hình thức xác thực phổ biến nhất nên chúng cũng bị tấn công nhiều nhất. Nhiều người dùng có xu hướng sử dụng mật khẩu dễ đoán hoặc giống nhau trên nhiều trang web. Hơn nữa, một số người dùng dựa vào các chi tiết cá nhân như ngày sinh và tên thú cưng của họ, vì nghĩ rằng điều này dễ nhớ và những kẻ tấn công không biết. Tuy nhiên, những kẻ tấn công nhận thức được xu hướng này của người dùng.
    
    Trung tâm An ninh Mạng Quốc gia (NCSC) đã công bố danh sách 100.000 mật khẩu phổ biến nhất [https://www.ncsc.gov.uk/static-assets/documents/PwnedPasswordsTop100k.txt](https://www.ncsc.gov.uk/static-assets/documents/PwnedPasswordsTop100k.txt)
    
    Tóm lại, nếu kẻ tấn công có thể đoán được mật khẩu của bất kỳ tài khoản trực tuyến nào của bạn, chẳng hạn như email hoặc tài khoản mạng xã hội, chúng sẽ có thể truy cập vào dữ liệu riêng tư của bạn. Vì vậy, điều quan trọng là bạn phải chọn mật khẩu phức tạp và sử dụng các mật khẩu khác nhau cho các tài khoản khác nhau.
    
    **Weak File Permissions**
    
    Bảo mật thích hợp đưa ra nguyên tắc đặc quyền tối thiểu. Trong môi trường làm việc, bạn muốn mọi tệp chỉ có thể truy cập được bởi những người cần truy cập vào tệp đó để hoàn thành công việc. Ở cấp độ cá nhân, nếu bạn đang lên kế hoạch cho một chuyến đi với gia đình hoặc bạn bè, bạn có thể muốn chia sẻ tất cả các tệp liên quan đến kế hoạch chuyến đi với những người tham gia chuyến đi đó; bạn không muốn chia sẻ những tập tin đó một cách công khai. Đó là nguyên tắc ít đặc quyền nhất, hay nói một cách đơn giản hơn là “ai có thể truy cập cái gì?”
    
    Quyền truy cập tệp yếu khiến đối thủ dễ dàng tấn công tính bảo mật và tính toàn vẹn. Họ có thể tấn công tính bảo mật vì quyền yếu cho phép họ truy cập các tệp mà lẽ ra họ không thể truy cập. Hơn nữa, chúng có thể tấn công tính toàn vẹn vì chúng có thể sửa đổi các tệp mà lẽ ra chúng không thể chỉnh sửa.
    
    **Access to Malicious Programs**
    
    Tùy thuộc vào loại chương trình độc hại, nó có thể tấn công tính bảo mật, tính toàn vẹn và tính khả dụng.
    
    Một số loại chương trình độc hại, chẳng hạn như ngựa Trojan, cấp cho kẻ tấn công quyền truy cập vào hệ thống của bạn. Do đó, kẻ tấn công có thể đọc tệp của bạn hoặc thậm chí sửa đổi chúng.
    
    Một số loại chương trình độc hại tấn công tính khả dụng. Một ví dụ như vậy là ransomware. Ransomware là một chương trình độc hại mã hóa các tập tin của người dùng. Mã hóa làm cho (các) tệp không thể đọc được nếu không biết mật khẩu mã hóa; nói cách khác, các tập tin sẽ trở nên vô nghĩa nếu không được giải mã (đảo ngược quá trình mã hóa). Kẻ tấn công cung cấp cho người dùng khả năng khôi phục tính khả dụng, tức là lấy lại quyền truy cập vào các tệp gốc của họ: họ sẽ cung cấp cho họ mật khẩu mã hóa nếu người dùng sẵn sàng trả “tiền chuộc”
    
- ctf
    
    lệnh history để xem cách lệnh đã nhập từ khi bắt đầu hoạt động phiên
    
1. Network Security
- Giới thiệu
    
    Mạng máy tính là một nhóm các máy tính và thiết bị được kết nối với nhau. An ninh mạng tập trung vào việc bảo vệ tính bảo mật của các thiết bị này và các liên kết kết nối chúng. (Nói một cách chính xác hơn, an ninh mạng đề cập đến các thiết bị, công nghệ và quy trình để bảo vệ tính bảo mật, tính toàn vẹn và tính khả dụng của mạng máy tính cũng như dữ liệu trên đó.)
    
    An ninh mạng bao gồm các giải pháp phần cứng và phần mềm khác nhau để đạt được các mục tiêu bảo mật đã đặt ra. Giải pháp phần cứng đề cập đến các thiết bị bạn thiết lập trong mạng để bảo vệ an ninh mạng của mình. Chúng là phần cứng nên bạn có thể cầm chúng theo đúng nghĩa đen. Một thiết bị phần cứng có thể trông giống như hình ảnh bên dưới.
    
    ![Untitled](Introduction%20to%20Cyber%20Security%20178cf1b17d6940898339aabb27389ee0/Untitled%206.png)
    
    Ví dụ về các thiết bị phần cứng bao gồm:
    
    - Firewall appliance: Tường lửa cho phép và chặn các kết nối dựa trên một bộ quy tắc được xác định trước. Nó hạn chế những gì có thể vào và những gì có thể rời khỏi mạng.
    - Intrusion Detection System( IDS): IDS phát hiện các hành vi xâm nhập vào hệ thống và mạng cũng như các nỗ lực xâm nhập. Nó cố gắng phát hiện những nỗ lực của kẻ tấn công nhằm đột nhập vào mạng của bạn.
    - Intrusion Prevention System( IPS): IPS chặn phát hiện các hành vi xâm nhập và nỗ lực xâm nhập. Nó nhằm mục đích ngăn chặn những kẻ tấn công xâm nhập vào mạng của bạn.
    - Virtual Private Network ( VPN): VPN đảm bảo rằng bên thứ ba không thể đọc hoặc thay đổi lưu lượng truy cập mạng. Nó bảo vệ tính bảo mật (bí mật) và tính toàn vẹn của dữ liệu được gửi
    
    Mặt khác, chúng tôi có các giải pháp bảo mật phần mềm. Các ví dụ phổ biến là:
    
    - Antivirus software: Bạn cài đặt phần mềm chống vi-rút trên máy tính hoặc điện thoại thông minh của mình để phát hiện các tệp độc hại và chặn chúng thực thi.
    - Host firewall: Không giống như thiết bị tường lửa, thiết bị phần cứng, tường lửa máy chủ là một chương trình được cung cấp như một phần của hệ thống của bạn hoặc là chương trình mà bạn cài đặt trên hệ thống của mình. Ví dụ: MS Windows bao gồm Tường lửa của Bộ bảo vệ Windows và Apple macOS bao gồm tường lửa ứng dụng; cả hai đều là tường lửa máy chủ.
- Phương pháp luận
    
    Mỗi “hoạt động” đều yêu cầu một số hình thức lập kế hoạch để đạt được thành công. Nếu bạn quan tâm đến chụp ảnh động vật hoang dã, bạn không thể chỉ cầm máy ảnh và đi vào rừng trừ khi bạn không quan tâm đến kết quả. Để có chuyến tham quan chụp ảnh động vật hoang dã an toàn và thành công, bạn cần tìm hiểu thêm về những loài động vật bạn muốn chụp bằng máy ảnh của mình. Điều này bao gồm thói quen của động vật và những nguy hiểm cần tránh. Điều tương tự cũng sẽ áp dụng cho một hoạt động quân sự chống lại mục tiêu hoặc đột nhập vào mạng mục tiêu 
    
    ![Untitled](Introduction%20to%20Cyber%20Security%20178cf1b17d6940898339aabb27389ee0/Untitled%207.png)
    
    Việc đột nhập vào mạng mục tiêu thường bao gồm một số bước. Theo [Lockheed Martin](https://www.lockheedmartin.com/en-us/capabilities/cyber/cyber-kill-chain.html) ,  Cyber Kill Chain có bảy bước:
    
    1. Recon: Recon, viết tắt của trinh sát, đề cập đến bước mà kẻ tấn công cố gắng tìm hiểu càng nhiều càng tốt về mục tiêu. Thông tin như loại máy chủ, hệ điều hành, địa chỉ IP, tên người dùng và địa chỉ email có thể giúp cuộc tấn công thành công.
    2. Weaponization: Bước này đề cập đến việc chuẩn bị một tệp có thành phần độc hại, chẳng hạn như để cung cấp cho kẻ tấn công quyền truy cập từ xa.
    3. Delivery: Delivery có nghĩa là phân phối tệp “được vũ khí hóa” tới mục tiêu thông qua bất kỳ phương thức khả thi nào, chẳng hạn như email hoặc bộ nhớ flash USB.
    4. Exploitation: Khi người dùng mở tệp độc hại, hệ thống của họ sẽ thực thi thành phần độc hại.
    5. Installation: Bước trước đó sẽ cài đặt phần mềm độc hại trên hệ thống đích.
    6. Command & Control (C2): Việc cài đặt thành công phần mềm độc hại cung cấp cho kẻ tấn công khả năng ra lệnh và kiểm soát hệ thống mục tiêu.
    7. Actions on Objectives: Sau khi giành được quyền kiểm soát một hệ thống mục tiêu, kẻ tấn công đã đạt được mục tiêu của mình. Một mục tiêu ví dụ là Lọc dữ liệu (đánh cắp dữ liệu của mục tiêu).
    
    Một sự tương tự khác là một tên trộm quan tâm đến ngôi nhà mục tiêu. Kẻ trộm sẽ dành một chút thời gian để tìm hiểu về ngôi nhà mục tiêu, những người sống ở đó, khi nào họ rời đi và khi nào họ trở về nhà. Kẻ trộm sẽ xác định xem họ có camera an ninh và hệ thống báo động hay không. Sau khi đã thu thập đủ thông tin, tên trộm sẽ lên kế hoạch cho chiến lược xâm nhập tốt nhất. Theo một cách nào đó, việc lập kế hoạch và thực hiện hành vi trộm cắp vật lý giống với cuộc tấn công độc hại nhằm mục đích đột nhập vào mạng và đánh cắp dữ liệu.
    
- ctf
    
    dịch vụ mở :
    
    1. Máy chủ FTP: FTP là viết tắt của File Transfer Protocol và được sử dụng để truyền file giữa các máy.
    2. Máy chủ SSH: SSH là viết tắt của Secure Shell và được sử dụng để đăng nhập từ xa an toàn. Nói cách khác, nó cho phép bạn thực thi các lệnh trên hệ thống từ xa một cách an toàn.
    3. Máy chủ HTTP: HTTP là viết tắt của Hypertext Transfer Protocol và được sử dụng cho web. Bất cứ khi nào bạn duyệt web, bạn đang sử dụng HTTP hoặc HTTPS. HTTPS là phiên bản an toàn (được mã hóa) của HTTP.
    
     Thu thập thêm thông tin về máy chủ FTP.
    
    1. Chúng ta sẽ kết nối với máy chủ FTP : ftp+ip
    2. Thử đăng nhập bằng thông tin đăng nhập `anonymous`để xem máy chủ FTP này có hỗ trợ đăng nhập ẩn danh hay không
    3. Tải file `get filename` 
    

# Defensive security

An ninh phòng thủ có phần trái ngược với an ninh tấn công vì nó liên quan đến hai nhiệm vụ chính:

1. Ngăn chặn sự xâm nhập xảy ra
2. Phát hiện sự xâm nhập khi chúng xảy ra và phản hồi đúng cách

Đội xanh là một phần của bối cảnh an ninh phòng thủ.

![Untitled](Introduction%20to%20Cyber%20Security%20178cf1b17d6940898339aabb27389ee0/Untitled%208.png)

- Một số nhiệm vụ liên quan đến an ninh phòng thủ bao gồm:
    - Nhận thức về an ninh mạng của người dùng: đào tạo người dùng về an ninh mạng giúp bảo vệ khỏi các cuộc tấn công khác nhau nhắm vào hệ thống của họ.
    - Lập hồ sơ và quản lý tài sản: chúng ta cần biết các loại hệ thống và thiết bị mà chúng ta phải quản lý và bảo vệ đúng cách.
    - Cập nhật và vá lỗi hệ thống: đảm bảo rằng máy tính, máy chủ và thiết bị mạng được cập nhật và vá chính xác đối với mọi lỗ hổng (điểm yếu) đã biết.
    - Thiết lập các thiết bị bảo mật phòng ngừa: tường lửa và hệ thống ngăn chặn xâm nhập ( IPS) là những thành phần quan trọng của bảo mật phòng ngừa. Tường lửa kiểm soát lưu lượng truy cập mạng nào có thể đi vào bên trong và những gì có thể rời khỏi hệ thống hoặc mạng. IPS chặn mọi lưu lượng truy cập mạng phù hợp với các quy tắc hiện tại và dấu hiệu tấn công.
    - Thiết lập thiết bị ghi nhật ký và giám sát: Nếu không ghi nhật ký và giám sát mạng đúng cách, sẽ không thể phát hiện các hoạt động độc hại và xâm nhập. Nếu một thiết bị trái phép mới xuất hiện trên mạng của chúng tôi, chúng tôi có thể biết.
    

Thường chia làm 2 mảng:

- **Security Operations Center (SOC)**
    
    Trung *tâm điều hành bảo mật* ( SOC ) là một *nhóm* gồm các chuyên gia bảo mật CNTT được giao nhiệm vụ giám sát mạng và hệ thống để phát hiện các sự kiện an ninh mạng độc hại của công ty 24 giờ một ngày, bảy ngày một tuần. 
    
    - Mục đích giám sát của họ là:
        - **Tìm lỗ hổng trên mạng** *Lỗ hổng* SOC là điểm yếu mà kẻ tấn công có thể khai thác để thực hiện những việc vượt quá mức cho phép của chúng. Một lỗ hổng có thể được phát hiện trong phần mềm của bất kỳ thiết bị nào (hệ điều hành và chương trình) trên mạng, chẳng hạn như máy chủ hoặc máy tính. Ví dụ: có thể phát hiện ra một tập hợp máy tính MS Windows phải được vá chống lại một lỗ hổng cụ thể đã được công bố. Nói đúng ra, các lỗ hổng không nhất thiết là trách nhiệm của SOC; tuy nhiên, các lỗ hổng chưa được sửa sẽ ảnh hưởng đến mức độ bảo mật của toàn bộ công ty.Bất cứ khi nào phát hiện ra lỗ hổng hệ thống (điểm yếu), điều cần thiết là phải khắc phục nó bằng cách cài đặt một bản cập nhật hoặc bản vá thích hợp. Khi không có bản sửa lỗi, cần thực hiện các biện pháp cần thiết để ngăn chặn kẻ tấn công khai thác nó. Mặc dù việc khắc phục các lỗ hổng là mối quan tâm sống còn của SOC nhưng nó không nhất thiết phải được giao cho chúng.
        - **Phát hiện hoạt động trái phép**: Hãy xem xét trường hợp kẻ tấn công phát hiện ra tên người dùng và mật khẩu của một trong các nhân viên và sử dụng nó để đăng nhập vào hệ thống công ty. Điều quan trọng là phải nhanh chóng phát hiện loại hoạt động trái phép này trước khi nó gây ra bất kỳ thiệt hại nào. Nhiều manh mối có thể giúp chúng ta phát hiện điều này, chẳng hạn như vị trí địa lý.Hãy xem xét trường hợp tên đăng nhập và mật khẩu của người dùng bị đánh cắp và kẻ tấn công sử dụng chúng để đăng nhập vào mạng. SOC cần phát hiện sự kiện như vậy và ngăn chặn nó càng sớm càng tốt trước khi gây thêm thiệt hại .
        - **Khám phá các vi phạm chính sách:** *Chính sách bảo mật* là một tập hợp các quy tắc và thủ tục được tạo ra để giúp bảo vệ công ty trước các mối đe dọa bảo mật và đảm bảo tuân thủ. Những gì được coi là vi phạm sẽ khác nhau tùy theo từng công ty; các ví dụ bao gồm tải xuống các tệp phương tiện vi phạm bản quyền và gửi các tệp bí mật của công ty một cách không an toàn.
        - **Phát hiện xâm nhập:** *Xâm nhập là* đề cập đến các hành vi xâm nhập vào hệ thống và mạng. Một tình huống ví dụ là kẻ tấn công khai thác thành công ứng dụng web của chúng tôi. Một tình huống ví dụ khác là người dùng truy cập một trang web độc hại và khiến máy tính của họ bị nhiễm virus. Cho dù hệ thống bảo mật của bạn có tốt đến đâu thì vẫn luôn có cơ hội bị xâm nhập. Sự xâm nhập có thể xảy ra khi người dùng nhấp vào liên kết độc hại hoặc khi kẻ tấn công khai thác máy chủ công cộng. Dù bằng cách nào, khi xảy ra sự xâm nhập, chúng ta phải phát hiện nó càng sớm càng tốt để ngăn chặn thiệt hại thêm.
        - **Hỗ trợ ứng phó sự cố:** *Sự cố* .có thể là quan sát, vi phạm chính sách, nỗ lực xâm nhập hoặc điều gì đó gây tổn hại hơn như vi phạm lớn. Việc ứng phó một cách chính xác trước một sự cố nghiêm trọng không phải là một việc dễ dàng. SOC có thể hỗ trợ đội ứng phó sự cố xử lý tình huống
    
    Hoạt động an ninh bao gồm nhiều nhiệm vụ khác nhau để đảm bảo bảo vệ; một trong những nhiệm vụ như vậy là thu thập thông tin về mối đe dọa.
    
    ![Untitled](Introduction%20to%20Cyber%20Security%20178cf1b17d6940898339aabb27389ee0/Untitled%209.png)
    
    - **Threat Intelligence**
        
         I*ntelligence* đề cập đến thông tin bạn thu thập được về kẻ thù thực tế và tiềm năng. Mối *đe dọa* là bất kỳ hành động nào có thể phá vỡ hoặc ảnh hưởng xấu đến hệ thống. Thông tin về mối đe dọa nhằm mục đích thu thập thông tin để giúp công ty chuẩn bị tốt hơn trước các đối thủ tiềm năng. Mục đích là để đạt được *khả năng phòng thủ trước mối đe dọa* . Các công ty khác nhau có những đối thủ khác nhau. Một số đối thủ có thể tìm cách đánh cắp dữ liệu khách hàng từ nhà cung cấp dịch vụ di động; tuy nhiên, các đối thủ khác quan tâm đến việc tạm dừng sản xuất ở một nhà máy lọc dầu. Các đối thủ ví dụ bao gồm đội quân mạng cấp quốc gia hoạt động vì lý do chính trị và nhóm ransomware hoạt động vì mục đích tài chính. Dựa trên công ty (mục tiêu), chúng ta có thể mong đợi những đối thủ.
        
        *Intelligence* cần dữ liệu. Dữ liệu phải được thu thập, xử lý và phân tích. Việc thu thập dữ liệu được thực hiện từ các nguồn cục bộ như nhật ký mạng và các nguồn công cộng như diễn đàn. Việc xử lý dữ liệu nhằm mục đích sắp xếp chúng thành một định dạng phù hợp để phân tích. Giai đoạn phân tích nhằm tìm thêm thông tin về những kẻ tấn công và động cơ của chúng; hơn nữa, nó nhằm mục đích tạo ra một danh sách các khuyến nghị và các bước có thể thực hiện được.
        
        Tìm hiểu về đối thủ của bạn cho phép bạn biết chiến thuật, kỹ thuật và thủ tục của họ. Nhờ thông tin về mối đe dọa, chúng tôi xác định tác nhân đe dọa (đối thủ), dự đoán hoạt động của chúng và do đó, chúng tôi sẽ có thể giảm thiểu các cuộc tấn công của chúng và chuẩn bị chiến lược ứng phó.
        
    - **Data Sources**
        
        SOC sử dụng nhiều nguồn dữ liệu để giám sát mạng nhằm phát hiện các dấu hiệu xâm nhập và phát hiện mọi hành vi nguy hiểm . Một số nguồn này là:
        
        - **Nhật ký máy chủ**: Có nhiều loại máy chủ trên mạng, chẳng hạn như máy chủ thư, máy chủ web và bộ điều khiển miền trên mạng MS Windows. Nhật ký chứa thông tin về các hoạt động khác nhau, chẳng hạn như các lần đăng nhập thành công và thất bại, cùng nhiều hoạt động khác. Có rất nhiều thông tin có thể được tìm thấy trong nhật ký máy chủ.
        - **Hoạt động DNS** DNS`tryhackme.com10.3.13.37` truy vấn DNS`tryhackme.com` máy chủ DNS: là viết tắt của Hệ thống tên miền và nó là giao thức chịu trách nhiệm chuyển đổi tên miền, chẳng hạn như, thành địa chỉ IP, chẳng hạn như , trong số các truy vấn liên quan đến tên miền khác. Một cách tương tự với là hỏi: “Làm cách nào tôi có thể truy cập TryHackMe?” và ai đó trả lời bằng địa chỉ bưu chính. Trong thực tế, nếu ai đó cố duyệt, phải giải quyết vấn đề đó và có thể ghi lại truy vấn DNS để theo dõi. SOC có thể thu thập thông tin về tên miền mà hệ thống nội bộ đang cố gắng liên lạc bằng cách chỉ kiểm tra các truy vấn DNS.
        - **Nhật ký tường lửa**: Tường lửa là một thiết bị kiểm soát các gói mạng vào và ra khỏi mạng chủ yếu bằng cách cho phép chúng đi qua hoặc chặn chúng. Do đó, nhật ký tường lửa có thể tiết lộ nhiều thông tin về những gói đã vượt qua hoặc cố gắng vượt qua tường lửa.
        - **Nhật ký DHCP** DHCP: là viết tắt của Giao thức cấu hình máy chủ động và nó chịu trách nhiệm gán địa chỉ IP cho các hệ thống cố gắng kết nối với mạng. Một sự tương tự với yêu cầu DHCP là khi bạn bước vào một nhà hàng sang trọng và người phục vụ chào đón bạn và hướng dẫn bạn đến một bàn trống. Biết rằng DHCP đã tự động cung cấp cài đặt mạng cho thiết bị của bạn bất cứ khi nào bạn có thể tham gia mạng mà không cần cấu hình thủ công. Bằng cách kiểm tra các giao dịch DHCP, chúng ta có thể tìm hiểu về các thiết bị đã tham gia mạng.
        
        Đây là một số nguồn dữ liệu phổ biến nhất; tuy nhiên, nhiều nguồn khác có thể được sử dụng để hỗ trợ giám sát an ninh mạng và các nhiệm vụ khác của SOC . SOC có thể sử dụng hệ thống Quản lý sự kiện và thông tin bảo mật (SIEM). SIEM tổng hợp dữ liệu từ các nguồn khác nhau để SOC có thể liên kết dữ liệu một cách hiệu quả và ứng phó với các cuộc tấn công.
        
    - **SOC Services**
        
        Dịch vụ SOC bao gồm các dịch vụ phản ứng và chủ động bên cạnh các dịch vụ khác.
        
        Dịch vụ phản ứng đề cập đến các tác vụ được bắt đầu sau khi phát hiện sự xâm nhập hoặc sự kiện độc hại. Ví dụ về các dịch vụ phản ứng bao gồm:
        
        - **Giám sát trạng thái bảo mật** SOC: Đây là vai trò chính của và nó bao gồm giám sát mạng và máy tính để biết các cảnh báo và thông báo bảo mật cũng như phản hồi chúng khi cần thiết.
        - **Quản lý lỗ hổng** : Điều này đề cập đến việc tìm kiếm các lỗ hổng trong hệ thống của công ty và vá (sửa) chúng. SOC có thể hỗ trợ nhiệm vụ này nhưng không nhất thiết phải thực hiện nó
        - **Phân tích phần mềm độc hại :** SOC có thể khôi phục các chương trình độc hại đã truy cập mạng. SOC có thể thực hiện phân tích cơ bản bằng cách thực hiện nó trong môi trường được kiểm soát. Tuy nhiên, phân tích nâng cao hơn yêu cầu gửi nó đến một nhóm chuyên trách.
        - **Phát hiện xâm nhập** *hệ thống phát hiện xâm nhập* IDS được sử dụng để phát hiện và ghi lại các hành vi xâm nhập cũng như các gói đáng ngờ. Công việc của SOC là duy trì một hệ thống như vậy, giám sát các cảnh báo của nó và xem xét nhật ký của nó khi cần thiết.
        - **Báo cáo**: Việc báo cáo sự cố và cảnh báo là điều cần thiết. Báo cáo là cần thiết để đảm bảo quy trình làm việc trôi chảy và hỗ trợ các yêu cầu tuân thủ.
        
        Các dịch vụ chủ động đề cập đến các nhiệm vụ do SOC xử lý mà không có bất kỳ dấu hiệu nào về sự xâm nhập. Ví dụ về các dịch vụ chủ động được SOC thực hiện bao gồm:
        
        - **Giám sát an ninh mạng ( NSM )** : Điều này tập trung vào việc giám sát dữ liệu mạng và phân tích lưu lượng truy cập để phát hiện các dấu hiệu xâm nhập.
        - **Săn lùng mối đe dọa** *việc săn lùng mối đe dọa* SOC với giả định một cuộc xâm nhập đã diễn ra và bắt đầu truy lùng để xem liệu họ có thể xác nhận giả định này hay không.
        - **Thông tin về mối đe dọa** *hệ thống phòng thủ nhận biết được mối đe dọa t*hông tin về mối đe dọa tập trung vào việc tìm hiểu về các đối thủ tiềm năng cũng như các chiến thuật và kỹ thuật của chúng để cải thiện khả năng phòng thủ của công ty. Mục đích là để thiết lập một *hệ thống phòng thủ nhận biết được mối đe dọa* .
        
        Các dịch vụ khác của SOC bao gồm **đào tạo an ninh mạng** . Nhiều hành vi vi phạm và xâm nhập dữ liệu có thể tránh được bằng cách nâng cao nhận thức về bảo mật của người dùng và trang bị cho họ chương trình đào tạo bảo mật vững chắc
        
    
- **Digital Forensics and Incident Response (DFIR)**
    - **Pháp y kỹ thuật số(Digital Forensics)**
        
        Pháp y là việc ứng dụng khoa học để điều tra tội phạm và xác lập sự thật. Với việc sử dụng và phổ biến các hệ thống kỹ thuật số, chẳng hạn như máy tính và điện thoại thông minh, một nhánh pháp y mới đã ra đời để điều tra các tội phạm liên quan: pháp y máy tính, sau này phát triển thành *pháp y kỹ thuật số* .
        
        Trong an ninh phòng thủ, trọng tâm của điều tra kỹ thuật số chuyển sang phân tích bằng chứng về một cuộc tấn công và thủ phạm cũng như các lĩnh vực khác như trộm cắp tài sản trí tuệ, gián điệp mạng và sở hữu nội dung trái phép. Do đó, pháp y kỹ thuật số sẽ tập trung vào các lĩnh vực khác nhau như:
        
        - Hệ thống tệp: Phân tích hình ảnh pháp y kỹ thuật số (bản sao cấp thấp) của bộ lưu trữ của hệ thống sẽ tiết lộ nhiều thông tin, chẳng hạn như các chương trình đã cài đặt, tệp đã tạo, tệp bị ghi đè một phần và tệp đã bị xóa.
        - Bộ nhớ hệ thống: Nếu kẻ tấn công đang chạy chương trình độc hại của chúng trong bộ nhớ mà không lưu nó vào đĩa, thì chụp ảnh pháp y (bản sao cấp thấp) của bộ nhớ hệ thống là cách tốt nhất để phân tích nội dung của nó và tìm hiểu về cuộc tấn công.
        - Nhật ký hệ thống: Mỗi máy khách và máy chủ duy trì các tệp nhật ký khác nhau về những gì đang xảy ra. Tệp nhật ký cung cấp nhiều thông tin về những gì đã xảy ra trên hệ thống. Một số dấu vết sẽ được để lại ngay cả khi kẻ tấn công cố gắng xóa dấu vết của chúng.
        - Nhật ký mạng: Nhật ký của các gói mạng đã đi qua mạng sẽ giúp trả lời nhiều câu hỏi hơn về việc liệu một cuộc tấn công có xảy ra hay không và nó kéo theo những gì.
        
        Hãy suy nghĩ về kịch bản sau đây. Các nhân viên thực thi pháp luật đến hiện trường vụ án; tuy nhiên, một phần của hiện trường vụ án này bao gồm các thiết bị kỹ thuật số và phương tiện truyền thông. Các thiết bị kỹ thuật số bao gồm máy tính để bàn, máy tính xách tay, máy ảnh kỹ thuật số, máy nghe nhạc và điện thoại thông minh, cùng một số thiết bị khác. Phương tiện kỹ thuật số bao gồm CD, DVD, ổ nhớ flash USB và bộ nhớ ngoài. Một số câu hỏi phát sinh:
        
        - Cảnh sát nên thu thập bằng chứng kỹ thuật số như điện thoại thông minh và máy tính xách tay như thế nào? Các quy trình cần tuân theo nếu máy tính và điện thoại thông minh đang chạy là gì?
        - Làm thế nào để chuyển bằng chứng kỹ thuật số? Chẳng hạn, có một số phương pháp hay nhất nhất định cần tuân theo khi di chuyển máy tính không?
        - Làm thế nào để phân tích các bằng chứng kỹ thuật số được thu thập? Dung lượng lưu trữ của thiết bị cá nhân nằm trong khoảng từ hàng chục gigabyte đến vài terabyte; làm thế nào điều này có thể được phân tích?
        
        Giả sử nhân viên này bị nghi ngờ trong hình trên, chúng ta có thể nhanh chóng thấy các thiết bị kỹ thuật số có thể được điều tra quan tâm. Chúng tôi nhận thấy máy tính bảng, điện thoại thông minh, máy ảnh kỹ thuật số và bộ nhớ flash USB ngoài máy tính để bàn. Bất kỳ thiết bị nào trong số này đều có thể chứa rất nhiều thông tin có thể giúp ích cho việc điều tra. Việc xử lý những thứ này làm bằng chứng sẽ yêu cầu pháp y kỹ thuật số.
        
        Chính thức hơn, pháp y kỹ thuật số là ứng dụng của khoa học máy tính để điều tra bằng chứng kỹ thuật số cho mục đích pháp lý. Pháp y kỹ thuật số được sử dụng trong hai loại điều tra:
        
        1. **Các cuộc điều tra trong khu vực công**
            
            đề cập đến các cuộc điều tra được thực hiện bởi chính phủ và các cơ quan thực thi pháp luật. Họ sẽ là một phần của một cuộc điều tra tội phạm hoặc dân sự.
            
        2. **Các cuộc điều tra của khu vực tư nhân**
            
            đề cập đến các cuộc điều tra được thực hiện bởi các cơ quan doanh nghiệp bằng cách chỉ định một điều tra viên tư nhân, dù là nội bộ hay thuê ngoài. Chúng được kích hoạt bởi các vi phạm chính sách của công ty.
            
        
        Cho dù điều tra tội phạm hay vi phạm chính sách của công ty, một phần bằng chứng đều liên quan đến thiết bị kỹ thuật số và phương tiện truyền thông kỹ thuật số. Đây là lúc pháp y kỹ thuật số phát huy tác dụng và cố gắng xác định điều gì đã xảy ra. Nếu không có các nhà điều tra pháp y kỹ thuật số được đào tạo, sẽ không thể xử lý bất kỳ bằng chứng kỹ thuật số nào một cách chính xác.
        
        Với tư cách là điều tra viên pháp y kỹ thuật số, bạn đến một cảnh tương tự như cảnh trong hình trên. Bạn nên làm gì với tư cách là điều tra viên pháp y kỹ thuật số? Sau khi nhận được sự cho phép hợp pháp thích hợp, kế hoạch cơ bản sẽ diễn ra như sau:
        
        1. Thu thập bằng chứng: Thu thập các thiết bị kỹ thuật số như máy tính xách tay, thiết bị lưu trữ và máy ảnh kỹ thuật số. (Lưu ý rằng máy tính xách tay và máy tính cần được xử lý đặc biệt nếu chúng được bật; tuy nhiên, điều này nằm ngoài phạm vi của phòng này.)
        2. Thiết lập chuỗi hành trình sản phẩm: Điền vào biểu mẫu liên quan một cách thích hợp ( [Mẫu mẫu](https://www.nist.gov/document/sample-chain-custody-formdocx)). Mục đích là để đảm bảo rằng chỉ những điều tra viên được ủy quyền mới có quyền truy cập vào bằng chứng và không ai có thể giả mạo nó.
        3. Đặt bằng chứng vào hộp đựng an toàn: Bạn muốn đảm bảo rằng bằng chứng không bị hư hỏng. Trong trường hợp điện thoại thông minh, bạn muốn đảm bảo rằng chúng không thể truy cập mạng để chúng không bị xóa từ xa.
        4. Vận chuyển bằng chứng đến phòng thí nghiệm pháp y kỹ thuật số của bạn.
        
        Tại phòng thí nghiệm, quá trình này diễn ra như sau:
        
        1. Lấy bằng chứng kỹ thuật số từ thùng chứa an toàn.
        2. Tạo bản sao pháp y của bằng chứng: Bản sao pháp y yêu cầu phần mềm tiên tiến để tránh sửa đổi dữ liệu gốc.
        3. Trả lại bằng chứng kỹ thuật số vào hộp đựng an toàn: Bạn sẽ làm việc trên bản sao. Nếu bạn làm hỏng bản sao, bạn luôn có thể tạo một bản sao mới.
        4. Bắt đầu xử lý bản sao trên máy trạm điều tra của bạn.
        
        Các bước trên đã được điều chỉnh từ [Hướng dẫn điều tra và pháp y máy tính, Phiên bản thứ 6](https://www.cengage.uk/shop/isbn/9781337568944) .
        
        Tổng quát hơn, theo cựu giám đốc Phòng thí nghiệm pháp y máy tính quốc phòng, Ken Zatyko, pháp y kỹ thuật số bao gồm:
        
        - Thẩm quyền tìm kiếm thích hợp: Các nhà điều tra không thể bắt đầu nếu không có thẩm quyền pháp lý phù hợp.
        - Chuỗi hành trình sản phẩm: Điều này là cần thiết để theo dõi xem ai đang nắm giữ bằng chứng vào bất kỳ lúc nào.
        - Xác thực bằng toán học: Sử dụng một loại hàm toán học đặc biệt, được gọi là hàm băm, chúng tôi có thể xác nhận rằng tệp chưa bị sửa đổi.
        - Sử dụng các công cụ đã được xác thực: Các công cụ được sử dụng trong pháp y kỹ thuật số phải được xác thực để đảm bảo rằng chúng hoạt động chính xác. Ví dụ: nếu bạn đang tạo hình ảnh của một đĩa, bạn muốn đảm bảo rằng hình ảnh pháp y giống hệt với dữ liệu trên đĩa.
        - Khả năng lặp lại: Các phát hiện của pháp y kỹ thuật số có thể được sao chép miễn là có sẵn các kỹ năng và công cụ phù hợp.
        - Báo cáo: Cuộc điều tra pháp y kỹ thuật số được kết thúc bằng một báo cáo hiển thị bằng chứng liên quan đến vụ án được phát hiện
        
        ctf : pdfinfo đọc file pdf; exiftool đọc file jpg
        
    - **Ứng phó sự cố (Incident Response)**
        
        Sự *cố* thường đề cập đến vi phạm dữ liệu hoặc tấn công mạng; tuy nhiên, trong một số trường hợp, đó có thể là lỗi ít nghiêm trọng hơn, chẳng hạn như cấu hình sai, nỗ lực xâm nhập hoặc vi phạm chính sách. Ví dụ về một cuộc tấn công mạng bao gồm kẻ tấn công làm cho mạng hoặc hệ thống của chúng tôi không thể truy cập được, làm mất giao diện (thay đổi) trang web công cộng và vi phạm dữ liệu (đánh cắp dữ liệu của công ty). Bạn sẽ *phản ứng* thế nào trước một cuộc tấn công mạng? Ứng phó sự cố chỉ rõ phương pháp cần tuân thủ để xử lý trường hợp đó. Mục đích là giảm thiệt hại và phục hồi trong thời gian ngắn nhất có thể. Lý tưởng nhất là bạn nên xây dựng một kế hoạch sẵn sàng ứng phó với sự cố.
        
        Bốn giai đoạn chính của quá trình ứng phó sự cố là:
        
        1. Chuẩn bị: Việc này đòi hỏi một đội ngũ được đào tạo bài bản và sẵn sàng xử lý các sự cố. Lý tưởng nhất là áp dụng nhiều biện pháp khác nhau để ngăn chặn sự cố xảy ra ngay từ đầu.
        2. Phát hiện và phân tích: Nhóm có các nguồn lực cần thiết để phát hiện bất kỳ sự cố nào; hơn nữa, điều cần thiết là phải phân tích sâu hơn bất kỳ sự cố nào được phát hiện để tìm hiểu về mức độ nghiêm trọng của nó.
        3. Ngăn chặn, loại bỏ và phục hồi: Sau khi phát hiện sự cố, điều quan trọng là phải ngăn chặn nó ảnh hưởng đến các hệ thống khác, loại bỏ nó và khôi phục các hệ thống bị ảnh hưởng. Ví dụ: khi chúng tôi nhận thấy một hệ thống bị nhiễm vi-rút máy tính, chúng tôi muốn ngăn chặn (chứa) vi-rút lây lan sang các hệ thống khác, làm sạch (tiêu diệt) vi-rút và đảm bảo khôi phục hệ thống thích hợp.
        4. Hoạt động sau sự cố: Sau khi khôi phục thành công, một báo cáo sẽ được tạo và bài học kinh nghiệm được chia sẻ để ngăn chặn những sự cố tương tự trong tương lai.
        
        ![Untitled](Introduction%20to%20Cyber%20Security%20178cf1b17d6940898339aabb27389ee0/Untitled%2010.png)
        
    - **Phân tích phần mềm độc hại(Malware Analysis)**
        
        Phần mềm độc hại là viết tắt của phần mềm độc hại. *Phần mềm* đề cập đến các chương trình, tài liệu và tệp mà bạn có thể lưu trên đĩa hoặc gửi qua mạng. Phần mềm độc hại bao gồm nhiều loại, chẳng hạn như:
        
        - Virus là một đoạn mã (một phần của chương trình) tự gắn vào chương trình. Nó được thiết kế để lây lan từ máy tính này sang máy tính khác; hơn nữa, nó hoạt động bằng cách thay đổi, ghi đè và xóa các tập tin sau khi lây nhiễm vào máy tính. Kết quả dao động từ việc máy tính trở nên chậm chạp đến không thể sử dụng được.
        - Trojan Horse là một chương trình hiển thị một chức năng mong muốn nhưng lại ẩn chứa một chức năng độc hại bên dưới. Ví dụ: nạn nhân có thể tải xuống trình phát video từ một trang web mờ ám để kẻ tấn công có toàn quyền kiểm soát hệ thống của họ.
        - Ransomware là một chương trình độc hại mã hóa các tập tin của người dùng. Mã hóa làm cho các tập tin không thể đọc được nếu không biết mật khẩu mã hóa. Kẻ tấn công cung cấp cho người dùng mật khẩu mã hóa nếu người dùng sẵn sàng trả “tiền chuộc”.
        
        Phân tích phần mềm độc hại nhằm mục đích tìm hiểu về các chương trình độc hại như vậy bằng nhiều cách khác nhau:
        
        1. Phân tích tĩnh hoạt động bằng cách kiểm tra chương trình độc hại mà không cần chạy nó. Thông thường, điều này đòi hỏi kiến thức vững chắc về hợp ngữ (bộ hướng dẫn của bộ xử lý, tức là các hướng dẫn cơ bản của máy tính).
        2. Phân tích động hoạt động bằng cách chạy phần mềm độc hại trong môi trường được kiểm soát và giám sát các hoạt động của nó. Nó cho phép bạn quan sát cách phần mềm độc hại hoạt động khi chạy.

# **Careers in Cyber**

- Security Analyst
    
    *Chịu trách nhiệm duy trì tính bảo mật dữ liệu của tổ chức*
    
    Các nhà phân tích bảo mật đóng vai trò không thể thiếu trong việc xây dựng các biện pháp bảo mật trong các tổ chức nhằm bảo vệ công ty khỏi các cuộc tấn công. Các nhà phân tích khám phá và đánh giá mạng lưới công ty để tìm ra dữ liệu hữu ích và đề xuất cho các kỹ sư để phát triển các biện pháp phòng ngừa. Vai trò công việc này yêu cầu làm việc với nhiều bên liên quan khác nhau để hiểu rõ về các yêu cầu bảo mật và bối cảnh bảo mật
    
    **Trách nhiệm**
    
    - Làm việc với các bên liên quan khác nhau để phân tích an ninh mạng trong toàn công ty
    - Biên soạn các báo cáo liên tục về sự an toàn của mạng, ghi lại các vấn đề bảo mật và các biện pháp được thực hiện để ứng phó
    - Phát triển các kế hoạch bảo mật, kết hợp nghiên cứu về các công cụ và xu hướng tấn công mới cũng như các biện pháp cần thiết giữa các nhóm để duy trì bảo mật dữ liệu.
- Security Engineer
    
    *Thiết kế, giám sát và duy trì các biện pháp kiểm soát bảo mật, mạng và hệ thống để giúp ngăn chặn các cuộc tấn công mạng*
    
    Các kỹ sư bảo mật phát triển và triển khai các giải pháp bảo mật bằng cách sử dụng dữ liệu về các mối đe dọa và lỗ hổng bảo mật - thường được lấy từ các thành viên của lực lượng bảo mật. Các kỹ sư bảo mật làm việc để tránh nhiều cuộc tấn công, bao gồm các cuộc tấn công ứng dụng web, các mối đe dọa mạng cũng như các xu hướng và chiến thuật đang phát triển. Mục tiêu cuối cùng là duy trì và áp dụng các biện pháp bảo mật để giảm thiểu nguy cơ bị tấn công và mất dữ liệu.
    
    **Trách nhiệm**
    
    - Kiểm tra và sàng lọc các biện pháp bảo mật trên phần mềm
    - Giám sát mạng và báo cáo để cập nhật hệ thống và giảm thiểu lỗ hổng
    - Xác định và triển khai các hệ thống cần thiết để bảo mật tối ưu
- Incident Responder
    
    *Xác định và giảm thiểu các cuộc tấn công trong khi hoạt động của kẻ tấn công vẫn đang diễn ra*
    
    Người ứng phó sự cố phản ứng một cách hiệu quả và hiệu quả đối với các vi phạm an ninh. Trách nhiệm bao gồm việc tạo ra các kế hoạch, chính sách và giao thức để các tổ chức ban hành trong và sau các sự cố. Đây thường là một vị trí chịu áp lực cao với các đánh giá và phản hồi cần thiết trong thời gian thực khi các cuộc tấn công đang diễn ra. Các số liệu ứng phó sự cố bao gồm MTTD, MTTA và MTTR - trong khi đó để phát hiện, xác nhận và phục hồi (sau các cuộc tấn công.) Mục đích là đạt được phản ứng nhanh chóng và hiệu quả, duy trì tình trạng tài chính và tránh các tác động tiêu cực đến vi phạm. Cuối cùng, những người ứng phó sự cố sẽ bảo vệ dữ liệu, danh tiếng và tình hình tài chính của công ty khỏi các cuộc tấn công mạng.
    
    **Trách nhiệm**
    
    - Xây dựng và áp dụng kế hoạch ứng phó sự cố toàn diện, khả thi
    - Duy trì các phương pháp thực hành tốt nhất về bảo mật mạnh mẽ và hỗ trợ các biện pháp ứng phó sự cố
    - Báo cáo sau sự cố và chuẩn bị cho các cuộc tấn công trong tương lai, xem xét các bài học và biện pháp thích ứng để rút ra từ các sự cố
- Digital Forensics Examiner
    
    *Chịu trách nhiệm sử dụng pháp y kỹ thuật số để điều tra các sự cố và tội phạm*
    
    Nếu bạn thích đóng vai thám tử thì đây có thể là công việc hoàn hảo. Nếu bạn đang làm việc trong bộ phận thực thi pháp luật, bạn sẽ tập trung vào việc thu thập và phân tích bằng chứng để giúp giải quyết tội phạm: buộc tội kẻ có tội và miễn tội cho người vô tội. Mặt khác, nếu công việc của bạn thuộc phạm vi bảo vệ mạng của công ty, bạn sẽ sử dụng các kỹ năng điều tra của mình để phân tích các sự cố, chẳng hạn như vi phạm chính sách.
    
    **Trách nhiệm**
    
    - Thu thập bằng chứng kỹ thuật số trong khi quan sát các thủ tục pháp lý
    - Phân tích bằng chứng kỹ thuật số để tìm câu trả lời liên quan đến vụ án
    - Ghi lại những phát hiện của bạn và báo cáo về vụ việc
- Malware Analyst
    
    *Phân tích tất cả các loại phần mềm độc hại để tìm hiểu thêm về cách chúng hoạt động và chức năng của chúng*
    
    Công việc của nhà phân tích phần mềm độc hại bao gồm phân tích các chương trình đáng ngờ, khám phá những gì chúng làm và viết báo cáo về những phát hiện của chúng. Nhà phân tích phần mềm độc hại đôi khi được gọi là kỹ sư đảo ngược vì nhiệm vụ cốt lõi của họ xoay quanh việc chuyển đổi các chương trình đã biên dịch từ ngôn ngữ máy sang mã có thể đọc được, thường là bằng ngôn ngữ cấp thấp. Công việc này đòi hỏi người phân tích phần mềm độc hại phải có nền tảng lập trình vững chắc, đặc biệt là các ngôn ngữ cấp thấp như hợp ngữ và ngôn ngữ C. Mục tiêu cuối cùng là tìm hiểu về tất cả các hoạt động mà một chương trình độc hại thực hiện, tìm ra cách phát hiện và báo cáo nó.
    
    **Trách nhiệm**
    
    - Thực hiện phân tích tĩnh các chương trình độc hại đòi hỏi kỹ thuật đảo ngược
    - Tiến hành phân tích động các mẫu phần mềm độc hại bằng cách quan sát hoạt động của chúng trong môi trường được kiểm soát
    - Ghi lại và báo cáo tất cả các phát hiện
- Penetration Tester
    
    *Chịu trách nhiệm kiểm tra các sản phẩm công nghệ để phát hiện lỗ hổng bảo mật*
    
    Bạn có thể thấy thử nghiệm thâm nhập được gọi là pentesting và hack đạo đức. Vai trò công việc của người kiểm tra thâm nhập là kiểm tra tính bảo mật của hệ thống và phần mềm trong công ty - điều này đạt được thông qua nỗ lực phát hiện ra các lỗ hổng và lỗ hổng thông qua việc hack có hệ thống. Người kiểm tra thâm nhập khai thác các lỗ hổng này để đánh giá rủi ro trong từng trường hợp. Sau đó, công ty có thể sử dụng những hiểu biết này để khắc phục các vấn đề nhằm ngăn chặn một cuộc tấn công mạng trong thế giới thực.
    
    **Trách nhiệm**
    
    - Tiến hành kiểm tra trên hệ thống máy tính, mạng và ứng dụng dựa trên web
    - Thực hiện đánh giá bảo mật, kiểm toán và phân tích chính sách
    - Đánh giá và báo cáo những hiểu biết sâu sắc, đề xuất hành động để ngăn chặn tấn công
- Red Teamer
    
    *Đóng vai kẻ thù, tấn công tổ chức và đưa ra phản hồi từ góc độ kẻ thù*
    
    Các thành viên của đội đỏ có những điểm tương đồng với những người thử nghiệm thâm nhập, với vai trò công việc được nhắm mục tiêu nhiều hơn. Những người thử nghiệm thâm nhập tìm cách phát hiện ra nhiều lỗ hổng trên các hệ thống để duy trì hoạt động phòng thủ mạng ở trạng thái tốt, trong khi các nhóm đỏ được cử đi kiểm tra khả năng phát hiện và phản hồi của công ty. Vai trò công việc này yêu cầu bắt chước hành động của tội phạm mạng, mô phỏng các cuộc tấn công độc hại, giữ quyền truy cập và tránh bị phát hiện. Quá trình đánh giá của đội đỏ có thể kéo dài tới một tháng, thường do một nhóm bên ngoài công ty thực hiện. Chúng thường phù hợp nhất với các tổ chức có sẵn các chương trình bảo mật hoàn thiện.
    
    **Trách nhiệm**
    
    - Mô phỏng vai trò của tác nhân đe dọa để phát hiện các lỗ hổng có thể khai thác, duy trì quyền truy cập và tránh bị phát hiện
    - Đánh giá các biện pháp kiểm soát an ninh, thông tin về mối đe dọa và quy trình ứng phó sự cố của tổ chức
    - Đánh giá và báo cáo thông tin chi tiết, với dữ liệu hữu ích cho các công ty để tránh các trường hợp thực tế