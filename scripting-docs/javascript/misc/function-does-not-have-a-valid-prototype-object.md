---
title: "함수에 유효한 프로토타입 개체가 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- javascript
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.WebClient.Help.SCRIPT5023
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: b9e34652-190f-4b57-b253-df2e8c4d09c6
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a4e2cbf198a452cd61f1355682ea3041436d2a27
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="function-does-not-have-a-valid-prototype-object"></a>함수에 유효한 프로토타입 개체가 없습니다.
사용 하려는 **instanceof** 개체는 특정 함수 클래스에서 파생 되지만 개체의 재정의 확인 하려면 `prototype` 하나로 속성 `null`, 또는 외부 개체 형식 (모두 유효 하지 않은 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 개체). 외부 개체 (예를 들어 Internet Explorer의 문서 또는 창 개체)는 호스트 개체 모델에서 개체 또는 외부 COM 개체 수 있습니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   함수의 확인 `prototype` 속성 참조 하는 유효한 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 개체입니다.  
  
## <a name="see-also"></a>참고 항목  
 [함수 개체](../../javascript/reference/function-object-javascript.md)   
 [prototype 속성(Object)](../../javascript/reference/prototype-property-object-javascript.md)