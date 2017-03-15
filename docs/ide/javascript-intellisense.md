---
title: "JavaScript IntelliSense | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IntelliSense [JavaScript]
- <reference> JavaScript XML tag
- JavaScript Code Editor
- XML code comments, JavaScript IntelliSense
- reference JavaScript XML tag
- JavaScript, IntelliSense
- code comments, JavaScript IntelliSense
- JavaScript, reference groups
- JavaScript Editor
- reference directives [JavaScript]
- JavaScript, XML documentation comments
- reference groups [JavaScript]
- JavaScript, reference directives
- IntelliSense [JavaScript], about
- IntelliSense extensibility [JavaScript]
- XML documentation comments [JavaScript]
ms.assetid: af1a3171-c9d8-45a3-9c96-a763e3b163ef
caps.latest.revision: 63
author: mikejo
ms.author: mikejo
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: d07820eda0d76163d99d7752789750eaf56182fd
ms.openlocfilehash: 1f8372fe201d6b23ee2c65e0f6d6a2fa28976654
ms.lasthandoff: 02/22/2017

---
# <a name="javascript-intellisense"></a>JavaScript IntelliSense
[!include[vs_dev15](../misc/includes/vs_dev15_md.md)]에서는 즉시 사용 가능한 강력한 JavaScript 편집 환경을 제공합니다. TypeScript 기반 언어 서비스로 제공되는 Visual Studio는 더 다양한 IntelliSense, 최신 JavaScript 기능 지원 및 정의로 이동, 리팩터링 등의 향상된 생산성 기능을 제공합니다.

