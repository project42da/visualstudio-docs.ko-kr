---
title: .ofs 파일에 있는 하나 이상의 속성을 선택한 메시지 클래스에 사용할 수 없습니다.
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VSTO.NewFormRegionWizard.OFSPropertyError
dev_langs:
- VB
- CSharp
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: cfae8533337bbe18c89dbb670fb58a0c89c6c54c
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34692501"
---
# <a name="one-or-more-properties-in-the-ofs-file-are-not-valid-for-the-message-class-selected"></a>.ofs 파일에 있는 하나 이상의 속성을 선택한 메시지 클래스에 사용할 수 없습니다.
  이 오류 Outlook에서 디자인 한 양식 영역을 가져올 때 나타나지만 양식 영역에 하나 이상의 필드의 마지막 페이지에서 선택한 메시지 클래스와 호환 되지 않습니다는 **새 양식 영역** 마법사.  

예를 들어 **새 양식 영역** 마법사의 마지막 페이지에서 **작업(IPM.Task)** 을 선택할 수 있습니다. 양식 영역에는 **회사 주소** 필드에 회사 주소가 없는 경우 작업 때문에이 오류가 발생 합니다. 따라서는 **회사 주소** 필드와 호환 되지 않습니다.는 `IPM.Task` message 클래스입니다.  
  
 선택할 수 있는 **작업 (IPM 합니다. 작업)** 의 마지막 페이지에는 **새 양식 영역** 마법사. 양식 영역에는 **회사 주소** 필드에 회사 주소가 없는 경우 작업 때문에이 오류가 발생 합니다. 따라서는 **회사 주소** 필드와 호환 되지 않습니다.는 `IPM.Task` message 클래스입니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   **새 양식 영역** 마법사의 마지막 페이지에서 양식 영역의 필드와 호환되는 메시지 클래스를 선택합니다.  
  
-   Outlook의 Forms 디자이너에서 메시지 클래스와 호환 되지 않는 필드를 제거 합니다. 마지막 페이지에서 선택 하려면 필드 제거는 **새 양식 영역** 마법사.  
  
## <a name="see-also"></a>참고자료  
 [연습: Outlook에서 디자인 한 양식 영역 가져오기](../vsto/walkthrough-importing-a-form-region-that-is-designed-in-outlook.md)  
  
  