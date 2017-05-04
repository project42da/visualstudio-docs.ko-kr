---
title: "나머지 연산자(JavaScript) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "%"
dev_langs: 
  - "JavaScript"
  - "DHTML"
helpviewer_keywords: 
  - "나머지 연산자, JavaScript"
  - "% 연산자[JavaScript]"
  - "Modulo 함수[JavaScript]"
ms.assetid: 087d654f-623b-498d-95ff-596d26bf674d
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 나머지 연산자(JavaScript)
한 식의 값을 다른 식의 값으로 나눈 후 나머지를 반환합니다.  
  
## 구문  
  
```  
  
result = number1 % number2  
```  
  
## 인수  
 `result`  
 임의의 변수입니다.  
  
 `number1`  
 임의의 숫자 식입니다.  
  
 `number2`  
 임의의 숫자 식입니다.  
  
## 설명  
 나머지 연산자는 `number1`을 `number2`로 나눈 후 나머지만 `result`로 반환합니다.  `result`의 부호는 `number1`의 부호와 같습니다.  `result`의 값은 0과 `number2`의 절대 값 사이입니다.  
  
 다음 코드에서는 나머지 연산자를 사용하는 방법을 보여 줍니다.  
  
```  
var modResult = 19 % 6.7;  
document.write(modResult);  
  
// Output: 5.6  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## 참고 항목  
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요\(JavaScript\)](../../javascript/misc/operator-subtractsummary-javascript.md)