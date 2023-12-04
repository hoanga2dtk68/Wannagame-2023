# Soda
[Link tải challange](https://drive.google.com/file/d/1gpK1JOSD9zzj2Zd8M75JBQhDY_U-t1ls/view?usp=drive_link)

![image](https://github.com/hoanga2dtk68/Wannagame-2023/assets/110059218/a455b74c-d79f-4490-a181-9aabba6d61fb)

Các câu hỏi cần phải trả lời

![image](https://github.com/hoanga2dtk68/Wannagame-2023/assets/110059218/7caff8a7-575a-4514-88ee-78031fce7d71)

Dựa vào mô tả của đầu bài chúng ta sẽ tìm những ứng dụng mail có trên máy cụ thể trong phần dữ liệu được cho đó là outlook lấy file ost và dùng systool ost recovery để xem.

**path file ost:\Users\user\AppData\Local\Microsoft\Outlook**

Sau khi xem thì có 1 mail rất đáng nghi ngờ từ tài khoản phanquangkhai10k@gmail.com với đường link tải file khá bất thường

![image](https://github.com/hoanga2dtk68/Wannagame-2023/assets/110059218/b178c067-19cb-44b9-954c-81a750d3fed9)

Sau khi tải file về thì chắc chắn đây là email phishing vì .docx nhưng dạng file lại là file lnk, rất dễ end user nhầm tưởng là file word chứa CV bấm vào và bị thực thi những câu lệnh mà hacker mong muốn. Xem qua câu lệnh của file lnk thì tải về 1 file word và 1 file ps1.

![image](https://github.com/hoanga2dtk68/Wannagame-2023/assets/110059218/c95068af-2c92-42b2-b515-fa2276d427c2)

![image](https://github.com/hoanga2dtk68/Wannagame-2023/assets/110059218/067d1e29-791c-42a3-98be-c38b4cb27880)

Do tác giả đã xóa file ở trên dropbox nhằm tránh dính malware hoặc anti-analyze, chúng ta có thể tìm ở trên dữ liệu mà tác giả đã đưa với file ps1 đã bị obfuscate thì mình dùng tool powerdecode để deobf

![image](https://github.com/hoanga2dtk68/Wannagame-2023/assets/110059218/0e9e3818-44ef-4ec3-8952-f95b3fe0137a)

![image](https://github.com/hoanga2dtk68/Wannagame-2023/assets/110059218/c196de0b-0fc7-435d-852f-ff165fc0ed04)

Có thể thấy file ps1 thực chất là một revshell. Do trình độ rev của mình gần bằng 0 nên quyết định ném nó lên một số sandbox ở đây mình chọn hybrid-analysis

![image](https://github.com/hoanga2dtk68/Wannagame-2023/assets/110059218/cd8d0ea1-8c5b-4c50-99e5-54bda3a60f0b)

Có thể xem thêm dữ liệu phân tích [ở đây](https://www.hybrid-analysis.com/sample/bf9d08ed66d6395a57087be2b8e5d5b86a172e65b3bf94dc9b209088b9bdc345)

Câu cuối hỏi kĩ thuật persistance quay lại phần dữ liệu được thu thập(do không có kĩ năng rev) để xem một số chỗ có thể cắm rất may tác giả đã xóa những folder không cần thiết để mình tìm được ra ở taskscheduele, lên [MITRE](https://attack.mitre.org/) đối chiếu thì đó là kĩ thuật [T1053.005](https://attack.mitre.org/techniques/T1053/005/)

![image](https://github.com/hoanga2dtk68/Wannagame-2023/assets/110059218/0d97917b-dc74-4471-82a4-5c3dabc28c68)

`Flag:  W1{n3v3r_feel_Go0d_c3a164e419244a1efec5d5cf192653ae}`
