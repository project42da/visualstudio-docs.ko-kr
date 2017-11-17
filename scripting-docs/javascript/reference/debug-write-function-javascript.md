---
title: "Debug.write 함수 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: Write
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: write method [JavaScript]
ms.assetid: fd1cfbb3-46cb-47cc-896c-a70d457dd413
caps.latest.revision: "22"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 74aad7a01e0dc166f22173cf193b312e1fd4d804
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="debugwrite-function-javascript"></a>Debug.write 함수(JavaScript)
스크립트 디버거를 문자열을 보냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
Debug.write([str1 [, str2 [, ... [, strN]]]])  
```  
  
## <a name="parameters"></a>매개 변수  
 *strN, s t r, 2..., str1*  
 선택 사항입니다. 문자열 스크립트 디버거를 보내려고 합니다.  
  
## <a name="remarks"></a>설명  
 `Debug.write` 함수 런타임 시 스크립트 디버거의 직접 실행 창에 문자열을 보냅니다. 스크립트 디버그 중이 아닌 경우는 `Debug.write` 함수에 영향을 주지 않습니다.  
  
 `Debug.write` 함수는 거의 동일는 `Debug.writeln` 함수입니다. 유일한 차이점은는 `Debug.writeln` 함수 문자열을 보낸 후에 줄 바꿈 문자를 보냅니다.  
  
## <a name="example"></a>예제  
 사용 하 여이 예제는 `Debug.write` 함수 스크립트 디버거의 직접 실행 창에 변수 값을 표시 합니다.  
  
> [!NOTE]
>  이 예제를 실행 하려면 스크립트 디버거가 설치 되어 있어야 하며 스크립트 디버그 모드에서 실행 해야 합니다.  
>   
>  Internet Explorer 8에 포함 되어는 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 디버거 합니다. 이전 버전의 Internet Explorer를 사용하는 경우 [방법: Internet Explorer에서 스크립트 디버깅 사용 및 시작](http://go.microsoft.com/fwlink/?LinkId=133801)을 참조하세요.  
  
```JavaScript  
var counter = 42;  
Debug.write("The value of counter is " + counter);  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [Debug 개체](../../javascript/reference/debug-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [Debug.writeln 함수](../../javascript/reference/debug-writeln-function-javascript.md)