> [!NOTE]
>  [!include[vs_dev15](../misc/includes/vs_dev15_md.md)]의 JavaScript 언어 서비스에는 새로운 언어 서비스용 엔진("salsa")이 사용됩니다. 자세한 내용은 이 항목에 포함되어 있고 이 [블로그 게시물](https://blogs.msdn.microsoft.com/visualstudio/2016/04/08/previewing-salsa-javascript-language-service-visual-studio-15/)을 참조할 수 있습니다. 새 편집 환경은 일반적으로 VS 코드에서도 적용됩니다. 자세한 내용은 [VS 코드 문서](https://code.visualstudio.com/docs/languages/javascript)를 참조하세요.

[!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]의 일반 IntelliSense 기능에 대한 자세한 내용은 [IntelliSense 사용](../ide/using-intellisense.md)을 참조하세요. 

## <a name="whats-new-in-the-javascript-language-service-in-includevsdev15miscincludesvsdev15mdmd"></a>[!include[vs_dev15](../misc/includes/vs_dev15_md.md)] JavaScript 언어 서비스의 새로운 기능

- 더 다양한 IntelliSense

    [!include[vs_dev15](../misc/includes/vs_dev15_md.md)]의 JavaScript IntelliSense는 이제 매개 변수 및 멤버 목록에 대한 훨씬 더 많은 정보를 표시합니다.
이 새로운 정보는 코드를 더 잘 이해하도록 내부에서 정적 분석으로 사용하는 TypeScript 언어 서비스를 통해 제공됩니다.
TypeScript는 여러 소스를 사용하여 이 정보를 구성합니다.
    - [형식 유추 기반 IntelliSense](#TypeInference)
    - [JSDoc 기반 IntelliSense](#JsDoc)
    - [TypeScript 선언 파일 기반 IntelliSense](#TSDeclFiles)

- [형식 정의의 자동 획득](#Auto)
- [ES6 이상 지원](#ES6)
- [JSX 구문 지원](#JSX)

## <a name="TypeInference"></a>형식 유추 기반 IntelliSense
JavaScript에서는 일반적으로 명시적 형식 정보를 사용할 수 없습니다. 다행히도 주변 코드 컨텍스트가 있는 경우 일반적으로 형식을 쉽게 추론할 수 있습니다.
이 프로세스를 형식 유추라고 합니다.

일반적으로 변수 또는 속성의 형식은 초기화에 사용된 값 또는 가장 최근 값 할당의 형식입니다. 

```js
var nextItem = 10;
nextItem; // here we know nextItem is a number

nextItem = "box";
nextItem; // now we know nextItem is a string
```

함수의 반환 형식은 return 문에서 유추할 수 있습니다. 

함수 매개 변수의 경우 현재 유추가 없지만 JSDoc 또는 TypeScript `.d.ts` 파일을 사용하여 이 문제를 해결할 수 있습니다(이후 섹션 참조).

또한 다음에 대한 특수 유추가 있습니다.
 - "ES3-style" 클래스 - 프로토타입 속성에 대한 생성자 함수 및 할당을 사용하여 지정됩니다.
 - CommonJS-style 모듈 패턴 - `exports` 개체의 속성 할당 또는 `module.exports` 속성에 대한 할당으로 지정됩니다.

```js
function Foo(param1) {
    this.prop = param1;
}
Foo.prototype.getIt = function () { return this.prop; };
// Foo will appear as a class, and instances will have a 'prop' property and a 'getIt' method.

exports.Foo = Foo;
// This file will appear as an external module with a 'Foo' export.
// Note that assigning a value to "module.exports" is also supported.
```

## <a name="JsDoc"></a> JSDoc 기반 IntelliSense

형식 유추에서 원하는 형식 정보(또는 지원 문서 정보)가 제공되지 않으면 JSDoc 주석을 통해 명시적으로 형식 정보를 제공할 수 있습니다.  예를 들어 부분적으로 선언된 개체에 특정 형식을 제공하려면 다음과 같이 `@type` 태그를 사용할 수 있습니다.

```js
/**
 * @type {{a: boolean, b: boolean, c: number}}
 */
var x = {a: true};
x.b = false;
x. // <- "x" is shown as having properties a, b, and c of the types specified
```

설명한 것처럼 함수 매개 변수는 유추되지 않습니다. 그러나 JSDoc `@param` 태그를 사용하여 함수 매개 변수에 형식을 추가할 수도 있습니다. 

```js
/**
 * @param {string} param1 - The first argument to this function
 */
function Foo(param1) {
    this.prop = param1; // "param1" (and thus "this.prop") are now of type "string".
}
```
 
현재 지원되는 JsDoc 주석은 [이 문서](https://github.com/Microsoft/TypeScript/wiki/JsDoc-support-in-JavaScript)를 참조하세요.

## <a name="TsDeclFiles"></a> TypeScript 선언 파일 기반 IntelliSense

JavaScript 및 TypeScript는 이제 같은 언어 서비스에 기반을 두므로 더 다양한 방법으로 조작할 수 있습니다. 예를 들어 JavaScript IntelliSense는 `.d.ts` 파일에 선언된 값에 대해 제공될 수 있고([추가 정보](https://github.com/Microsoft/TypeScript-Handbook/blob/master/pages/Writing%20Definition%20Files.md)) TypeScript에 선언된 인터페이스 및 클래스 등의 형식은 JsDoc 주석에서 형식으로 사용할 수 있습니다. 

다음 내용은 JsDoc 태그를 사용하는 같은 프로젝트에서 인터페이스를 통해 이 형식 정보를 JavaScript 파일에 제공하는 TypeScript 정의 파일의 간단한 예제입니다.

_**JavaScript에서 사용되는 TypeScript 선언**_

<img src="https://raw.githubusercontent.com/wiki/Microsoft/TypeScript/images/decl1.png" height="400" width="640"/>

## <a name="Auto"></a> 형식 정의의 자동 획득
TypeScript 환경에서 가장 인기 있는 JavaScript 라이브러리에는 `.d.ts` 파일을 통해 설명되는 API가 있고 해당 정의의 가장 일반적인 리포지토리는 [DefinitelyTyped](https://github.com/DefinitelyTyped/DefinitelyTyped)에 있습니다.

기본적으로 Salsa 언어 서비스는 어떤 JavaScript 라이브러리가 사용 중인지 검색하고, 더 다양한 IntelliSense를 제공하기 위해 라이브러리를 설명하는 해당 `.d.ts` 파일을 자동으로 다운로드하여 참조합니다. 파일은 `%LOCALAPPDATA%\Microsoft\TypeScript`의 사용자 폴더 아래에 있는 캐시에 다운로드됩니다. 

> [!NOTE]
> `tsconfig.json` 구성 파일을 사용할 경우 이 기능은 기본적으로 **사용되지 않지만** 아래 추가로 설명된 대로 사용되도록 설정할 수 있습니다.

현재 자동 검색은 npm에서 다운로드된 종속성(`package.json` 파일 읽기 수행), Bower(`bower.json` 파일 읽기 수행) 및 대략 상위 400개의 가장 인기 있는 JavaScript 라이브러리 목록과 일치하는 프로젝트의 느슨한 파일에 적용됩니다. 예를 들어 프로젝트에 `jquery-1.10.min.js`가 있는 경우 더 나은 편집 환경을 제공하기 위해 `jquery.d.ts` 파일이 페치 및 다운로드됩니다. 이 `.d.ts` 파일은 프로젝트에 영향을 미치지 않습니다. 

자동 획득을 사용하지 않으려면 다음 설명대로 구성 파일을 추가하여 기능을 사용하지 않도록 설정합니다. 사용할 정의 파일을 직접 프로젝트 내에 수동으로 배치할 수 있습니다.

## <a name="ES6"></a> ES6 이상 지원

ES6 또는 ECMAScript 2015는 JavaScript의 다음 버전입니다. 클래스, 화살표 함수, `let`/`const` 등의 새로운 구문이 언어에 추가됩니다. 이 새로운 구문이 모두 Visual Studio에서 지원됩니다.

TypeScript에서 제공하는 주요 기능 중 하나는 ES6 기능을 사용하고 아직 해당 최신 기능을 인식하지 못하는 JavaScript 런타임에서 실행될 수 있는 코드를 내보내는 기능입니다. 일반적으로 이 기능을 "소스 간 컴파일(transpiling)"이라고 합니다. JavaScript에서는 같은 언어 서비스를 사용하므로 ES6+에서 ES5로의 소스 간 컴파일을 활용할 수 있습니다.

이를 설정하기 전에 어느 정도 구성 옵션을 이해해야 합니다.  TypeScript는 `tsconfig.json` 파일을 통해 구성됩니다. 해당 파일이 없는 경우 일부 기본값이 사용됩니다. 호환성 때문에 JavaScript 파일만(그리고 선택적으로 `.d.ts` 파일) 있는 컨텍스트에서는 이러한 기본값이 서로 다릅니다. JavaScript 파일을 컴파일하려면 `tsconfig.json` 파일을 추가하고 이러한 기본값의 일부를 명시적으로 설정해야 합니다.

tsconfig 파일에 대한 필수 설정은 다음과 같이 설명됩니다.

 - `allowJs`: JavaScript 파일이 인식되려면 이 값을 `true`로 설정해야 합니다.
기본적으로 이 값은 `false`이므로 TypeScript가 JavaScript로 컴파일되고, 방금 컴파일한 파일이 컴파일러에 포함되지 않게 하려면 이 설정이 필요합니다.
 - `outDir`: 내보낸 JavaScript 파일이 검색된 후 프로젝트에 포함되지 않도록 하려면 이 값을 프로젝트에 포함되지 않은 위치로 설정해야 합니다(아래 `exclude` 참조).
 - `module`: 모듈을 사용할 경우 이 설정은 내보낸 코드에서 사용해야 하는 모듈 형식을 컴파일러에 알립니다(예: Browserify와 같은 노드 또는 bundler의 경우 `commonjs`).
 - `exclude`: 이 설정은 프로젝트에 포함하지 않을 폴더를 나타냅니다. 
 출력 위치 및 `node_modules` 또는 `temp`와 같은 프로젝트 이외 폴더를 이 설정에 추가해야 합니다.
 - `enableAutoDiscovery`: 이 설정을 통해 위에서 설명한 대로 정의 파일을 자동으로 검색 및 다운로드할 수 있습니다.
 - `compileOnSave`: 이 설정은 언제든 소스 파일이 Visual Studio에서 저장되면 다시 컴파일해야 하는 경우 컴파일러에 알립니다.

`./out` 폴더에서 JavaScript 파일을 CommonJS 모듈로 변환하기 위해 아래와 같은 설정이 `tsconfig.json` 파일에 포함됩니다.

```json
{
  "compilerOptions": {
    "module": "commonjs",
    "allowJs": true,
    "outDir": "out"
  },
  "exclude": [
    "node_modules",
    "wwwroot",
    "out"
  ],
  "compileOnSave": true,
  "typingOptions": {
    "enableAutoDiscovery": true
  }
}
```

위 설정을 적용하고 아래 표시된 대로 여러 ECMAScript 2015 언어 기능이 포함된 소스 파일(`./app.js`)이 있는 경우:

```js
import {Subscription} from 'rxjs/Subscription';

class Foo {
    sayHi(name) {
        return `Hi ${name}, welcome to Salsa!`;
    }
}

export let sqr = x => x * x;
export default Subscription;
```

아래와 같이 표시되는 ECMAScript 5(기본값)를 대상으로 지정하는 `./out/app.js`로 파일을 내보냅니다.

```js
"use strict";
var Subscription_1 = require('rxjs/Subscription');
var Foo = (function () {
    function Foo() {
    }
    Foo.prototype.sayHi = function (name) {
        return "Hi " + name + ", welcome to Salsa!";
    };
    return Foo;
}());
exports.sqr = function (x) { return x * x; };
Object.defineProperty(exports, "__esModule", { value: true });
exports.default = Subscription_1.Subscription;
//# sourceMappingURL=app.js.map
```

## <a name="JSX"></a> JSX 구문 지원

Visual Studio 2017의 JavaScript에는 JSX 구문에 대한 다양한 지원이 있습니다. JSX는 JavaScript 파일 내에서 HTML 태그를 허용하는 구문 집합입니다. 

아래 그림은 `comps.tsx` TypeScript 파일에 정의된 React 구성 요소 및 JSX 식 내에서 완료 및 문서화를 위해 IntelliSense를 통해 완료되는 `app.jsx` 파일에서 이 구성 요소가 사용되는 것을 보여 줍니다.
여기에는 TypeScript가 필요하지 않습니다. 이 특정 예제에는 일부 TypeScript 코드도 포함됩니다.
<img src="https://raw.githubusercontent.com/wiki/Microsoft/TypeScript/images/react.png" height="500" width="640"/>

> [!NOTE]
> JSX 구문을 React 호출로 변환하려면 `"jsx": "react"` 설정을 위에 설명된 `tsconfig.json` 파일의 `compilerOptions`에 추가해야 합니다.

빌드 시 `./out/app.js'에서 만들어진 JavaScript 파일에는 다음 코드가 포함됩니다.

```js
"use strict";
var comps_1 = require('./comps');
var x = React.createElement(comps_1.RepoDisplay, {description: "test"});
```

