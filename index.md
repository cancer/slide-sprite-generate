
## CSS Spriteを動的に生成する

2014/08/18 LT大会

---

## YogaのSprite生成の流れ
- Image Assets Generator(Photoshop)
- フォルダに配置
- Spriteファイル生成/最適化

---

## Image Assets Generator(Photoshop)

- [ファイル] → [生成]にチェックを入れておく
- レイヤーにファイル名をつけておく
- レイヤーが更新されると指定した名前で自動的に書き出し
- ※ Photoshop CC以降

---

## フォルダに配置

- 職人が丹精込めて一つ一つ移動

---

## Spriteファイル生成/最適化

- Grunt and Compass
- CSSの生成と一緒にSpriteファイルも生成してくれる
 - grunt-imageminでSpriteファイルを最適化

---

## CSS Sprite Helpers for Compass

http://compass-style.org/reference/compass/helpers/sprites/

---

## CSS Sprite Helpers(略)について

- CompassビルトインのSprite generator
- 導入が楽
 - Compassが用意しているfunctionを使えばすぐ
 - Sass(SCSS)ファイルに書いていくだけ
- マッピング情報はRuby側で管理
 - function経由で取得
 - 要キャッシュ

---

## CSS Sprite Helpers(略)について

- CSSの生成が遅くなる...(画像の変更が無くても+数秒)
 - Sass(SCSS)に変更があるたびに画像の差分をチェック
- 生成されたSpriteファイルをwatchできない...
 - Compassタスクの実行中に画像が生成されるため  
grunt-imageminのwatchに検知されない

---

## grunt-spritesmith

https://github.com/Ensighten/grunt-spritesmith

---

## grunt-spritesmithについて

- spritesmithのGrunt plugin
- Sassに非依存
 - LESSでもStylusでも使える
- CSSの生成とCSS Spriteの生成を分離できる
 - CompassはCSSの生成に集中
 - Spriteファイルのwatchも可能に
- マッピング情報はSass(SCSS)の変数化される
 - 変数にアクセスするfunctionも一緒に書きだされる

---

## grunt-spritesmithについて

- フォルダが分けられない...
- CompassのI/Fと差異があるので、途中からの移行がつらい...
- カスタムタスクを書いて解決

---

## その他のSprite generator

- css-sprite - https://github.com/aslansky/css-sprite
 - そのままでgruntでもgulpでもnodeでもsassでも使えるっぽい？
 - 新しい(ReleaseNoteは今年の2月から)

- glue - https://github.com/jorgebastida/glue
 - python製
 - ガールフレンドはこれ  
 http://ameblo.jp/ca-1pixel/entry-11862882925.html
 - gruntプラグインはなぜかbitbucket

- and more...
 - https://www.npmjs.org/search?q=sprite

---

## 今後やりたいこと
- Image Assets Generatorとgruntの連携

