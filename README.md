# Xin chào! 👋

Mình là Ứng Tiến Đạt, một **sinh viên IT** đam mê **lập trình web** 💻.  
Mình thích khám phá các công nghệ mới, xây dựng website và trải nghiệm các hiệu ứng thú vị trên web.

---

## 🎉 Hiệu ứng chữ động

Đây là đoạn code JavaScript mô phỏng hiệu ứng chữ nhấp nháy, hiện từng chữ:

```javascript
let texts = [
  "Chào mừng 20 - 10 - 2025",
  "Chúc bạn một ngày vui vẻ",
  "Bạn thật tuyệt vời",
  "Chúc luôn mạnh khỏe và hạnh phúc",
  "Luôn cười thật tươi nhé ^^",
];

let text = "";
let textElement = document.createElement("p");
textElement.style = "color: red; font-size: 22px;";
document.body.appendChild(textElement);

function randomText() {
  return texts[Math.floor(Math.random() * texts.length)];
}

function showPre() {
  text = randomText();
  textElement.innerHTML = "";
  let index = 0;

  let textTime = setInterval(() => {
    textElement.innerHTML += text[index];
    index++;
    if (index === text.length) {
      clearInterval(textTime);
      setTimeout(showBefore, 200);
    }
  }, 100);
}

function showBefore() {
  let index = text.length;

  let textReverse = setInterval(() => {
    textElement.innerHTML = text.slice(0, index);
    index--;
    if (index < 0) {
      clearInterval(textReverse);
      setTimeout(showPre, 200);
    }
  }, 100);
}

showPre();
