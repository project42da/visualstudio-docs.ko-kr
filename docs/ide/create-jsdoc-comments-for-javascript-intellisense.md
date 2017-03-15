---
title: "JavaScript IntelliSense에 대한 JSDoc 주석 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a0dadc81-3755-4a47-bcee-c1010819ff2a
caps.latest.revision: 4
caps.handback.revision: 4
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# JavaScript IntelliSense에 대한 JSDoc 주석 만들기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Visual Studio의 IntelliSense는 표준 JSDoc 주석을 사용하여 스크립트에 추가하는 정보를 표시합니다.  JSDoc 주석을 사용하여 함수, 필드 및 변수와 같은 코드 요소에 대한 정보를 제공할 수 있습니다.  
  
## JSDoc 주석 태그  
 다음과 같은 표준 JSDoc 주석 태그는 IntelliSense에서 코드에 대한 정보를 표시하는 데 사용됩니다.  
  
|JSDoc 태그|구문|노트|  
|--------------|--------|--------|  
|@deprecated|@deprecated *description*|사용되지 않는 함수 또는 메서드를 지정합니다.|  
|@description|@description *description*|함수 또는 메서드에 대한 설명을 지정합니다.|  
|@param|@param {*type*} *parameterName**description*|함수 또는 메서드의 매개 변수에 대한 정보를 지정합니다.<br /><br /> TypeScript는 @paramTag도 지원합니다.|  
|@property|@property {*type*} *propertyName*|설명을 포함하여 개체에 정의된 필드 또는 멤버에 대한 정보를 지정합니다.|  
|@returns|@returns {*type*}|반환 값을 지정합니다.<br /><br /> TypeScript의 경우 @returns 대신 @returnType을 사용합니다.|  
|@summary|@summary *description*|함수 또는 메서드에 대한 설명을 지정합니다\(@description과 동일\).|  
|@type|@type {*type*}|상수 또는 변수의 형식을 지정합니다.|  
|@typedef|@typedef {*type*} *customTypeName*|사용자 지정 형식을 지정합니다.|  
  
### 예  
 다음 예제에서는 `getArea`라는 함수에 대한 @description, @param 및 @return JSDoc 태그를 사용하는 방법을 보여 줍니다.  
  
```javascript  
/** @description Determines the area of a circle that has the specified radius parameter.  
 * @param {number} radius The radius of the circle.  
 * @return {number}  
 */  
function getArea(radius) {  
    var areaVal;  
    areaVal = Math.PI * radius * radius;  
    return areaVal;  
}  
```  
  
 앞의 예제에서 IntelliSense는 `getArea`에 대한 여는 괄호를 입력할 때 설명, 매개 변수 및 반환 정보를 표시합니다.  
  
 ![함수에 대한 IntelliSense 정보](../ide/media/js_intellisense_jsdoc_comments.png "JS\_IntelliSense\_JSDoc\_Comments")  
  
 다음 예제에서는 @property 태그와 함께 @typedef 태그를 사용하는 방법을 보여 줍니다.  
  
```javascript  
/**  
  * @typedef {object} Weather  
  * @property {string} current The current weather.  
  */  
function getForecast(Weather) {  
}  
  
var w = new Weather();  
```  
  
 다음 예제에서는 @type JSDoc 태그를 사용하는 방법을 보여 줍니다.  이 예제와 같이 초기 별표 쌍\(\*\*\) 뒤에 오는 단일 별표\(\*\)는 필요하지 않습니다.  
  
```javascript  
/**  
    @type {string}  
*/  
const RED = 'FF0000';  
  
```  
  
 다음 예제에서는 @deprecated JSDoc 태그를 사용하는 방법을 보여 줍니다.  
  
```javascript  
/**  
 * @deprecated since version 2.0  
 */  
function old() {  
}  
```