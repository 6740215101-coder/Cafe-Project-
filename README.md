name: Cafe Project CI/CD Workflow

# กำหนดให้ทำงานเมื่อมีการ Push หรือทำ Pull Request เข้ามาที่ branch main
on:
  push:
    branches: [ "main" ]
  pull_request:
    branches: [ "main" ]

jobs:
  build-and-test:
    runs-on: ubuntu-latest

    steps:
    # 1. ดึงโค้ดจาก Repository มาที่ runner
    - name: Checkout Code
      uses: actions/checkout@v4

    # 2. ติดตั้ง Node.js
    - name: Setup Node.js
      uses: actions/setup-node@v4
      with:
        node-version: '18'

    # 3. ติดตั้ง Dependencies
    - name: Install Dependencies
      run: npm install

    # 4. ทดสอบรัน หรือ Build โปรเจกต์
    - name: Run Build Test
      run: npm run build --if-present
Main Features
รายชื่อสมาชิก
นางสาวกิ่งกมล สุขสบาย 6740215101
นายเปรมชัย  คุณเจริญ 6740215120
