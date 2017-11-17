---
title: "Boolean 개체 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: boolean_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Boolean object
- Boolean data type, Boolean object
ms.assetid: d67748f2-7bf5-4889-8269-e777616cc5f0
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 20695376e4935cf6ddc34f30e373df19575ece3f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="boolean-object-javascript"></a>Boolean 개체(JavaScript)
새 부울 값을 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
boolObj = new Boolean([boolValue])  
```  
  
## <a name="parameters"></a>매개 변수  
 `boolObj`  
 필수 요소. `Boolean` 개체가 할당되는 변수 이름입니다.  
  
 `boolValue`  
 선택 사항입니다. 새 개체에 대 한 초기 부울 값입니다. 경우 `boolvalue` 이 생략 되거나 `false`, 0, `null`, `NaN`, 빈 문자열을 Boolean 개체의 초기 값은 또는 `false`합니다. 그렇지 않은 경우 초기 값은 `true`합니다.  
  
## <a name="remarks"></a>설명  
 `Boolean` 개체는 Boolean 데이터 형식에 대 한 래퍼입니다. [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]암시적으로 사용 된 `Boolean` Boolean 데이터 형식으로 변환 됩니다 때마다 개체는 `Boolean` 개체입니다.  
  
 거의 인스턴스화하는 `Boolean` 개체를 명시적으로 합니다.  
  
## <a name="properties"></a>속성  
 다음 표에서는 `Boolean` 개체의 속성을 보여 줍니다.  
  
|속성|설명|  
|--------------|-----------------|  
|[constructor 속성](../../javascript/reference/constructor-property-boolean.md)|부울 값을 만드는 함수를 지정 합니다.|  
|[prototype 속성](../../javascript/reference/prototype-property-boolean.md)|부울의 프로토타입에 대한 참조를 반환합니다.|  
  
<a name="js56jsobjarraymeth"></a>   
## <a name="methods"></a>메서드  
 다음 표에서는 `Boolean` 개체의 메서드를 보여 줍니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[toString 메서드](../../javascript/reference/tostring-method-boolean-1.md)|부울 값의 문자열 표현을 반환합니다.|  
|[valueOf 메서드](../../javascript/reference/valueof-method-boolean.md)|부울에 대 한 참조를 가져옵니다.|  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]