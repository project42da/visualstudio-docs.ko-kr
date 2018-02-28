---
title: "new 연산자 (JavaScript) | Microsoft Docs"
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
- new_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- new operator in JavaScript
ms.assetid: 5ea556ba-7ae6-426c-8430-9032eee5a0a5
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0ad004abb534d69bed1a1bd9bbd2ae96755544b9
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="new-operator-javascript"></a>new 연산자(JavaScript)
새 개체를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
new constructor ([arguments])   
```  
  
## <a name="parameters"></a>매개 변수  
 `constructor`  
 필수 요소. 개체의 생성자입니다. 생성자에 인수가 없는 경우 괄호를 생략할 수 있습니다.  
  
 `arguments`  
 선택 사항입니다. 새 개체의 생성자에 전달할 인수입니다.  
  
## <a name="remarks"></a>설명  
 `new` 연산자는 다음 작업을 수행 합니다.  
  
-   멤버 없이 개체를 만듭니다.  
  
-   으로 새로 만든된 개체에 대 한 포인터를 전달 해당 개체에 대 한 생성자를 호출 하는 `this` 포인터입니다.  
  
-   생성자에는 다음 생성자에 전달 된 인수에 따라 개체를 초기화 합니다.  
  
 이러한 주석은 올바르게 사용 하 여 **새** 연산자입니다.  
  
```JavaScript  
my_object = new Object;  
my_array = new Array();  
my_date = new Date("Jan 5 1996");  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [function 문](../../javascript/reference/function-statement-javascript.md)