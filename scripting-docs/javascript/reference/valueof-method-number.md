---
title: "valueOf 메서드 (Number) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 0242a9ce-d41a-4c9b-af59-e8df32bbd913
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d7918fb94673803e99d476d63fd814bce19bf9a5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="valueof-method-number"></a>valueOf 메서드(Number)
지정된 된 숫자의 기본 값을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
number.valueOf()  
```  
  
#### <a name="parameters"></a>매개 변수  
 이 메서드는 매개 변수가 없습니다.  
  
## <a name="return-value"></a>반환 값  
 반환합니다.  
  
## <a name="remarks"></a>설명  
 다음 예제에서는 인스턴스화된 숫자 개체의이 메서드의 반환 값과 동일 합니다.  
  
```JavaScript  
var num = 1234;  
var s = num.valueOf();  
  
if (num === s)  
document.write("same");  
else  
document.write("different");  
  
// Output:  
// same  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]