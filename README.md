# The Internship Season 3 : Developer Exam
# [ตอนที่ 1]
ให้ผู้สมัครเขียนโปรแกรมต่อไปนี้โดยใช้ภาษาโปรแกรมอะไรก็ได้ (สามารถทำได้มากกว่า 1 ภาษา แต่ไม่
เกิน 3 ภาษา/ข้อ)

## โปรแกรมที่ 1
เขียนโปรแกรมที่รับจำนวนเต็มจาก Command Line Argument 1 ตัว และแสดงจำนวนเฉพาะทั้งหมด
ที่เป็นตัวประกอบของจำนวนนั้นทาง Standard Output โดยแต่ละตัวให้แสดงเพียงแค่ 1 ครั้ง เว้นด้วย ช่องว่าง และเรียงลำดับจากน้อยไปมาก

ตัวอย่างการรันโปรแกรม

```
> prime_factors 20
2 5
```

```
> prime_factors 186
2 3 31
```

## โปรแกรมที่ 2
เขียนโปรแกรมเพื่ออ่าน Text File ตามชื่อไฟล์ที่รับจาก Command Line Argument โดยไฟล์นี้จะบรรจุข้อความอยู่หลายข้อความ (บรรทัดละ 1 ข้อความ) และให้แสดงจำนวนของข้อความที่เป็น Palindrome ในไฟล์ซึ่งจะพิจารณาเฉพาะตัวอักษรภาษาอังกฤษเท่านั้น ไม่พิจารณาช่องว่าง สัญลักษณ์ ตัวเลข อักขระพิเศษ

ตัวอย่าง File: palin_input.txt

```
Sore was I ere I saw Eros.
A man, a plan, a canal -- Panama!
This one is NOT a palindrome!
Never a foot too far, even.
Euston saw I was not Sue.
```

ตัวอย่างการรันโปรแกรม

```
> count_palindrome palin_input.txt
4
```

---

# [ตอนที่ 2]
ให้ผู้สมัคร **“ปรับปรุงคุณภาพของโค้ด”** โปรแกรมเก่า ซึ่งโปรแกรมเมอร์ในอดีตของบริษัทหนึ่งเขียนด้วยภาษา C (C99) ต่อไปนี้โดย ให้ **“ปรับปรุงให้ดีที่สุดเท่าที่จะทำได้”** โดยผู้สมัครสามารถเขียนใหม่เป็นภาษาที่ผู้สมัครถนัดก็ได้ (โดยผู้สมัครจะต้อง **“เดา”** วัตถุประสงค์รวมถึงขอบเขตต่างๆ ของโปรแกรมนี้เอง ... เนื่องจากโปรแกรมเมอร์ที่เขียนโปรแกรมนี้ได้ลาออกไปแล้ว) ทั้งนี้ผู้สมัครสามารถถือได้ว่า **“โปรแกรมเหล่านี้ทดสอบแล้วว่าไม่มีข้อผิดพลาด (Bug) และสามารถทำงานได้ตามวัตถุประสงค์/ขอบเขตการทำงานอยู่แล้ว”** (ปรับปรุงคุณภาพโค้ดอย่างเดียว ไม่ต้องหาหรือแก้ข้อผิดพลาด)

## โปรแกรมที่ 1
```c
#include <stdio.h>
#include <string.h>
#include <ctype.h>
int main(int argc, char* argv[])
{
  int result = 0;
  int len = strlen(argv[1]);
  for(int i=0; i<len; ++i) {
    char c = tolower(argv[1][i]);
    if(c == 'a' || c == 'e' || c == 'i' || c == 'o' || c == 'u') {
      ++result;
    }
  }
  printf("%d\n", result);
  return 0;
}
```

## โปรแกรมที่ 2
```c
#include <stdio.h>
#include <stdlib.h>
#include <stdbool.h>
int x[8]; /* x[i] = x coordinate of queen in row i. */
/* prints field */
void print ()
{
  int i,j;
  printf ("+-----------------------+\n");
  for (i=0; i<8; i++) {
    printf ("|");
    for (j=0; j<8; j++)
      if (j==x[i]) printf ("Q.|");
      else printf (" |");
    printf ("\n");
    printf ("+-----------------------+\n");
  }
  printf ("\n");
}
/* tests, whether (ix, iy) is beaten by queens 0...(iy-1) */
bool is_free (int ix, int iy)
{
  int i;
  for (i=0; i<iy; i++)
    if ((x[i]==ix) || (abs(x[i]-ix)==abs(i-iy)))
      return false;
  return true;
}
/* tries to place queen n on row n */
void placequeen (int n)
{
  int i;
  if (n==8)
    print();
  else
    for (i=0; i<8; i++)
      if (is_free(i,n)) {
        x[n]=i;
        placequeen (n+1);
      }
}
int main ()
{
  placequeen (0);
  return 0;
}
```

---

# [ตอนที่ 3]
ให้ผู้สมัคร “เลือก” โค้ดโปรแกรม ที่ผู้สมัครเคยเขียน มา 1 ไฟล์โดยให้เป็นโค้ดที่ผู้สมัครเขียนเองทั้งหมดไม่มีส่วนที่คัดลอกจากหนังสือ  เว็บไซต์เอกสารประกอบการสอน ฯลฯ ใดๆ ทั้งสิ้น ไม่จำเป็นว่าต้องเป็นไฟล์ที่ใหญ่หรือโปรแกรมที่ยาก

---

# การส่งคำตอบ
1. ให้ผู้สมัครแยกคำตอบทั้ง 3 ตอน ลงใน 3 Folders (Directory) โดยตั้งชื่อ Folder 1, 2 และ 3 ตามลำดับ
2. ชื่อไฟล์ในแต่ละตอนให้ตั้งตามความเหมาะสม เช่น program1.c, program1.js, PrimeFactor.java, prime_factors.rb, prime_factors.py เป็นต้น
3. เตรียมไฟล์ชื่อ Readme.txt ที่ระบุชื่อ เบอร์โทรศัพท์ e-mail ไว้ในไฟล์โดยเตรียมไฟล์นี้ไว้นอก Folder ทั้ง 3
4. ZIP ทั้งโฟลเดอร์กับไฟล์ Readme.txt โดยตั้งชื่อ Internship2017.zip (ย้ำ: ZIP เท่านั้น ห้าม RAR)
5. Submit ในระบบ หรือส่งไฟล์ตามที่ระบุในเว็บไซต์

ตัวอย่าง Folder Structure ที่มี Readme.txt ด้วย

![Folder Structure](https://rawgit.com/theinternship-io/dev-2017/master/folder-structure.png)
