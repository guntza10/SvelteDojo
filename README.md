# `SvelteDojo`

- เป็น framework ที่เอาไว้ทำ front-end

- เป็น SPA(Single Page Application) เหมือน ReactJs

- Compiler ที่ generate javascript code ที่เล็กและมีประสิทธิภาพสูง

## `ข้อแตกต่าง Svelt กับ ReactJs`

- ReactJs จะใช้ virtual Dom(`Document Object Model`) ที่ represent ui และเก็บไว้ที่ memory และ sync กับ Dom ซึ่ง ReactJs จะทำการ Update ui ผ่าน virtual Dom แล้ว virtual Dom ก็จะทำการ sync กับ Dom อีกทีนึงเพื่อให้ Browser render ui ใหม่
- virtual Dom มันจะ update เฉพาะจุดที่มีการเปลี่ยนแปลง state เท่านั้น ทำให้ Browser ไม่ต้อง render ใหม่ทั้งหมด render เฉพาะส่วนที่เปลี่ยนแปลงจริงๆ
- Svelt ไม่มี virtual Dom
- Vitrual DOM ถือว่าเป็นเทคโนโลยีที่มีความเร็วสูงมาก แต่ปัจจุบันเว็บไซต์มีการพัฒนาที่มากขึ้นทำให้เกิดผลกระทบของ DOM ที่ซ้ำกันใน memory ซึ่งจะส่งผลให้ประสิทธิภาพการทำงานแย่ลง

`Note:` โดยปกติ Browser โหลดหน้าเว็บเสร็จ จะสร้าง Dom ขึ้นมาจาก Html แล้วถ้าเราต้องการจะเปลี่ยนแปลงอะไรบนหน้าเว็บเราก็ใช้ javascript access Dom ตัวนี้ แล้วทำการเปลี่ยนแปลง ซึ่งมันจะทำการ render ทั้งหน้าใหม่เมื่อมีการเปลี่ยนแปลง Dom

## `SSR(Server-Side Rendering) vs CSR(Client-Side Rendering)`

1. SSR(Server-Side Rendering) => เป็นความสามารถของเว็บไซต์ที่สามารถ render หน้าเว็บบน server แทนที่จะ render บน browser ทำให้ข้อมูลมันถูก render เสร็จเรียบร้อยแล้วที่ server ก่อนที่จะส่งมาที่ client ทำให้ client สามารถนำไปแสดงผลได้เลย ซี่งส่งผลให้การโหลดหน้าเว็บมันเร็ว
2. CSR (Client-Side Rendering) => client จะ render หน้าเว็บทั้งหมดไว้ โดยที่ client request ไป server และ server จะส่งโครงของเว็บไซต์มาพร้อมกับไฟล์ js จากนั้นไฟล์ js จะทำการ render หน้าเว็บทั้งหมดให้สมบูรณ์ ทำให้การโหลดหน้าเว็บในครั้งแรกจะช้ากว่าแบบ SSR แต่จะมีการเปลี่ยนหน้าเว็บที่เร็วกว่า เพราะทุกหน้าได้ถูก render ไว้แล้วตั้งแต่ครั้บแรกที่ได้ไฟล์ js มา

### Why SSR?

- ต้องการทำ SEO เพราะ SSR ทำให้ search engine มันมองเห็นข้อความในหน้าเว็บไซต์ได้
- ต้องการให้ผู้ใช้ได้รับ UX ที่ดีในการโหลดหน้าเว็บไซต์ที่ไว
- เว็บไซต์ที่สร้างไม่ต้องการการตอบสนองมาก เพราะการตอบสนองแต่ละครั้งจะทำให้ server ต้องทำงาน และอาจส่งผลให้ server ล่มได้หากได้รับ request จากฝั่ง client มากเกินไป

### Why CSR?

- ไม่ได้ต้องการทำ SEO
- เว็บไซต์มีการตอบสนองกับผู้ใช้บ่อย
- ต้องการประหยัด server

`Note: ` SEO(Search Engine Optimize) มันคือการทำให้เว็บมีประสิทธิภาพ และรองรับการติดอันดับบน Google

## `Why use Svelte?`

- No virtual Dom
- สร้าง dynamic front-end ui
- สร้าง js ที่มีประสิทธิภาพสูง
- เร็วกว่า framework อื่น 30%
- เป็น ssr ด้วย
- ใช้งานง่าย

## `Reason Why Svelte different?`

1. Flexible and write less code
2. No virtual DOM
3. CSS scope
   - โครงสร้างไฟล์คล้าย VueJs

## `Ref`

- https://svelte.dev/blog/the-easiest-way-to-get-started
