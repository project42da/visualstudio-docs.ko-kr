---
title: "fill 메서드 (Array) (JavaScript) | Microsoft Docs"
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
ms.assetid: 11526627-c0bb-4157-a8c4-0a039079b4a1
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4546bafb3fa3a8c242b8b7ef4ef2863ea86bf179
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="fill-method-array-javascript"></a>fill 메서드(Array)(JavaScript)
지정된 값으로 배열을 채웁니다.  
  
## <a name="syntax"></a>구문  
  
```  
arrayObj.fill(value [ , start [ , end ] ]);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `arrayObj`  
 필수 요소. Array 개체입니다.  
  
 `value`  
 필수 요소. 배열을 채우는 데 사용되는 값입니다.  
  
 `start`  
 선택 사항입니다. 배열 값을 채우는 데 사용되는 시작 인덱스입니다. 기본값은 0입니다.  
  
 `end`  
 선택 사항입니다. 배열 값을 채우는 데 사용되는 끝 인덱스입니다. 기본값은 `this` 개체의 length 속성입니다.  
  
## <a name="remarks"></a>설명  
 경우 `start` 가 음수 이면 `start` 로 처리 `length` + `start`여기서 `length` 배열의 길이입니다. 경우 `end` 가 음수 이면 `end` 로 처리 `length` + `end`합니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 배열을 값으로 채웁니다.  
  
```JavaScript  
[0, 0, 0].fill(7, 1);  
// Array contains [0,7,7]  
  
[0, 0, 0].fill(7);  
// Array contains [7,7,7]  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]