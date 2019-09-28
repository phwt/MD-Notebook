# Multimedia Technology

## Selector
ใช้อ้างถึง Element ต่างๆในหน้า

- `*`: เลือกทุกตัว
- `.class`: Class
- `#id`: ID
- `tag`: Tag
----------
- `.a, .b`: เลือกตัวที่มี `.a` หรือ `.b` อย่างน้อย 1 ตัว
- `.a.b`: เลือก Element ที่มี `.a` และ `.b` อยู่ร่วมกัน
- `.a > .b`: เลือก `.b` ที่เป็นลูก(child)ของ `.a`
----------
- `a[attr]`: เลือก `a` ที่มี Attribute `attr` อยู่
- `a[attr='x']`: เลือก `a` ที่ Attribute `attr` มีค่าเป็น `x`
- `a[attr^='x']`: เลือก `a` ที่ Attribute `attr` ขี้นต้นเป็น `x`
- `a[attr$='x']`: เลือก `a` ที่ Attribute `attr` ลงท้ายเป็น `x`
----------
- `p:first-child`: เลือก `p` ตัวแรก
- `p:last-child`: เลือก `p` ตัวสุดท้าย
- `p:nth-child(2)`: เลือก `p` ตัวที่สอง
- `p:nth-child(odd)`: เลือก `p` ทุกตัวที่ลำดับเป็นคี่ (คู่ใช่ `even`)
- `p:nth-child(2n)`: เลือก `p` ทุกตัวที่ลำดับหารสองลงตัว (เลือกทุกๆสองตัว)
----------
- `a:hover`: เลือก `a` ขนะเมาส์ชี้อยู่
- `a:active`: เลือก `a` ขนะเมาส์คลิกอยู่

[ตัวอย่างผลลัพธ์](https://www.w3schools.com/csSref/trysel.asp)

## HTML

### Tag/การตั้งค่า/ใช้งานต่างๆที่ควรรู้

#### เชื่อมไฟล์ CSS, JavaScript
```html
<link rel="stylesheet" type="text/css" href="ไฟล์.css">
<script src="ไฟล์.js"></script>
```

#### ตั้ง Character Encoding ให้อยู่ในระบบ `UTF-8`
ใช้ในกรณีที่หน้ามีภาษาไทยแล้วแสดงผลไม่ได้
```html
<meta charset="UTF-8">
```

#### ตั้งให้หน้าเว็บย่อ/ขยายตามขนาดหน้าจอ (Responsive)
```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

#### Event

- `onclick`: ตอนที่ถูกคลิก
- `onmouseover`: ตอนที่นำเคอร์เซอร์ไปวาง
- `onkeydown`: ตอนที่กดปุ่มบนแป้นพิมพ์ใดๆ

```html
<button onclick="alert('Clicked');">Click me!</button> //จะมี Alert ขึ้นมาตอนกดปุ่ม
<a onclick="alert('Hovered');">Hover me!</a> //จะมี Alert ขึ้นมาตอนเคอร์เซอร์อยู่เหนือตัวหนังสือ
<textarea onkeydown="alert('Pressed');"></textarea> //จะมี Alert ขึ้นมาตอนมีการกดปุ่มบนแป้นพิมพ์ใดๆใน textarea นี้
```

## CSS

```css
selector{
  property: value;
}
```

#### การทำให้วัตถุอยู่ตรงกลางทั้งแนวตั้งและแนวนอน

```css
element{
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
```

## JavaScript

### เลือก Element บนหน้า
```javascript
document.querySelector('ใส่ Selector เหมือนหัวข้อบน');
```

### ดึงค่า/เปลี่ยนค่าบนหน้าเว็บ

- `innerText`: เฉพาะตัวหนังสือ
- `innerHTML`: แทกต่างๆด้วย

#### ดึงค่า

```html
<div id="example">
  <b>Hello World</b>
</div>
```

```javascript
document.querySelector('#example').innerText; //จะได้ค่าเป็น Hello World
document.querySelector('#example').innerHTML; //จะได้ค่าเป็น <b>Hello World</b>
```

#### เปลี่ยนค่า

```html
<div id="example">
  <b>Hello World</b>
</div>
```

```javascript
document.querySelector('#example').innerText = 'Hello Earth'; //จะได้ค่าเป็น Hello Earth ตัวหนาเหมือนเดิม
document.querySelector('#example').innerHTML = 'Hello Earth'; //จะได้ค่าเป็น Hello Earth ที่ไม่เป็นตัวหนา
```

### ดึงค่า/เปลี่ยนค่า Attribute

- `getAttrbute()`: ดึงค่า
- `setAttrbute()`: เปลี่ยนค่า

```html
<div id="example" status="ok"></div>
```

```javascript
document.querySelector('#example').getAttribute('status'); //จะได้ค่าเป็น ok
document.querySelector('#example').setAttribute('status', 'nein'); //ค่าของ status ใน #example จะกลายเป็น nein (<div id="example" status="nein"></div>)
```

### แก้ CSS

- `.style.property = newstyle;`

```html
<div id="example">Planet Earth is blue, And there's nothing I can do</div>
```

```javascript
document.querySelector('#example').style.color = 'red'; //ตัวหนังสือใน div ก็จะเปลี่ยนเป็นสีแดง
```
### การใช้งานต่างๆที่ควรรู้

#### ทำคำสั่งเมื่อมีการกดปุ่มบนแป้นพิมพ์

เมื่อกด `space` (32) จะมี Alert ขึ้น

```javascript
document.onkeypress = function (e) {
    e = e || window.event;
    if(e.keycode == 32){
        alert('Space pressed!');
    }
};
```