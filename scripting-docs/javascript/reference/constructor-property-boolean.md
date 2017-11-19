---
title: "constructor 속성 (Boolean) | Microsoft Docs"
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
ms.assetid: b67ca875-23c6-4687-a5ce-1cdd25d1c923
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 091da5342c4713c8eba646a8bd78c315a6a0fa48
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="constructor-property-boolean"></a>constructor 속성(Boolean)
부울 값을 만드는 함수를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
boolean.constructor([[value])  
```  
  
#### <a name="parameters"></a>매개 변수  
 `boolean`  
 부울의 이름입니다.  
  
 `value`  
 선택 사항입니다. 부울 값을 지정합니다. 숫자 1 또는 0 일 수 있습니다 문자열 "true" 또는 "false"입니다.  
  
## <a name="remarks"></a>설명  
 `constructor` 속성 Boolean 개체의 인스턴스를 구성 하는 함수에 대 한 참조를 포함 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 생성자 속성의 사용을 보여 줍니다.  
  
```JavaScript  
var x = new Boolean("true");  
  
if (x.constructor == Boolean)  
    document.write("Object is a Boolelan.");  
  
// Output:  
// Object is a Boolean.  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]