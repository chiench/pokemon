1. Tạo card ( Thẻ bài ) component 
  Mỗi card gồm hai mặt (back - front)
  -> css body để card body đc
  font: odibee sans thêm ở public/index.html
2. Tạo các variable css ở file gobla css
usage: --variable: #f132323,
use : color: var(--variable);
3. Bản chất là cùng trên 1 card nhưng use rotate sẽ giúp quay lại giữa các mặt
  Card sẽ phải giữ nguyên lên width và height sẽ 100%, position: relative, không khi
  quay sẽ tràn ra.
4. Add 1 class phu để thêm khi quay ex is-flipped
 -> miss backface-visibility: hidden thể hiện việc mặt sau đang ẩn 
   sau đó bind class để xuất hiệm class đã style theo việc lật mặt trái lại 