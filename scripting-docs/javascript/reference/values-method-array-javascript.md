---
title: "values 메서드 (Array) (JavaScript) | Microsoft Docs"
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
ms.assetid: b20699d6-f8b1-4744-8551-9e81c82850dd
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d1a90dfd81ae8baf6590f69f0126adc97d42c20e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="values-method-array-javascript"></a>values 메서드(Array)(JavaScript)
배열의 값을 반환하는 반복기를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
arrayObj.values();  
```  
  
#### <a name="parameters"></a>매개 변수  
 `arrayObj`  
 필수 요소. Array 개체입니다.  
  
## <a name="remarks"></a>설명  
  
## <a name="example"></a>예제  
 다음 예제에서는 배열의 값을 가져오는 방법을 보여 줍니다.  
  
```JavaScript  
var v = ["a", "b", "c"].values();  
// v.next().value == "a"  
// v.next().value == "b"  
// v.next().value == "c"   
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]