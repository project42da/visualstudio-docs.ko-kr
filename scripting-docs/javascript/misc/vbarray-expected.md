---
title: "VBArray가 필요 합니다. | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: javascript
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.WebClient.Help.SCRIPT5013
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: f2998d7d-13a4-4bbe-b872-3ff3316551e4
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9b07c5e08e4178c9c31045317627424f5192f5e1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="vbarray-expected"></a>VBArray가 필요합니다.
사용자가 제공한 개체 중 하나는 예상 될 때 Visual Basic safeArray 하지 않은입니다.  
  
```  
new VBArray(safeArray);  
```  
  
 VBArrays는 읽기 전용이므로 직접 만들 수 없습니다. SafeArray 인수는 VBArray 값이 고 얻어야 VBArray 값에 전달 되기 전에 `VBArray` 생성자입니다. 이 작업은 기존 ActiveX 또는 다른 개체에서 값을 검색하는 방식으로만 수행할 수 있습니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   만 통과 **VBArray** 개체는 **VBArray** 생성자입니다.  
  
## <a name="see-also"></a>참고 항목  
 [VBArray 개체](../../javascript/reference/vbarray-object-javascript.md)   
 [배열 사용](../../javascript/advanced/using-arrays-javascript.md)