---
title: 이 프로젝트를 만드는 데 사용된 통합 문서에 디자이너에서 로드할 수 없는 ActiveX 컨트롤이 있습니다.
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
ms.openlocfilehash: 9d47ee32f23ca0eb856b2a8f618d60fae552a027
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34693073"
---
# <a name="the-workbook-used-to-create-this-project-contains-activex-controls-that-the-designer-cannot-load"></a>이 프로젝트를 만드는 데 사용된 통합 문서에 디자이너에서 로드할 수 없는 ActiveX 컨트롤이 있습니다.
  Word 문서나 Excel 워크시트에 프로그래밍 방식으로 컨트롤을 추가하고, 문서나 통합 문서를 저장하고, 문서나 통합 문서를 기반으로 새 문서 수준 솔루션을 만들 때 오류가 나타납니다.  
  
 컨트롤의 관리되는 형식을 설명하는 정보는 문서 또는 통합 문서와 함께 저장되지 않습니다. 해당 문서 또는 통합 문서를 기반으로 새 솔루션을 만들 때 Visual Studio에는 호스트 항목 디자이너에 컨트롤을 로드할 충분한 정보가 없습니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  문서 또는 통합 문서를 엽니다.  
  
2.  런타임에 추가 된 컨트롤을 제거 합니다. 문서 또는 통합 문서 및 키를 눌러 선택 하 여이 작업을 수행할 수는 **삭제** 키입니다.  
  
3.  문서 또는 통합 문서를 기반으로 문서 수준 솔루션을 만듭니다.  
  
## <a name="see-also"></a>참고자료  
 [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [런타임에 Office 문서에 컨트롤 추가](../vsto/adding-controls-to-office-documents-at-run-time.md)  
  
  