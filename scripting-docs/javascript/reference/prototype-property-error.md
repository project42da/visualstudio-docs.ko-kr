---
title: "prototype 속성 (Error) | Microsoft Docs"
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
ms.assetid: 6c268a51-1a3d-4397-abf8-e54ca4e598fe
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b7d0413d3541691a38672e7c0720b58245725b76
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="prototype-property-error"></a>prototype 속성(Error)
프로토타입에 대 한 오류에 대 한 참조를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
error.prototype  
```  
  
## <a name="remarks"></a>설명  
 `error` 인수는 오류의 이름입니다.  
  
 사용 하 여는 `prototype` 속성을 오류에는 기본 기능 집합을 제공 합니다. 인스턴스의 새 개체는 해당 개체에 할당된 프로토타입의 동작을 "상속"합니다.  
  
 예를 들어 배열의 최대 요소 값을 반환하는 `Error` 개체에 메서드를 추가하려면 함수를 선언하고 `Error.prototype`에 추가한 다음 사용합니다.  
  
```JavaScript  
function getSeverity(){  
    if (this.number > 1000)  
        return "high";  
    else  
        return "low";  
}  
Error.prototype.getSev = getSeverity;  
var myError = new Error();  
myError.number = 5000;  
  
document.write(myError.getSev());   
  
// Output: high  
  
```  
  
 모든 내장 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 개체는 `prototype` 속성은 읽기 전용입니다. 속성 및 메서드는 프로토타입에 추가할 수 있지만 개체에 다른 프로토타입을 할당할 수 있습니다. 그러나 사용자 정의 개체에는 새 프로토타입을 할당할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]