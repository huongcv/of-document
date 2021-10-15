Text Input
=====

Cú pháp:
 .. code-block:: ts
  this.fw.base.text({
            label: 'Mã cơ sở',
            placeholder: 'Mã cơ sở y tế',
            maxLength: 100,
            grid: this.fw.getGridByWidth(4)
          })
Giải thích: 
   label: Tên label, 
   placeholder,
   maxLength: Độ dài tối đa input
   grid: Cấu hình độ rộng theo grid của antd (24)


