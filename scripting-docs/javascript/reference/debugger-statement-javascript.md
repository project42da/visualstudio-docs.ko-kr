---
title: "문 (JavaScript) 디버거 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- debugger_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- debugger statement
ms.assetid: c6d2e193-c1f7-4fb3-8a4e-cc9823174ae4
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9e64e860cebd065f357857484e932b4aea3f05ea
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="debugger-statement-javascript"></a>debugger 문(JavaScript)
실행을 일시 중단 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
debugger  
```  
  
## <a name="remarks"></a>설명  
 배치할 수 `debugger` 실행이 일시 중단 하는 절차에는 문입니다. 사용 하 여 `debugger` 문이 코드에 중단점을 설정 하는 것과 비슷합니다.  
  
 `debugger` 문 실행을 일시 중단 되지만 파일을 모두 닫고 하거나 모든 변수의 선택을 취소 하지 않습니다.  
  
> [!NOTE]
>  `debugger` 스크립트를 디버깅 하는 경우가 아니면 문에 영향을 주지 않습니다.  
  
## <a name="example"></a>예제  
 사용 하 여이 예제는 `debugger` 문을 통해 반복 실행을 일시 중지는 `for` 루프입니다.  
  
> [!NOTE]
>  이 예제를 실행 하려면 스크립트 디버거가 설치 되어 있어야 하며 스크립트 디버그 모드에서 실행 해야 합니다.  
>   
>  Internet Explorer 8에 포함 되어는 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 디버거 합니다. 이전 버전의 Internet Explorer를 사용하는 경우 [방법: Internet Explorer에서 스크립트 디버깅 사용 및 시작](http://go.microsoft.com/fwlink/?LinkId=133801)을 참조하세요.  
  
```JavaScript  
for(i = 1; i<5; i++) {  
   // Print i to the Output window.  
   Debug.write("loop index is " + i);  
   // Wait for user to resume.  
   debugger  
}  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [JavaScript 문](../../javascript/reference/javascript-statements.md)   
 [조건부 컴파일](../../javascript/advanced/conditional-compilation-javascript.md)