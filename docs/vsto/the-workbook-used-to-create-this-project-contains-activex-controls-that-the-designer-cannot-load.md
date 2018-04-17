---
title: 이 프로젝트를 만드는 사용 되는 통합 문서에 디자이너에서 로드할 수 없는 ActiveX 컨트롤 포함 | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VST.SelectDocWizard.ContainsActiveXControls
dev_langs:
- VB
- CSharp
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 8d31674f54ce454db50a63572c24f92031e7d886
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="the-workbook-used-to-create-this-project-contains-activex-controls-that-the-designer-cannot-load"></a>이 프로젝트를 만드는 데 사용된 통합 문서에 디자이너에서 로드할 수 없는 ActiveX 컨트롤이 있습니다.
  Word 문서나 Excel 워크시트에 프로그래밍 방식으로 컨트롤을 추가하고, 문서나 통합 문서를 저장하고, 문서나 통합 문서를 기반으로 새 문서 수준 솔루션을 만들 때 오류가 나타납니다.  
  
 컨트롤의 관리되는 형식을 설명하는 정보는 문서 또는 통합 문서와 함께 저장되지 않습니다. 해당 문서 또는 통합 문서를 기반으로 새 솔루션을 만들 때 Visual Studio에는 호스트 항목 디자이너에 컨트롤을 로드할 충분한 정보가 없습니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  문서 또는 통합 문서를 엽니다.  
  
2.  런타임에 추가된 컨트롤을 제거합니다. 문서 또는 통합 문서에서 컨트롤을 선택하고 DELETE 키를 눌러서 이 작업을 수행합니다.  
  
3.  문서 또는 통합 문서를 기반으로 문서 수준 솔루션을 만듭니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [런타임에 Office 문서에 컨트롤 추가](../vsto/adding-controls-to-office-documents-at-run-time.md)  
  
  