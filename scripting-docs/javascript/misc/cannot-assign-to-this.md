---
title: "없습니다 지정 &#39;이 &#39; | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: javascript
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.WebClient.Help.SCRIPT5000
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: ba2b0a2b-f0f8-4698-b335-a4ab6c166671
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c164b9b7d2989076a9dc0ef0bafba6159bc08885
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="cannot-assign-to-39this39"></a>없습니다 지정 &#39;이 &#39;
값을 할당 하려고 했습니다. **이**합니다. **이** 는 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 키워드 중 하나를 참조입니다.  
  
-   현재는 메서드를 실행 하는 개체  
  
-   현재 메서드가 없는 (또는 메서드가 다른 개체에 속해 있지 않습니다) 하는 경우 전역 개체입니다.  
  
 메서드는 한 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 개체를 통해 호출 되는 함수입니다. 메서드 내에서 **이** 키워드는 메서드를 통해 호출 된 개체에 대 한 참조 (클래스 생성자를 호출 하 여 만든 개체에는 **새** 연산자).  
  
 메서드 내에서 사용할 수 있습니다 **이** 현재 개체를 참조 하는 새 값을 할당할 수 없습니다 **이**합니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   에 할당 하려고 하지 마십시오 **이**합니다. 점 연산자를 사용 하 여 인스턴스화된 개체의 메서드나 속성에 액세스 하려면 (예: circle**.** radius)입니다.  
  
    > [!NOTE]
    >  사용자가 만든 변수 이름을 지정할 수 없습니다 **이**; 이기는 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 예약어입니다.  
  
## <a name="see-also"></a>참고 항목  
 [이 문은](../../javascript/reference/this-statement-javascript.md)   
 [스크립트 문제 해결](../../javascript/advanced/troubleshooting-your-scripts-javascript.md)