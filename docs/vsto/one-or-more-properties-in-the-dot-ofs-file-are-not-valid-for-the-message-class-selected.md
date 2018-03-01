---
title: ".Ofs 파일에 하나 이상의 속성이 선택한 메시지 클래스에 유효 하지 않습니다. | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VSTO.NewFormRegionWizard.OFSPropertyError
dev_langs:
- VB
- CSharp
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 6ab0b36921911ac8c70501096868f47a40371f79
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="one-or-more-properties-in-the-ofs-file-are-not-valid-for-the-message-class-selected"></a>.ofs 파일에 있는 하나 이상의 속성을 선택한 메시지 클래스에 사용할 수 없습니다.
  이 오류는 Outlook에서 디자인되는 양식 영역을 가져올 때 나타나지만 양식 영역의 하나 이상의 필드가 **새 양식 영역** 마법사의 마지막 페이지에서 선택하는 메시지 클래스와 호환되지 않습니다.  
  
 예를 들어 **새 양식 영역** 마법사의 마지막 페이지에서 **작업(IPM.Task)** 을 선택할 수 있습니다. 양식 영역에 **회사 주소** 필드가 포함된 경우 작업에 회사 주소가 없기 때문에 이 오류를 받게 됩니다. 따라서 **회사 주소** 필드는 IPM.Task 메시지 클래스와 호환되지 않습니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   **새 양식 영역** 마법사의 마지막 페이지에서 양식 영역의 필드와 호환되는 메시지 클래스를 선택합니다.  
  
-   Outlook의 양식 디자이너에서 **새 양식 영역** 마법사의 마지막 페이지에서 선택하려는 메시지 클래스와 호환되지 않는 필드를 제거합니다.  
  
## <a name="see-also"></a>참고 항목  
 [연습: Outlook에서 디자인한 양식 영역 가져오기](../vsto/walkthrough-importing-a-form-region-that-is-designed-in-outlook.md)  
  
  