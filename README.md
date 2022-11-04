"# xphom_rule" 
Luật đánh phỏm

1.	Luật cơ bản phỏm
Phỏm: Là bộ gồm 3 quân bài trở lên có cùng chất và số liên tiếp nhau hoặc bộ 3 quân bài khác chất nhưng cùng số.
Bài rác: Những lá bài lẻ không thuộc Phỏm nào.
Nọc: Các lá bài còn dư sau khi chia cho người chơi.
Móm: Kết thúc ván, người chơi không hạ được Phỏm nào thì gọi là Móm.
Ù: Khi tất cả 9 lá bài đều có phỏm và không còn bài rác.
Ăn chốt: Ăn bài người chơi trước ở lượt đánh cuối.
Đền: Trong lượt đánh cuối, nếu người chơi Ăn chốt của người ngồi trước thì bất kì người chơi nào sau lượt đánh của người đó Ù thì người chơi vừa ăn chốt sẽ bị đền. Người ăn chốt sau sẽ phải đền thay người ăn chốt trước. Lưu ý: Người chơi cũng bị tính là đền nếu bị ăn 3 lá bài liên tục.
Tái: Sau khi hạ bài, nếu trong bàn có người ăn, các quân bài đã đánh ra sẽ được chuyển chỗ và bạn được phép đánh thêm một lượt.
Gửi: Ở lượt cuối, nếu bài rác của bạn có thể kết nạp vào Phỏm của những người chơi đã hạ bài thì bạn có thể Gửi lá bài rác đó đi. Lá bài được gửi đi sẽ không bị tính điểm khi kết thúc ván.

2.	Thuật toán chơi
-	Client gửi info tất cả các lá bài đã lộ lên cho server (10 lá bài của mình và các cây đánh của các nhà khác)
-	Xét ưu tiên lá bài trong bài mình là lá què to nhất, xác suất bị ăn thấp nhất thì đánh trước (nếu trường hợp có >= 2 lá 100% ko bị ăn thì để lại lá bé hơn làm chốt, còn nếu chỉ có 1 lá thì sẽ để dành đánh chốt).
 
Sơ đồ vị trí ngồi và hướng đánh bài

-	Cách tính xác suất lá bị ăn như sau:
•	Vd lá 10 sẽ có 7 trường hợp bị ăn như sau: 10rô 10cơ 10bích, 10rô 10cơ 10tép, 10cơ 10bích 10tép, 10 10 10 10, 8 9 10, 9 10 J, 10 J Q.
•	Riêng lá át vs K thì ít hơn 2 trường hợp.
-	Cây 10 rô 100% không bị nhà bên phải ăn khi gặp các th sau:
o	Người chơi phải đã đánh 1 cây Q nào đó và đã xuất hiện 9 rô, J rô, hoặc 8 rô, J rô
o	Người chơi phải chưa đánh Q nào nhưng đã biết 2 cây Q khác và đã xuất hiện 9 rô J rô hoặc 8 rô J rô
-	Cây 10 rô khó bị nhà bên phải ăn khi gặp các th sau:
Người chơi phải đã đánh 9 tép hoặc 9 bích hoặc j tép hoặc J bích ở 2 vòng đầu, mà mình cầm đôi 10 đỏ, thì mình đánh 10 rô 10 cơ họ khó ăn dc (ngược lại cũng vậy)
-	Nếu cây què mình định đánh mà thấy chắc chắn gửi được vào phỏm của nhà khác thì giữ lại, trừ khi là chốt cây gửi đó đánh chốt 100% ko bị ăn
-	Khi hạ cuối cùng thì cây to què nhất bài đánh.
-	Khi đánh chốt nếu các cây què ko có cây nào chắc 100 mà có phỏm 4 cây trở lên và có cây đầu cuối chốt chắc thì có thể cắt bớt 1 lá để chốt cho chắc
-	Khi đã bị ăn 2 cây thì các cây sau cây nào cũng phải chọn cây chắc nhất có thể để tránh bị ù đền

