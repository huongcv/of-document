OfSchemaModel
=====
 .. Cú pháp

 Html
  .. code-block:: html
    <of [schemaModel]='coSoSchema'></of>
TS
 .. code-block:: ts
    coSoSchema = new OfSchemaModel<CoSoDto>({
      fieldObject: {
        phanLoai: {
          ...this.fw.selectControl.phanLoaiCoSoTiemChung,
          required: true,
          grid: this.fw.getGridByWidth(4)
        },
        cap: {
          ...this.fw.sessionControl.capCoSo(),
          required: true,
          grid: this.fw.getGridByWidth(4)
        },
        maKcb: {
          ...this.fw.base.text({
            label: 'Mã cơ sở',
            placeholder: 'Mã cơ sở y tế',
            maxLength: 100,
            grid: this.fw.getGridByWidth(4)
          })
        },
        ten: {
          ...this.fw.base.text({
            label: 'Tên cơ sở',
            placeholder: 'Nhập tên cơ sở',
            maxLength: 200,
            required: true,
            grid: this.fw.getGridByWidth(12)
          })
        },

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
        soNha: {
          ...this.fw.base.text({
            label: 'Địa chỉ chi tiết',
            placeholder: 'Nhập số nhà, ngõ, xóm phố',
            maxLength: 300,
            grid: this.fw.getGridByWidth(8)
          })
        },
        coSoIdCha: {
          ...this.fw.sessionControl.coSoTiemChungTrucThuoc({
            extendOptions: {
              isCoSoChaInCreateOrUpdateCoSoForm: true
            }
          }),
          label: 'Cơ sở cha',
          grid: this.fw.getGridByWidth(16),
          required: true
        },
        dienThoai: {
          ...this.fw.base.text({
            label: 'Điện thoại',
            placeholder: 'Nhập Điện thoại (nếu có)',
            maxLength: 300,
            grid: this.fw.getGridByWidth(8)
          })
        }
      }
    });

