---
title: "파일 열기 명령을 사용 하 여 파일을 표시 합니다. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- project types, supporting Open File command
- Open File command
- persistence, supporting Open File command
ms.assetid: 4fff0576-b2f3-4f17-9769-930f926f273c
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f2cbcb6e6239552ae32c817601634587a2fe3a41
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="displaying-files-by-using-the-open-file-command"></a>파일 열기 명령을 사용 하 여 파일을 표시 합니다.
다음 단계는 IDE에서 처리 하는 방법을 설명는 **열려 있는 파일** 명령에서 제공 되는 **파일** 의 메뉴 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다. 또한이 단계는 프로젝트가이 명령에서 발생 하는 호출에 응답 해야 방법을 나타냅니다.  
  
 사용자가 클릭할 때는 **열려 있는 파일** 명령을 **파일** 메뉴에서 파일을 선택 하 고는 **열려 있는 파일** 대화 상자에서 다음 프로세스가 발생 합니다.  
  
1.  IDE을 실행 중인 문서 테이블을 사용 하는 파일은 이미 프로젝트에서 열려 있는지 여부를 결정 합니다.  
  
    -   파일이 열려 있으면 IDE 창 자신에 게 있습니다.  
  
    -   IDE를 호출 하는 파일이 열려 있지 않으면 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.IsDocumentInProject%2A> 각 프로젝트는 프로젝트 파일을 열 수를 쿼리할 수 있습니다.  
  
        > [!NOTE]
        >  프로젝트 구현에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.IsDocumentInProject%2A>, 우선 순위는 프로젝트 파일을 열고 수준을 나타내는 값을 제공 합니다. 우선 순위 값은 제공 된 <xref:Microsoft.VisualStudio.Shell.Interop.VSDOCUMENTPRIORITY> 열거형입니다.  
  
2.  각 프로젝트 중요도 나타내는 우선 순위를 사용 하 여 응답 되는 프로젝트 파일을 열 수에 부과 합니다.  
  
3.  IDE는 프로젝트 파일을 열고 결정 하는 다음 조건을 사용 합니다.  
  
    -   가장 높은 우선 순위 (DP_Intrinsic)를 사용 하 여 응답 하는 프로젝트 파일을 엽니다. 여러 프로젝트가 우선이 순위를 사용 하 여 응답을 응답할 첫 번째 프로젝트 파일을 엽니다.  
  
    -   가장 높은 우선 순위 (DP_Intrinsic)로 없는 프로젝트 응답 했지만 동일 하 고 낮은 우선 순위를 가진 모든 프로젝트 응답, 활성 프로젝트 파일을 엽니다. 활성 프로젝트가 없으면 응답 하는 첫 번째 프로젝트 파일을 엽니다.  
  
    -   프로젝트가 (DP_Unsupported) 파일의 소유권을 주장, 기타 파일 프로젝트 파일을 엽니다.  
  
         기타 파일 프로젝트의 인스턴스를 만든 경우 프로젝트는 항상 DP_CanAddAsExternal 값을 사용 하 여 응답 합니다. 이 값은 프로젝트 파일을 열 수를 나타냅니다. 이 프로젝트는 다른 프로젝트에 없는 열려 있는 파일을 보관 하는 데 사용 됩니다. 이 프로젝트에 있는 항목 목록 유지 되지 않습니다. 이 프로젝트에 표시 됩니다. **솔루션 탐색기** 만 사용 하는 경우 파일을 열려고 합니다.  
  
         기타 파일 프로젝트 파일을 열 수 있도록 나타내지 않는 경우 프로젝트의 인스턴스 만들어지지 않습니다. 이 경우 IDE는 기타 파일 프로젝트의 인스턴스를 만들고 하 고 프로젝트 파일을 열 수를 알려 줍니다.  
  
4.  IDE는 프로젝트 파일을 열고를 결정 하는 즉시 호출는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.OpenItem%2A> 해당 프로젝트에서 메서드.  
  
5.  다음 프로젝트는 프로젝트 관련 편집기나 표준 편집기를 사용 하 여 파일을 열 수입니다. 자세한 내용은 참조 [하는 방법: 프로젝트 관련 편집기 열기](../../extensibility/how-to-open-project-specific-editors.md) 및 [하는 방법: 표준 편집기 열기](../../extensibility/how-to-open-standard-editors.md)각각.  
  
## <a name="see-also"></a>참고 항목  
 [파일 열기 명령을 사용 하 여 표시](../../extensibility/internals/displaying-files-by-using-the-open-with-command.md)   
 [열기 및 프로젝트 항목 저장](../../extensibility/internals/opening-and-saving-project-items.md)   
 [방법: 프로젝트 관련 편집기 열기](../../extensibility/how-to-open-project-specific-editors.md)   
 [방법: 표준 편집기 열기](../../extensibility/how-to-open-standard-editors.md)