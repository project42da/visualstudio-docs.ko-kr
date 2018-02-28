---
title: "with 문 (JavaScript) | Microsoft Docs"
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
- with_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- With statement
ms.assetid: 892c7621-ae9e-4c10-8adb-05532274b1ca
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 35d49b13261c66cde0ecd53517a99361f6aecb79
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="with-statement-javascript"></a>with 문(JavaScript)
문의 기본 개체를 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
with (object) {  
    statements  
}   
```  
  
## <a name="parameters"></a>매개 변수  
 `object`  
 기본 개체입니다.  
  
 `statements`  
 `object`가 기본 개체가 되는 하나 이상의 문입니다.  
  
## <a name="remarks"></a>설명  
 일반적으로 `with` 문은 특정한 상황에서 작성해야 할 코드의 양을 줄이기 위해 사용합니다.  
  
> [!WARNING]
>  strict 모드에서는 `with`를 사용할 수 없습니다. `with`를 사용하면 코드를 읽고 디버깅하기 어려워질 수 있으며 일반적으로 사용하지 않아야 합니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 `Math` 개체가 반복적으로 사용됩니다.  
  
```JavaScript  
x = Math.cos(3 * Math.PI) + Math.sin(Math.LN10)   
y = Math.tan(14 * Math.E)  
```  
  
## <a name="example"></a>예제  
 예제를 다시 작성하여 `with` 문을 사용하는 경우 코드가 더 간결해 집니다.  
  
```JavaScript  
with (Math){  
   x = cos(3 * PI) + sin (LN10)    
   y = tan(14 * E)  
}  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [this 문](../../javascript/reference/this-statement-javascript.md)