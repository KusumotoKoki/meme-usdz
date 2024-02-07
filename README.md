# MEME USDZ

猫ミームをAIで3D化しました！

デモ：https://meme-usdz.vercel.app/

iPhoneやVisionProのSafariでデモサイトを開くと、ARで猫ミームが飛び出します

## 作り方

### 1. DreamGaussian
[DreamGaussian](https://github.com/dreamgaussian/dreamgaussian)で猫ミーム画像を3D化

Colabのコードをそのまま動かすとtrainingのところでエラるので、以下を実行する
（cf. https://github.com/dreamgaussian/dreamgaussian/issues/10 ）
```
!sudo apt-get install cuda-cudart-11-7
```

`logs/`以下に`{NAME}.obj`, `{NAME}.mtl`などが生成されるので、それらを全てダウンロードする

`.glb`形式でも出力できるらしいが、エラーが出て動かなかった(2024/02/07)

### 2. Blender
[Blender](https://www.blender.org/)で`{NAME}.obj`をインポート

エクスポート形式として`.usd*`を選び、エクスポート名のところで拡張子を`.usdz`にする（デフォルトだと`.usdc`なので、`.usdz`に書き換える）

### 3. Webサイトに配置
HTMLに次を書けば大丈夫
（cf. https://developer.apple.com/jp/documentation/arkit/previewing_a_model_with_ar_quick_look/ ）
```
<div>
    <a rel="ar" href="/assets/models/my-model.usdz">
        <img src="/assets/models/my-model-thumbnail.jpg">
    </a>
</div>
```


## 猫ミームたち

<div>
<a rel="ar" href="/models/huhcat.usdz" class="centered-img">
    <img src="/models/huhcat_rgba.png" alt="huh cat">
</a>
</div>
<div>
<a rel="ar" href="/models/girlfriendcat.usdz" class="centered-img">
    <img src="/models/girlfriendcat_rgba.png" alt="girlfriend cat">
</a>
</div>
<div>
<a rel="ar" href="/models/okocat.usdz" class="centered-img">
    <img src="/models/okocat_rgba.png" alt="oko cat">
</a>
</div>
<div>
<a rel="ar" href="/models/okorarecat.usdz" class="centered-img">
    <img src="/models/okorarecat_rgba.png" alt="okorare cat">
</a>
</div>
<div>
<a rel="ar" href="/models/dubidabacat.usdz" class="centered-img">
    <img src="/models/dubidabacat_rgba.png" alt="dubidaba cat">
</a>
</div>

