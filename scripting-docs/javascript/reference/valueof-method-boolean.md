---
title: "valueOf 메서드 (Boolean) | Microsoft Docs"
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
ms.assetid: ac6ad343-7663-406a-a2b7-4cc5025ca3d6
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c36eda63fb38886df4d8bffec7cfdbb6c6d05eb8
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="valueof-method-boolean"></a>valueOf 메서드(Boolean)
지정 된 부울 값의 기본 값을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
boolean.valueOf()  
```  
  
## <a name="return-value"></a>반환 값  
 기본 값 (true 또는 false) 부울입니다.  
  
## <a name="remarks"></a>설명  
 다음 코드에는이 메서드를 사용 하는 방법을 보여 줍니다.  
  
```JavaScript  
var bool = new Boolean("true");  
var s = bool.valueOf();  
document.write(s);  
  
// Output: true  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]