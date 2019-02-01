
[![](https://user-images.githubusercontent.com/11352152/30252159-1bbb9cfe-963b-11e7-966c-b44116c74a86.png)](https://chmln.github.io/vue-wysiwyg/)

## 사용방법


### vue-wysiwyg 설치

``` bash
npm install vue-wysiwyg --save
```
OR

``` bash
yarn add vue-wysiwyg
```

js파일을 생성하여 다음과 같이 입력한다.
예시)'vue-wysiwyg.js'파일

```js
import Vue from 'vue';
import wysiwyg from "vue-wysiwyg";
import "vue-wysiwyg/dist/vueWysiwyg.css";

Vue.use(wysiwyg, {});
```

에디터를 사용할 Vue 파일에 다음과 같이 적용한다.

```html
<wysiwyg v-model="myHTML" />
```

## 옵션 설정

다음 키들은 모두 선택사항이다.

```js
{
  // { [모듈명] : boolean (true 시, 숨김) }
  hideModules: { "bold": true },

  // icon 그림은 재정의할 수 있다. (재정의한 icon은 커스텀 스타일이 필요할 수 있다.)
  iconOverrides: { "bold": "<i class='your-custom-icon'></i>" },

  // 이미지 옵션이 설정되어있지 않다면, 이미지들은 기본적으로 base64형식으로 삽입된다.
  image: {
    uploadURL: "/api/myEndpoint",
    dropzoneOptions: {}
  },

  // 에디터 높이를 정의한다. 정의하지 않는다면, 사이즈는 자동으로 설정될 것이다.
  maxHeight: "500px",

  // true로 설정하면 특정 텍스트를 불러올 때, 서식이 적용되지 않은 상태로 삽입된다.
  forcePlainTextOnPaste: true
}
```
모듈(서식) 목록:
 - bold
 - italic
 - underline
 - justifyLeft
 - justifyCenter
 - justifyRight
 - headings
 - link
 - code
 - orderedList
 - unorderedList
 - image
 - table
 - removeFormat
 - separator

Note on the image upload API endpoint:
- Image is uploaded by `multipart/form-data`
- Your endpoint must respond back with a string, the URL for the image - e.g. `http://myapp.com/images/12345.jpg`
