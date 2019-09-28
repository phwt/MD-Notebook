# Computer Programming

## ตัวแปร

    type variable_name = value;
  
### Type
ประเภทตัวแปร

- `char`
- `int`
- `float`
- `double`

### Declaration
ประกาศตัวแปร

    type variable_name;
    
    int num1, num2;
    char txt1, txt2;

ประกาศตัวแปรให้รู้จักเฉยๆ ยังไม่มีการใส่ค่า

### Initialization
ประกาศตัวแปรพร้อมค่า

    type variable_name = value;
    
    int num = 0;
    char txt1 = 'a', txt2 = 'b';

### Assignment
เปลี่ยนค่าตัวแปร

    variable_name = value;
    
    num = 112;
    char k = 'o';

ต้องมีการ Declaration หรือ Initialization ก่อนไม่งั้นจะเปลี่นนค่าไม่ได้

## การรับค่า

    scanf(format, variable);

    scanf("%s", txt);

- `%s`: string
- `%c`: char
- `%d`: integer
- `%f`: float
- `%lf`: long float (double)

หมายเหตุ - ทุกตัวยกเว้น string (`%s`) ต้องมี `&` นำหน้าตัวแปรเสมอ เช่น `scanf("%d", &num);`

### การรับลงหลายตัวแปร

    scanf("%s %d %f", txt, &numi, &numf);
    
### การรับ String ที่มีช่องว่าง

    scanf("%[^\n]s", txt);
    
String จะไม่ถูกตัดเมื่อเจอช่องว่าง(space) แต่จะถูกตัดเมื่อเจอขึ้นบรรทัดใหม่(`\n`)เท่านั้น

## การส่งออกค่า

    printf(formatting, var);
    
**Formatting**
- `%s`: string
- `%c`: char
- `%d`: integer
- `%f`: float
- `%lf`: long float (double)

## Operators

- `+` `-` `*` `/`: บวก, ลบ, คูณ, หาร
- `%`: หาเศษ `12%5 = 2`
- `++` `--`: เพิ่ม/ลดค่าที่ละ 1 `a++;` = `a = a + 1;`
-------
- `==` `!=`: ตรวจเท่ากัน/ไม่เท่ากัน
- `<` `>`: มากกว่า/น้อยกว่า
- `<=` `>=`: มากกว่าเท่ากัน/น้อยกว่าเท่ากับ
-------
- `&&`: AND (1 ทั้งสอง = True)
- `||`: OR (1 ตัวใดตัวหนึ่ง = True)
- `!`: NOT (`!true = false` `!false = true`)

ตรวจสอบว่าตัวเลขอยู่ในช่วง
    
    x >= 80 && x <= 100

ถ้า x มีค่าอยู่ระหว่าง 80 - 100 จะได้เป็น true

## Condition (if-else)

    if(condition){
        //condition true do this
    }else{
        //if not do this 
    }
    
    if(condition){
        //condition true do this
    }else if(condition2){
        //if not but condition2 do this 
    }else{
       /if not do this
    }
    
## Loop

### `while`

    while(ถ้าตรงนี้ true จะทำต่อเรื่อยๆ){
       //ทำทำ
    }
    
### `for`

    for(เริ่ม; จบ; เพิ่มทีละเท่าไร){
        //ทำทำ
    }

    for(int i=0; i<10; i++){
        //จะลูป 10 รอบโดยที่ i เป็น 0-9 โดยเพิ่มที่ละ 1
    }
    
### `break` `continue`

- `break` - จบลูปนั้นันที
- `continue` - ข้ามลูปรอบนั้นไป (ลูปจะลูปต่อ แต่จะไม่ทำรอบนั้นต่อ)

## Array

    type var_name[size] = value; (ค่าใน Array มีได้ประเภทเดียวเท่านั้น)
    
    int num[] = {4, 4, 1, 1, 2};

