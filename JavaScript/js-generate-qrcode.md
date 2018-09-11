---
title: js generate qrcode
date: 2018-09-05 08:46:57
tags:
- JavaScript
- qrcode
categories:
- JavaScript
---

### 0x01 qrcodejs

<https://github.com/davidshimjs/qrcodejs>

```bash
yarn add qrcodejs2 
import QRCode from 'qrcodejs2'
```

### 0x02 node-qrcode(recommend)

<https://github.com/soldair/node-qrcode>

```bash
# 安装 qrcode
yarn add qrcode
```

`.vue`

```vue
<template>
  <div>
	<canvas id="canvas" @click="downloadImg()"></canvas>
  </div>
</template>

<script>
import QRCode from "qrcode";
export default {
  data() {
    return {
        Url: ''
    };
  },
  created() {},
  mounted() {
      this.setQRCode(this.Url);
  },
  methods: {
    setQRCode(Url) {
      // 生成二维码
      let canvas = document.getElementById("canvas");
      QRCode.toCanvas(
        canvas,
        Url,
        { errorCorrectionLevel: "H", width: 350 },
        error => {
          if (error) {
            this.$message({
              message: `生成二维码失败${error}`,
              type: "warning"
            });
          }
        }
      );
    },
    downloadImg() {
      // 下载二维码
      let canvasData = document.getElementById("canvas");
      let a = document.createElement("a");
      a.href = canvasData.toDataURL();
      a.download = `${this.enterpriseName}二维码`;
      a.click();
    }
  }
};
</script>

<style scoped>
</style>
```



<!--more-->