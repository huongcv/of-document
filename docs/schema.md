# Welcome to Orenda form dynamic
### Html
```html
<of [schemaModel]='coSoSchema'></of>
```
```typescript
coSoSchema = new OfSchemaModel<PagedRequestCoSoDto>({
    fieldObject: {
      filter: this.fw.base.text({
        label: 'Từ khóa tìm kiếm',
        placeholder: 'Nhập tên/ mã cơ sở tiêm chủng cần tìm kiếm',
        grid: this.fw.getGridByWidth(8),
        allowEnterKeySearch: true
      }),
      khuVucId: {
        ...this.fw.sessionControl.khuVucDiaChi(),
        grid: this.fw.getGridByWidth(4)
      },
      tinhId: {
        ...this.fw.sessionControl.tinhTheoKhuVucSearch('khuVucId'),
        grid: this.fw.getGridByWidth(4)
      },
      huyenId: {
        ...this.fw.sessionControl.huyen('tinhId'),
        grid: this.fw.getGridByWidth(4)
      },
      xaId: {
        ...this.fw.sessionControl.xa('huyenId'),
        grid: this.fw.getGridByWidth(4)
      },
      cap: {
        ...this.fw.sessionControl.capCoSoMulti(),
        grid: this.fw.getGridByWidth(4)
      },
      phanLoai: {
        ...this.fw.selectControl.phanLoaiCoSoTiemChungMulti,
        grid: this.fw.getGridByWidth(4)
      },
      coSoChaId: {
        ...this.fw.sessionControl.coSoTiemChungTrucThuoc(),
        label: 'Đơn vị cha',
        grid: this.fw.getGridByWidth(8)
      },
      searchBtn: this.fw.base.templateRef({
        label: ' ',
        grid: this.fw.getGridByWidth(8)
      })
    }
  })
``` 
### Mô tả class OfSchemaModel 

|Property||Default Value|Description|
|-|-|-|-|
|`value()`||The unique ID of the form control. Usually this is the name of the field in the form value prefixed by the ID of the containing group or array, e.g. `MY_FORM.someTextInput`.|

