# bnc-canvas

## 安装

> composer require blue-nest-cloud/bnc-canvas

## 配置

> 配置字体文件位于 `public/system/font/Alibaba-PuHuiTi-Regular.otf`

### 使用方式

> 为了适应框架 放置canvas 生成 目录 需要自己创建

### 例子
```
clss Index{
    
    public function index($data){
       $canvas = \bnc\canvas\Canvas::instance();
        $path = __DIR__;
        $imageType = 'jpg';
        $name = 'follow';
        $imageUrl = $path . $name . '.' . $imageType;
        $canvas->setImageUrl('https://car3.autoimg.cn/cardfs/selected/520/g24/M06/26/59/520x390_0_q95_autohomecar__ChwFjmB2xPuAKUbhAARK65kPon0502.jpg')->setImageHeight(720)->setImageWidth(500)->pushImageValue();
        $canvas->setImageUrl('https://img.cnmo.com/1843/1842270.jpg')->setImageHeight(344)->setImageWidth(344)->setImageLeft(76)->setImageTop(76)->pushImageValue();
        $canvas->setFontPath('https://info.chinahc.wang/Alibaba-PuHuiTi-Regular.otf')->setFontText('本次二维码认证有效过期时间为:')->setFontSize(12)->setFontTop(45)->setFontLeft(40)->setFontColor('255,255,255')->pushFontValue();
        $image = $canvas->setFileName($name)->setImageType($imageType)->setPath($path)->setBackgroundWidth(500)->setBackgroundHeight(720)->starDrawChart();
    }
 
}
