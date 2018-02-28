---
title: "인코딩할 URI에 잘못 된 문자가 | Microsoft Docs"
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
- VS.WebClient.Help.SCRIPT5024
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: a3f0fdbb-8d4b-41ae-a396-43dfc9483760
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1e93d145ea6b0991123c2a7c80f8acf54a83a264
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="the-uri-to-be-encoded-contains-an-invalid-character"></a>인코딩될 URI에 잘못된 문자가 있습니다.
문자열 URI (Uniform Resource Identifier)로 인코딩하 하려고 했지만 잘못 된 문자를 포함 합니다. 대부분의 문자 Uri에 변환 된 문자열 내 유효 하지만, 일부 유니코드 문자 시퀀스를 사용할 수 없습니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   인코딩할 문자열에 유효한 유니코드 시퀀스를 확인 합니다. 구성 요소 및 구분 기호 시퀀스는 전체 URI로 구성 됩니다. 꺾쇠 괄호의 이름은 구성 요소를 나타내며 및 ":", "/", ";" 및 "?"는 예약 된 문자를 구분 기호로 사용 합니다. 일반 형식은 다음과 같습니다.  
  
    ```JavaScript  
    <Scheme>:<first>/<second>;<third>?<fourth>  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [encodeURI 함수](../../javascript/reference/encodeuri-function-javascript.md)   
 [encodeURIComponent 함수](../../javascript/reference/encodeuricomponent-function-javascript.md)