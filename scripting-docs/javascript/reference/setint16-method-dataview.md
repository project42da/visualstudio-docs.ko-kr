---
title: "setInt16 메서드 (DataView) | Microsoft Docs"
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
ms.assetid: 901c6cf5-63fb-45bd-9ea8-185c1d892060
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 04ea20079c217d1aeef8456e9c81996661fed356
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="setint16-method-dataview"></a>setInt16 메서드(DataView)
보기의 시작 부분부터 지정 된 바이트 오프셋에서 Int16 값을 설정합니다. 맞춤 제약 조건이 없습니다. 모든 오프셋에서 멀티 바이트 값을 설정할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
dataView.setInt16(byteOffset, value, littleEndian);   
```  
  
## <a name="parameters"></a>매개 변수  
 `byteOffset`  
 값을 검색 해야 하는 버퍼의 위치입니다.  
  
 `value`  
 설정할 값입니다.  
  
 `littleEndian`  
 선택 사항입니다. False 또는 정의 되지 않은 경우 기록 될 big endian 값, 그렇지 않으면 little endian 값을 써야 하 합니다.  
  
## <a name="remarks"></a>설명  
 보기의 끝을 넘어 작성할 수 하는 경우 이러한 메서드는 예외를 발생 시킵니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 DataView의 첫 번째 Int16를 설정 하는 방법을 보여 줍니다.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            dataView.setInt16(0, 9);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]