- `int num[] = {1, 2, 3, 4, 5};`: สร้าง Array ประเภท `int` จำนวน x ตัว (ตัวตามค่าที่ตั้งไว้)
- `int num[10] = {0};`: สร้าง Array ประเภท `int` จำนวน 10 ตัว แล้วให้ทุกตัวมีค่าเป็น 0

เลือกค่าและเซ็ตค่าใน Array

    int num[] = {1, 2, 3, 4, 5};
    //num[2] จะได้ค่า 3
    num[2] = 7;
    //num[2] จะได้ค่า 7;
    //num[] จะกลายเป็น {1, 2, 7, 4, 5}

## Function

    return_type functionName(type parameters){
       //ทำทำ
    }
   
    int returnFive(){
        //ฟังก์ชั่นไม่รับตัวแปรและคืนค่าเป็น int เลข 5
        return 5;
    }
   
    void returnNothing(int num){
        //ฟังก์ชั่นรับตัวแปรชื่อ num ที่เป็น int และไม่คืนค่า (void)
        printf("Entered: %d", num);
    }
   
    int plusMe(int num1, int num2){
        //ฟังก็ชั่นรับ int num1, num2 คืนค่าเป็น int ที่ num1 + num2
        return num1 + num2;
    }
   
    int numfromfunc = returnFive();
    //จะได้ค่า 5 จากที่ return มา
   
    returnNothing(9);
    //"Entered: 9" จะถูกปริ้นออกมา
  
    int numplus = plusMe(3, 6);
    //จะได้ค่า 9

## Library
ไลบราลี

    #include <library.ext>

- `stdio.h`: Standard I/O คำสั่งพวก `scanf`, `printf`
- `string.h`: จัดการ string
- `ctype.h`: จัดการ/ตรวจสอบ char
- `math.h`: การคิดคณิตศาสตร์ต่างๆ

### `string.h`

`dest` - ตัวแปรปลายทาง, `char` - string char ที่ต้องการนำมาใช้

- `strcpy(dest, char)`: Assign ค่าให้ตัวแปร (C ทำแบบ `ชื่อตัวแปร = "abcd"` ไม่ได้)
- `strcat(dest, char)`: ต่อค่า(concatenate)เข้ากับตัวแปร
- `strlen(var)`: ความยาว string (ค่าที่ได้ -1 เสมอ เพราะจะนับ `\0` มาด้วย)

### `ctype.h`

- `isalpha(char)`: ตรวจว่าเป็นตัวหนังสือรึเปล่า (boolean)
- `isdigit(char)`: ตรวจว่าเป็นตัวเลขรึเปล่า (boolean)
- `islower(char)`: ตรวจว่าเป็นพิมพ์เล็กรึเปล่า (boolean)
- `isupper(char)`: ตรวจว่าเป็นใหญ่เล็กรึเปล่า (boolean)
-------
- `tolower(char)`: แปลงเป็นตัวพิมพ์เล็ก
- `toupper(char)`: แปลงเป็นตัวพิมพ์ใหญ่

### `math.h`

- `pow(var, power)`: ยกกำลัง `pow(2, 3)` = `2^3`
- `sqrt(var)`: รากที่สอง
- `floor(var)`: ตัดทศนิยมทิ้ง

หมายเหตุ - ตอน Compile ต้องมี `-lm` ต่อท้ายด้วย

## Compile/Run
ในห้องสอบทำใน Ubuntu เปิดใน Terminal ให้เหมือนบน PC ทุกอย่าง

    gcc file.c [-o file] (Compile)
   
    ./file.exe (Run)
    
## การใช้งานที่ควรรู้

### รับค่าเรื่อยๆจนกว่าจะเจอค่าที่กำหนด
    
    int num;
    while(1){ //1 = true
        scanf("%d", &num);
        if(num == 10){break;} //ถ้าใส่ 10 เข่ามาลูปจะหยุด
    }
    
### รับค่าเข้า Array

    int num[10];
    for(int i=0; i<10; i++){ //ลูป 10 ครั้ง i เป็น 0-9
        scanf("%d", num[i]); //ยัดค่าที่รับเข้า num ที่ตำแหน่ง i
    }
