<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Thông điệp 2025</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            padding: 45px;
            background-image: url('POSTER.png');
            background-size: cover;
            background-repeat: no-repeat;
            background-position: center;
            background-color: #fff3e0;
        }
        h1 {
            color: #800000;
        }
        .content-box {
            margin: 30px auto;
            padding: 40px;
            border: 3px solid #800000;
            border-radius: 15px;
            background-color: rgba(255, 255, 255, 0.95);
            max-width: 800px;
            font-size: 20px;
            color: #800000;
            line-height: 1.8;
            text-align: left;
        }
        button {
            padding: 15px 25px;
            font-size: 22px;
            color: #fff;
            background-color: #800000;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            margin-top: 20px;
        }
        button:hover {
            background-color: #a33a3a;
        }
    </style>
</head>
<body>
    <h1>Thông điệp 2025 dành cho bạn</h1>
    <div class="content-box" id="content-box">
        Nhấn nút bên dưới để đón nhận thông điệp nào!
    </div>
    <button id="randomButton">Xem thông điệp</button>

    <script>
        const contents = [
            "The Fool (Kẻ Mới Bắt Đầu):<br><strong>Công việc:</strong> Năm mới có thể mang đến cơ hội mới, nhưng bạn cần phải tự tin và sẵn sàng đối mặt với những thử thách chưa biết. Đừng ngần ngại thử điều gì đó mới mẻ.<br><strong>Tình cảm:</strong> Đây là thời điểm bạn có thể bắt đầu một mối quan hệ mới, với sự chân thành và niềm tin vào tương lai.<br><strong>Gia đình:</strong> Cần nhìn nhận lại mối quan hệ gia đình để tạo sự tươi mới và hòa hợp.<br><strong>Bạn bè:</strong> Coi trọng những người bạn cũ và mở lòng đón nhận những mối quan hệ mới.",
            "The Magician (Nhà Pháp Thuật):<br><strong>Công việc:</strong> Bạn có năng lực và khả năng sáng tạo vượt trội. Hãy tận dụng mọi nguồn lực để đạt được thành công trong công việc.<br><strong>Tình cảm:</strong> Bạn có sức hút mạnh mẽ trong mắt người khác, là thời điểm để thể hiện bản thân và tìm kiếm một mối quan hệ ổn định.<br><strong>Gia đình:</strong> Bạn là người tạo động lực và là người lãnh đạo trong gia đình. Hãy khuyến khích mọi người theo đuổi ước mơ của họ.<br><strong>Bạn bè:</strong> Đối với bạn bè, bạn sẽ trở thành nguồn động viên lớn, luôn sẵn sàng giúp đỡ họ đạt được mục tiêu.",
            "The High Priestess (Nữ Tu Sĩ):<br><strong>Công việc:</strong> Đừng vội quyết định vội vàng trong công việc, hãy lắng nghe trực giác và suy nghĩ kỹ lưỡng trước khi hành động.<br><strong>Tình cảm:</strong> Cảm giác bị thu hút bởi ai đó có thể xuất phát từ sự kết nối tâm linh, không chỉ là vật chất.<br><strong>Gia đình:</strong> Sự tĩnh lặng sẽ giúp gia đình bạn tìm lại sự cân bằng và hòa hợp.<br><strong>Bạn bè:</strong> Dành thời gian để lắng nghe và chia sẻ những điều sâu sắc với bạn bè.",
            "The Empress (Nữ Hoàng):<br><strong>Công việc:</strong> Một năm đầy triển vọng với sự phát triển mạnh mẽ, bạn có thể nhận được sự hỗ trợ tài chính hoặc thăng tiến.<br><strong>Tình cảm:</strong> Hãy đón nhận tình yêu và chăm sóc mối quan hệ một cách chân thành.<br><strong>Gia đình:</strong> Gia đình sẽ là nguồn hỗ trợ vững vàng, và bạn có thể tìm thấy sự an ủi từ họ.<br><strong>Bạn bè:</strong> Tình bạn sẽ được nuôi dưỡng, bạn sẽ là người tạo ra bầu không khí ấm áp và tình cảm.",
            "The Emperor (Hoàng Đế):<br><strong>Công việc:</strong> Năm 2025 là thời điểm bạn sẽ có cơ hội trở thành lãnh đạo hoặc điều hành một dự án quan trọng.<br><strong>Tình cảm:</strong> Bạn sẽ trở thành người chịu trách nhiệm trong mối quan hệ. Hãy chắc chắn rằng bạn có thể duy trì sự ổn định.<br><strong>Gia đình:</strong> Tạo dựng nền tảng vững vàng cho gia đình, là người trụ cột trong mọi quyết định.<br><strong>Bạn bè:</strong> Cần phải điều chỉnh vai trò của mình trong các mối quan hệ bạn bè để tránh sự áp đặt.",
            "The Hierophant (Nhà Hiền Triết):<br><strong>Công việc:</strong> Hãy tìm kiếm sự hướng dẫn từ một người có kinh nghiệm hoặc cố gắng học hỏi từ một nguồn tri thức nào đó.<br><strong>Tình cảm:</strong> Mối quan hệ tình cảm có thể mang tính truyền thống hoặc nghiêm túc, bạn sẽ hướng tới một mối quan hệ lâu dài.<br><strong>Gia đình:</strong> Gia đình bạn sẽ tuân theo những nguyên tắc, có thể có sự chú trọng đến tôn giáo hoặc truyền thống.<br><strong>Bạn bè:</strong> Bạn sẽ là người đưa ra lời khuyên sáng suốt cho bạn bè trong các tình huống khó khăn.",
            "The Lovers (Những Người Yêu Nhau):<br><strong>Công việc:</strong> Sự hợp tác và đồng đội sẽ quyết định thành công trong công việc của bạn. Đừng ngại gắn kết với người khác.<br><strong>Tình cảm:</strong> Đây là thời điểm tuyệt vời cho tình yêu, có thể bạn sẽ gặp được 'người ấy' hoặc sự gắn kết trong mối quan hệ hiện tại sẽ được củng cố.<br><strong>Gia đình:</strong> Gia đình sẽ là một nguồn động viên lớn, giúp bạn đi qua mọi thử thách.<br><strong>Bạn bè:</strong> Các mối quan hệ bạn bè sẽ trở nên sâu sắc hơn khi bạn học cách chia sẻ và đồng cảm với họ.",
            "The Chariot (Cỗ Xe Chiến):<br><strong>Công việc:</strong> Bạn sẽ phải làm việc chăm chỉ và có thể phải đối mặt với những thách thức lớn. Tuy nhiên, sự kiên định và kỷ luật sẽ giúp bạn thành công.<br><strong>Tình cảm:</strong> Mối quan hệ có thể gặp thử thách, nhưng bạn sẽ tìm cách vượt qua và tiếp tục đi cùng nhau.<br><strong>Gia đình:</strong> Gia đình có thể gặp phải sự căng thẳng hoặc xung đột, nhưng bạn có thể là người dẫn dắt họ vượt qua.<br><strong>Bạn bè:</strong> Những thử thách sẽ làm cho mối quan hệ bạn bè trở nên mạnh mẽ hơn khi bạn biết cách kiên trì.",
            "Strength (Sức Mạnh):<br><strong>Công việc:</strong> Sự kiên nhẫn và sức mạnh nội tâm sẽ giúp bạn vượt qua những khó khăn trong công việc.<br><strong>Tình cảm:</strong> Mối quan hệ sẽ đòi hỏi bạn phải thể hiện sự kiên nhẫn và lòng bao dung.<br><strong>Gia đình:</strong> Bạn sẽ là người kiên cường trong gia đình, giúp giải quyết vấn đề với sự thông cảm và trí tuệ.<br><strong>Bạn bè:</strong> Được bạn bè tin tưởng và tìm đến khi gặp khó khăn. Sự thấu hiểu của bạn sẽ là chìa khóa.",
            "The Hermit (Nhà Ẩn Dật):<br><strong>Công việc:</strong> Đây là thời gian bạn cần suy nghĩ và tự xem xét lại hướng đi của mình trong sự nghiệp.<br><strong>Tình cảm:</strong> Mối quan hệ có thể cần một chút thời gian và không gian để phát triển, tránh nóng vội.<br><strong>Gia đình:</strong> Gia đình có thể cần một chút tĩnh lặng để tự nhìn nhận lại các vấn đề.<br><strong>Bạn bè:</strong> Một năm dành nhiều thời gian cho bản thân sẽ giúp bạn nhìn nhận lại những mối quan hệ bạn bè quan trọng.",
            "Wheel of Fortune (Cối Xay May Mắn):<br><strong>Công việc:</strong> Những thay đổi lớn có thể đến bất ngờ trong sự nghiệp của bạn. Cơ hội mới hoặc thậm chí một bước ngoặt sẽ xuất hiện. Hãy sẵn sàng thích ứng.<br><strong>Tình cảm:</strong> Mối quan hệ tình cảm có thể có những thay đổi lớn, bạn sẽ phải học cách chấp nhận thay đổi và hiểu rằng mọi thứ luôn có thể thay đổi.<br><strong>Gia đình:</strong> Gia đình có thể gặp một số thay đổi, nhưng đó sẽ là cơ hội để cải thiện mối quan hệ nếu bạn sẵn lòng điều chỉnh.<br><strong>Bạn bè:</strong> Bạn bè sẽ có những thay đổi trong cuộc sống của họ, và có thể bạn sẽ cần hỗ trợ họ trong giai đoạn này.",
            "Justice (Công Lý):<br><strong>Công việc:</strong> Công việc của bạn sẽ đòi hỏi tính công bằng và trung thực. Bạn sẽ nhận được kết quả xứng đáng với những gì đã làm. Nếu bạn cảm thấy có sự bất công, mọi thứ sẽ sớm được giải quyết.<br><strong>Tình cảm:</strong> Mối quan hệ tình cảm sẽ có sự rõ ràng và công bằng. Những quyết định trong tình yêu sẽ được đưa ra một cách công bằng và hợp lý.<br><strong>Gia đình:</strong> Gia đình bạn có thể đối mặt với một vấn đề cần giải quyết công bằng. Sự hòa thuận trong gia đình sẽ đến từ sự thấu hiểu và công bằng.<br><strong>Bạn bè:</strong> Sự công bằng sẽ là chìa khóa trong các mối quan hệ bạn bè. Bạn sẽ nhận lại được sự công nhận từ những người bạn đáng tin cậy.",
            "The Hanged Man (Người Treo Ngược):<br><strong>Công việc:</strong> Đôi khi bạn cần phải thay đổi góc nhìn để tìm ra giải pháp trong công việc. Đừng vội vã quyết định, mà hãy tạm dừng để suy nghĩ lại.<br><strong>Tình cảm:</strong> Mối quan hệ có thể gặp phải những khó khăn và thử thách. Hãy nhìn nhận lại mọi thứ từ một góc độ khác để hiểu rõ hơn về đối phương.<br><strong>Gia đình:</strong> Gia đình sẽ yêu cầu bạn nhìn nhận lại những giá trị cốt lõi và có thể thay đổi quan điểm của bạn về một số vấn đề.<br><strong>Bạn bè:</strong> Bạn có thể phải nhìn nhận lại các mối quan hệ bạn bè, có thể có sự xa cách hoặc những cảm xúc chưa được giải quyết.",
            "Death (Cái Chết):<br><strong>Công việc:</strong> Một chu kỳ cũ trong công việc sẽ kết thúc để mở ra một chu kỳ mới. Đừng sợ sự thay đổi, vì đây chính là cơ hội để bắt đầu lại từ đầu.<br><strong>Tình cảm:</strong> Mối quan hệ có thể kết thúc, nhưng đó cũng là một cơ hội để phát triển bản thân và tạo dựng một mối quan hệ mới tốt đẹp hơn.<br><strong>Gia đình:</strong> Một sự thay đổi trong gia đình có thể khiến bạn cảm thấy không thoải mái. Tuy nhiên, đây là điều cần thiết để tiến về phía trước.<br><strong>Bạn bè:</strong> Bạn sẽ phải đối diện với sự mất mát hoặc thay đổi trong các mối quan hệ bạn bè. Điều này sẽ giúp bạn trưởng thành và hiểu rõ hơn về những gì thực sự quan trọng.",
            "Temperance (Điềm Tĩnh):<br><strong>Công việc:</strong> Bạn sẽ cần sự kiên nhẫn và khả năng làm việc hòa hợp với đồng nghiệp để đạt được thành công. Mọi thứ sẽ không đến nhanh chóng, nhưng nếu kiên trì, kết quả sẽ đến.<br><strong>Tình cảm:</strong> Tình yêu sẽ cần sự hòa hợp và cân bằng. Hãy tìm ra cách để làm cho mối quan hệ của bạn trở nên ổn định và lâu dài.<br><strong>Gia đình:</strong> Gia đình sẽ cần sự hòa hợp, và bạn có thể là người đem lại sự bình yên và điềm tĩnh cho mọi người.<br><strong>Bạn bè:</strong> Cần có sự cân bằng trong mối quan hệ bạn bè. Hãy giữ gìn những mối quan hệ quan trọng và biết cách chia sẻ, thông cảm.",
            "The Devil (Ác Quỷ):<br><strong>Công việc:</strong> Trong công việc, bạn có thể đối mặt với sự cám dỗ hoặc những yếu tố tiêu cực như căng thẳng hoặc những thói quen xấu. Hãy nhận diện những điều này và tìm cách thoát ra.<br><strong>Tình cảm:</strong> Hãy thận trọng với sự kiểm soát hoặc sự lệ thuộc trong tình yêu.<br><strong>Gia đình:</strong> Có thể có sự căng thẳng hoặc một yếu tố tiêu cực trong gia đình. Cần phải đối mặt và giải quyết vấn đề này.<br><strong>Bạn bè:</strong> Bạn bè có thể có những ảnh hưởng xấu đến bạn hoặc bạn có thể cảm thấy bị ràng buộc. Cẩn thận với những người có năng lượng tiêu cực.",
            "The Tower (Tòa Tháp):<br><strong>Công việc:</strong> Một sự thay đổi lớn và đột ngột trong công việc có thể khiến bạn cảm thấy bất ngờ. Tuy nhiên, đây là cơ hội để tái tạo và bắt đầu một tương lai mới tươi sáng hơn.<br><strong>Tình cảm:</strong> Mối quan hệ có thể trải qua một cú sốc lớn. Tuy nhiên, sau khủng hoảng, bạn sẽ thấy rõ ràng hơn về những gì mình thực sự cần trong tình yêu.<br><strong>Gia đình:</strong> Gia đình có thể phải trải qua một sự kiện lớn hoặc biến động, nhưng sau đó sẽ là thời gian để chữa lành và xây dựng lại mối quan hệ.<br><strong>Bạn bè:</strong> Một sự thay đổi trong mối quan hệ bạn bè có thể là một cú sốc, nhưng nó sẽ giúp bạn nhận thức được giá trị của những người bạn thật sự.",
            "The Star (Ngôi Sao):<br><strong>Công việc:</strong> Đây là thời gian bạn sẽ nhìn thấy những cơ hội mới. Cảm giác hy vọng và tươi sáng sẽ giúp bạn tiến gần hơn đến mục tiêu của mình.<br><strong>Tình cảm:</strong> Mối quan hệ sẽ đầy hy vọng và có thể đem lại những kết quả tốt đẹp trong tương lai. Hãy giữ niềm tin vào tình yêu.<br><strong>Gia đình:</strong> Gia đình sẽ trải qua những khoảnh khắc đầy cảm hứng và hỗ trợ lẫn nhau. Sự hòa hợp và tình yêu sẽ là nền tảng vững chắc.<br><strong>Bạn bè:</strong> Bạn sẽ tìm thấy sự hỗ trợ và nguồn động viên từ những người bạn chân thành. Những mối quan hệ này sẽ giúp bạn vượt qua khó khăn.",
            "The Moon (Mặt Trăng):<br><strong>Công việc:</strong> Sự không chắc chắn hoặc những tình huống không rõ ràng có thể xuất hiện trong công việc. Hãy thận trọng và sử dụng trực giác để tìm ra sự thật.<br><strong>Tình cảm:</strong> Tình cảm có thể bị che đậy hoặc hiểu lầm. Đừng để cảm xúc chi phối bạn quá mức.<br><strong>Gia đình:</strong> Gia đình có thể trải qua những giai đoạn mơ hồ hoặc khó khăn. Hãy tìm kiếm sự rõ ràng và giải quyết vấn đề một cách khéo léo.<br><strong>Bạn bè:</strong> Những hiểu lầm hoặc sự mơ hồ có thể xảy ra trong các mối quan hệ bạn bè. Hãy dành thời gian để làm sáng tỏ mọi chuyện.",
            "The Sun (Mặt Trời):<br><strong>Công việc:</strong> Một năm đầy ánh sáng và thành công trong công việc. Bạn sẽ cảm thấy hạnh phúc và tự tin với những thành quả đạt được.<br><strong>Tình cảm:</strong> Tình yêu sẽ đem lại niềm vui và sự hạnh phúc lớn lao. Đây là một thời điểm tuyệt vời để xây dựng một mối quan hệ ổn định và hạnh phúc.<br><strong>Gia đình:</strong> Gia đình bạn sẽ có những khoảnh khắc đáng nhớ và đầy niềm vui. Những mối quan hệ sẽ trở nên gắn kết hơn.<br><strong>Bạn bè:</strong> Bạn bè sẽ là nguồn động viên và mang lại niềm vui cho cuộc sống của bạn. Những tình bạn vững chắc sẽ là chìa khóa cho sự hạnh phúc của bạn."
        ];

        document.getElementById("randomButton").addEventListener("click", function () {
            const randomIndex = Math.floor(Math.random() * contents.length);
            const contentBox = document.getElementById("content-box");

            // Hiển thị nội dung
            contentBox.innerHTML = contents[randomIndex];

            // Lưu trạng thái vào localStorage
            localStorage.setItem('receivedMessage', true);

            // Vô hiệu hóa nút
            this.disabled = true;
            this.textContent = "Đã nhận thông điệp!";
        });

        // Kiểm tra nếu người dùng đã nhận thông điệp trước đó
        if (localStorage.getItem('receivedMessage')) {
            const button = document.getElementById("randomButton");
            button.disabled = true;
            button.textContent = "Đã nhận thông điệp!";
        }
    </script>
</body>
</html>
