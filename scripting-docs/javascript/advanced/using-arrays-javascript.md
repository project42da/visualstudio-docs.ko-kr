---
title: "배열 사용(JavaScript) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "배열[JavaScript]"
  - "배열[JavaScript], 개체"
ms.assetid: 785c5acd-b8b3-4152-af9a-dd42ecdd75ba
caps.latest.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 13
---
# 배열 사용(JavaScript)
[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]의 배열은 *스파스*입니다.  즉, 번호가 0, 1 및 2인 세 개의 요소가 있는 배열인 경우 3에서 49 사이의 요소는 신경쓰지 않고 50번 요소를 만들 수 있습니다.  배열에 자동 length 변수가 포함된 경우\(배열 길이의 자동 모니터링에 대한 설명은 [내장 개체](../../javascript/intrinsic-objects-javascript.md) 참조\) 변수 길이가 4가 아닌 51로 설정됩니다.  요소 번호 매김에 간격이 없는 배열을 만들 수 있지만 반드시 이렇게 할 필요는 없습니다.  
  
 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]에서는 개체와 배열이 서로 거의 동일합니다.  두 가지 주된 차이점으로, 배열이 아닌 개체에는 자동 length 속성이 포함되지 않으며, 배열에는 개체의 속성과 메서드가 포함되지 않습니다.  
  
## 배열 처리  
 배열은 다음 예제에 표시된 것처럼 대괄호\(\[\]\)를 사용하여 처리할 수 있습니다.  대괄호에는 숫자 값 또는 정수로 계산되는 식을 넣습니다.  
  
```javascript  
var entryNum = 5;  
  
sample = new Array();  
  
sample[1] = "Maple Street";  
sample[entryNum] = 25;  
  
document.write (sample[1]);  
document.write (" ");  
document.write (sample[entryNum]);  
  
// Output: Maple Street 25  
  
```  
  
## 연결 배열 개체  
 개체 속성에 액세스하기 위해서는 일반적으로 점 연산자 "."를 사용합니다.  다음 예제를 참조하세요.  
  
```javascript  
myObject.aProperty  
```  
  
 이 경우 속성 이름이 식별자입니다.  인덱스 연산자\(\[\]\)를 사용하여 개체의 속성에 액세스할 수도 있습니다.  이 경우에는 데이터 값이 문자열과 연결된 *연결 배열*로 개체를 처리합니다.  다음 예제를 참조하세요.  
  
```javascript  
myObject["aProperty"] // Same as above.  
```  
  
 인덱스 연산자는 보다 일반적으로 배열 요소 액세스와 연관됩니다.  개체와 함께 사용할 때는 인덱스가 속성 이름을 나타내는 문자열 리터럴입니다.  
  
 다음은 개체 속성에 액세스하는 두 가지 방법의 중요한 차이점입니다.  
  
1.  식별자\(점\(.\) 구문\)와 같이 처리되는 속성 이름은 데이터와 같은 방식으로 조작할 수 없습니다.  
  
2.  인덱스\(대괄호\(\[\]\) 구문\)와 같이 처리되는 속성 이름은 데이터와 같은 방식으로 조작할 수 있습니다.  
  
 이러한 차이점은 사용자 입력에 따라 개체를 생성할 때처럼 런타임까지 속성 이름을 모를 때 유용합니다.  연결 배열에서 모든 속성을 추출하려면 `for…in` 루프를 사용해야 합니다.