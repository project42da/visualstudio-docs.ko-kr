---
title: "RegExp 개체 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: RegExp
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- RegExp object, overview
- RegExp object
ms.assetid: 7f6b1073-8cbb-49ed-94b6-56833ba663c5
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b7319e4556721bcfd397061ce525acfb3278c6b9
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="regexp-object-javascript"></a>RegExp 개체(JavaScript)
정규식 패턴의 결과 대 한 정보를 저장 하는 내장 전역 개체와 일치 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
RegExp.property   
```  
  
## <a name="remarks"></a>설명  
 필요한 *속성* 인수 중 하나가 될 수는 `RegExp` 개체의 속성입니다.  
  
 `RegExp` 개체를 직접 만들 수 없지만 항상 사용 하기 위해 사용할 수 있습니다. 성공적인 정규식 검색이 완료 될 때까지의 다양 한 속성의 초기 값은 `RegExp` 개체는 다음과 같습니다.  
  
|속성|줄임|초기 값|  
|--------------|---------------|-------------------|  
|인덱스입니다.||-1|  
|입력|$_|빈 문자열입니다.|  
|lastIndex||-1|  
|lastMatch|$&|빈 문자열입니다.|  
|lastParen|$+|빈 문자열입니다.|  
|leftContext|$`|빈 문자열입니다.|  
|rightContext|$'|빈 문자열입니다.|  
|$1 - $9|$1 - $9|빈 문자열입니다.|  
  
 성공적인 정규식 검색이 완료 될 때까지 해당 속성이 해당 값으로 정의 되지 않았습니다.  
  
 전역 `RegExp` 개체와 일치 하지 않습니다는 **정규식** 개체입니다. 동일한 작업 같은 같지만, 프로세스와 다른 별도 됩니다. 전역 속성 `RegExp` 개체의 속성을 하는 동안 발생 시 각 일치 항목에 대 한 정보를 지속적으로 업데이트 된 포함 된 **정규식** 개체 발생 하는 일치 항목에 대 한 정보만 포함 해당 인스턴스와 **정규식**합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 정규식 검색을 수행합니다. 일치 항목을 표시 하 고 전역에서 submatches `RegExp` 개체에서 반환 되는 배열에서는 `exec` 메서드.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
<a name="js56jsobjregexpprop"></a>   
## <a name="properties"></a>속성  
 [$1... $9 속성](../../javascript/reference/dollar-1-dot-dot-dot-dollar-9-properties-regexp-javascript.md) &#124; [index 속성](../../javascript/reference/index-property-regexp-javascript.md) &#124; [입력 속성](../../javascript/reference/input-property-dollar-regexp-javascript.md) &#124; [lastIndex 속성](../../javascript/reference/lastindex-property-regexp-javascript.md) &#124; [lastMatch 속성](../../javascript/reference/lastmatch-property-dollar-regexp-javascript.md) &#124; [lastParen 속성](../../javascript/reference/lastparen-property-dollar-regexp-javascript.md) &#124; [leftContext 속성](../../javascript/reference/leftcontext-property-dollar-grave-regexp-javascript.md) &#124; [rightContext 속성](../../javascript/reference/rightcontext-property-dollar-regexp-javascript.md)  
  
## <a name="methods"></a>메서드  
 `RegExp` 개체에는 메서드가 없습니다.  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [Regular Expression 개체](../../javascript/reference/regular-expression-object-javascript.md)   
 [정규식 구문 (JavaScript)](http://msdn.microsoft.com/en-us/ab0766e1-7037-45ed-aa23-706f58358c0e)   
 [String 개체](../../javascript/reference/string-object-javascript.md)