---
title: "entries 메서드 (Array) (JavaScript) | Microsoft Docs"
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
ms.assetid: 9bc46afb-74d2-4f99-8c95-f46475acf21d
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ff1e32ba0782d637ea1418daf5b3a56203d7e34b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="entries-method-array-javascript"></a>entries 메서드(Array)(JavaScript)
배열의 키/값 쌍을 반환하는 반복기를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
arrayObj.entries();  
```  
  
#### <a name="parameters"></a>매개 변수  
 `arrayObj`  
 필수 요소. Array 개체입니다.  
  
## <a name="remarks"></a>설명  
  
## <a name="example"></a>예제  
 다음 예제에서는 배열의 키/값 쌍을 가져오는 방법을 보여 줍니다.  
  
```JavaScript  
var entries = ["a", "b", "c"].entries();  
// entries.next().value == [0, "a"]  
// entries.next().value == [1, "b"]  
// entries.next().value == [2, "c"]   
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]